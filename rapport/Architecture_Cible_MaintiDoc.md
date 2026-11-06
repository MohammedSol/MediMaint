# MaintiDoc — Architecture du Système Agentique
## Conception Architecturale — Livrable 1

> **Rôle :** Architecte système  
> **Équipements :** AGFA DR 100e · Mindray BeneVision N-Series (N12/N15/N17/N19/N22)  
> **Date :** 2025-11-06 · **Révision :** 1.0

---

## 1. Vision Architecturale

MaintiDoc est un système **RAG agentique multimodal** à 5 couches, conçu pour répondre en langage naturel aux questions de techniciens biomédicaux sur leurs équipements, en s'appuyant sur un corpus documentaire vérifié.

### Principes directeurs

| Principe | Application |
|----------|-------------|
| **Vérifiabilité** | Toute réponse cite sa source documentaire avec numéro de page |
| **Sécurité patient** | Aucune information sur le patient n'est persistée |
| **Robustesse** | Détection des injections de prompt et des contradictions |
| **Traçabilité** | Chaque requête est journalisée avec sa chaîne de retrieval |
| **Domaine fermé** | L'agent refuse explicitement les requêtes hors-périmètre |

---

## 2. Architecture en Blocs (5 couches)

```mermaid
flowchart TD
    subgraph C1["🖥️ COUCHE 1 — Interface Utilisateur"]
        UI_CHAT["Chat Texte\n(requêtes libres)"]
        UI_IMG["Upload Image / Photo\n(écran moniteur, panneau)"]
        UI_VOICE["Saisie vocale\n(optionnel — S4)"]
        UI_RESULT["Affichage réponse\n+ sources citées\n+ niveau confiance"]
    end

    subgraph C2["🛡️ COUCHE 2 — Sécurité & Validation"]
        SEC_INJECT["Détecteur\nInjection Prompt"]
        SEC_SCOPE["Filtre\nHors-périmètre"]
        SEC_ANON["Anonymisation\ndonnées patient"]
        SEC_LOG["Journal\naudit requêtes"]
    end

    subgraph C3["🤖 COUCHE 3 — Orchestrateur Agentique"]
        AG_ROUTER["Router de requêtes\n(texte / image / hybride)"]
        AG_PLANNER["Planificateur\n(décompose requêtes complexes)"]
        AG_TOOLS["Outils spécialisés"]
        AG_SYNTH["Synthétiseur\n(agrège les résultats)"]
        AG_CONTRA["Détecteur\nContradictions"]
    end

    subgraph C3T["Outils de l'agent"]
        T1["🔍 RAG Search\n(retrieval sémantique)"]
        T2["📸 OCR Tool\n(image → texte)"]
        T3["📋 Code Erreur Lookup\n(table de codes)"]
        T4["🗓️ Historique Maintenance\n(timeline équipement)"]
        T5["⚠️ Sécurité Checker\n(précautions & warnings)"]
    end

    subgraph C4["📚 COUCHE 4 — Moteur RAG"]
        RAG_EMB["Moteur d'Embedding\nBGE-M3 / multilingual-e5"]
        RAG_VS["Vector Store\nChromaDB / Qdrant"]
        RAG_RERANK["Re-ranker\n(cross-encoder)"]
        RAG_CHUNK["Chunker\n(par section, 512 tokens,\noverlap 128)"]
    end

    subgraph C5["💾 COUCHE 5 — Corpus & Données"]
        D_REAL["Documents Réels\n(PDF officiel Agfa/Mindray)"]
        D_SYN["Documents Synthétiques\n(rapports, procédures, historiques)"]
        D_TEST["Documents de Test\n(contradictions, injections)"]
        D_IDX["Index documentaire\ninventaire.csv"]
        D_META["Métadonnées\n(famille, modèle, type, page)"]
    end

    subgraph LLM["🧠 LLM Générateur"]
        LLM_GEN["GPT-4o / Gemini 1.5 Pro\n(génération réponse)"]
        LLM_CTX["Contexte injecté\n(chunks + métadonnées)"]
    end

    UI_CHAT --> SEC_INJECT
    UI_IMG --> SEC_INJECT
    UI_VOICE --> SEC_INJECT
    SEC_INJECT -->|"✅ Validé"| SEC_SCOPE
    SEC_INJECT -->|"⛔ Bloqué"| UI_RESULT
    SEC_SCOPE -->|"✅ Dans périmètre"| SEC_ANON
    SEC_SCOPE -->|"⛔ Hors périmètre"| UI_RESULT
    SEC_ANON --> AG_ROUTER
    AG_ROUTER --> AG_PLANNER
    AG_PLANNER --> AG_TOOLS
    AG_TOOLS --> T1 & T2 & T3 & T4 & T5
    T1 --> RAG_EMB
    T2 --> RAG_EMB
    RAG_EMB --> RAG_VS
    RAG_VS --> RAG_RERANK
    RAG_RERANK --> AG_SYNTH
    AG_SYNTH --> AG_CONTRA
    AG_CONTRA --> LLM_CTX
    LLM_CTX --> LLM_GEN
    LLM_GEN --> AG_SYNTH
    AG_SYNTH --> SEC_LOG
    AG_SYNTH --> UI_RESULT
    D_REAL & D_SYN --> RAG_CHUNK
    RAG_CHUNK --> RAG_EMB
    D_IDX & D_META --> RAG_VS
    D_TEST --> RAG_CHUNK
```

---

## 3. Parcours d'une Requête (Sequence Diagram)

```mermaid
sequenceDiagram
    actor Tech as 👷 Technicien
    participant UI as Interface
    participant Sec as Garde-fous
    participant Agt as Agent
    participant OCR as OCR Tool
    participant RAG as RAG Engine
    participant LLM as LLM

    Tech->>UI: "Quelle est la procédure de calibration du DR 14s ?"
    UI->>Sec: Requête brute
    Sec->>Sec: Détection injection prompt
    Sec->>Sec: Vérification périmètre (DR 100e / BeneVision)
    Sec->>Agt: Requête validée + contexte équipement

    Agt->>Agt: Planification (requête simple → RAG direct)
    Agt->>RAG: Query embedding("calibration DR 14s procédure")
    RAG->>RAG: Recherche vectorielle top-10
    RAG->>RAG: Re-ranking cross-encoder top-5
    RAG-->>Agt: 5 chunks + métadonnées (source, page, révision)

    Agt->>Agt: Détection contradictions entre chunks
    Agt->>LLM: Prompt structuré + chunks + instruction citation
    LLM-->>Agt: Réponse structurée avec balises [SOURCE: doc, p.X]
    Agt-->>UI: Réponse + sources cliquables + niveau confiance
    UI-->>Tech: Réponse affichée avec 3 sources référencées
    Agt->>Agt: Journal audit (timestamp, requête hashée, chunks utilisés)
```

---

## 4. Parcours d'une Requête Image (Photo d'un Panneau)

```mermaid
sequenceDiagram
    actor Tech as 👷 Technicien
    participant UI as Interface
    participant Agt as Agent
    participant OCR as OCR Tool
    participant T3 as Code Erreur Lookup
    participant RAG as RAG Engine
    participant LLM as LLM

    Tech->>UI: 📸 Photo du panneau d'alarme (voyant rouge clignotant)
    UI->>Agt: Image + contexte ("que signifie cette alarme ?")
    Agt->>OCR: Extraction texte depuis image
    OCR-->>Agt: "E-042 SpO2 Signal Lost"
    Agt->>T3: Lookup code E-042 dans table codes erreurs
    T3-->>Agt: Code trouvé → cause + action recommandée
    Agt->>RAG: Recherche contexte élargi("E-042 SpO2 Signal Lost cause")
    RAG-->>Agt: Chunks pertinents (manuel + historique maintenance)
    Agt->>LLM: Synthèse : code + contexte RAG
    LLM-->>Agt: Réponse complète avec procédure corrective
    Agt-->>UI: Code identifié + cause + 3 étapes correctives + source p.142
    UI-->>Tech: ✅ Réponse complète
```

---

## 5. Flux de Données et Modèle d'Accès

### 5.1 Pipeline d'indexation (offline)

```mermaid
flowchart LR
    PDF["📄 PDF Réel\n(Agfa/Mindray)"] --> LOAD["PDF Loader\n(pypdf / pdfplumber)"]
    MD["📝 Markdown\nSynthétique"] --> LOAD2["MD Loader"]
    IMG["🖼️ Image\n(schéma, photo)"] --> OCR2["OCR\n(Tesseract / Azure)"]

    LOAD --> CLEAN["Nettoyage\n(headers/footers, lignes vides)"]
    LOAD2 --> CLEAN
    OCR2 --> CLEAN

    CLEAN --> META["Extraction métadonnées\n(famille, modèle, type, langue, page)"]
    META --> CHUNK["Chunking\n512 tokens / overlap 128\npar section logique"]
    CHUNK --> EMB["Embedding\nBGE-M3 multilingual\n(dim 1024)"]
    EMB --> VS["Vector Store\nChromaDB\ncollections: RAD | MON | TEST"]
    META --> IDX["inventaire.csv\nmis à jour"]
```

### 5.2 Modèle d'accès par rôle

| Rôle | Accès corpus | Fonctions autorisées |
|------|-------------|---------------------|
| **Technicien** | RAD + MON (docs vérifiés) | Consultation, historique propre équipement |
| **Ingénieur biomédical** | RAD + MON + TEST | Consultation + vue des contradictions détectées |
| **Administrateur** | Tout le corpus | Gestion inventaire, ajout/retrait documents |
| **Agent IA** | Corpus filtré par requête | RAG retrieval + lookup tables |

> [!IMPORTANT]
> Les documents de test (`tests/prompt_injection/`, `tests/contradictions/`) sont **exclus du corpus de production** et uniquement accessibles aux administrateurs pour évaluation.

### 5.3 Stratégie de chunking

| Type de document | Stratégie | Taille chunk |
|-----------------|-----------|-------------|
| Manuels utilisateur | Par section (H1/H2) | 512 tokens |
| Procédures maintenance | Par étape numérotée | 256 tokens |
| Codes d'erreur | Par code (1 chunk = 1 code) | 128 tokens |
| Rapports d'intervention | Par bloc sémantique | 384 tokens |
| Schémas illustrés | Texte alternatif + légende | 256 tokens |

---

## 6. Analyse des Risques (10 risques)

| # | Risque | Prob. | Impact | Criticité | Mitigation |
|---|--------|-------|--------|-----------|------------|
| **R01** | **Hallucination LLM** sur procédure critique (ex: tension kV incorrecte) | Moyenne | Critique | 🔴 Élevée | RAG strict (top-k faible) + disclaimer + citation obligatoire de source |
| **R02** | **Injection de prompt** dans le corpus (document piégé) | Faible | Élevé | 🟠 Moyenne | Scan préalable corpus + sandbox LLM + liste blanche des instructions système |
| **R03** | **Documents réels indisponibles** publiquement (licence restrictive) | Élevée | Élevé | 🟠 Moyenne | Corpus synthétique de substitution qualifié |
| **R04** | **OCR défaillant** sur documents scannés dégradés | Moyenne | Moyen | 🟡 Modérée | Prétraitement image (denoise, deskew) + seuil de confiance OCR |
| **R05** | **Données contradictoires** entre versions de manuel (ex: 0365B vs 0365D) | Élevée | Élevé | 🟠 Moyenne | Détecteur contradiction cross-chunks + alerte explicite dans réponse |
| **R06** | **Violation RGPD** : données patient dans une requête | Faible | Critique | 🟠 Moyenne | Anonymisation automatique (regex NER) + aucune persistance |
| **R07** | **Dérive hors-périmètre** : questions sur d'autres équipements | Moyenne | Faible | 🟢 Faible | Filtre domaine strict (liste blanche modèles) + rejet explicite |
| **R08** | **Latence excessive** (>5s) pour usage terrain sans réseau | Faible | Élevé | 🟡 Modérée | Cache embeddings + modèle local fallback (Ollama) |
| **R09** | **Document synthétique non vérifié** utilisé comme référence | Moyenne | Élevé | 🟠 Moyenne | Tag `verifie:false` → avertissement automatique dans la réponse |
| **R10** | **Mise à jour matériel** (nouveau firmware) rend corpus obsolète | Faible | Moyen | 🟢 Faible | Versionning documents + alertes révision dans inventaire |

---

## 7. Plan de Génération du Corpus (36+ documents)

### État cible du corpus

| Catégorie | Famille RAD | Famille MON | Total |
|-----------|------------|------------|-------|
| Manuels & documentation | 3 | 3 | **6** |
| Procédures de maintenance | 4 | 4 | **8** |
| Fiches de sécurité | 2 | 2 | **4** |
| Tables de codes d'erreur | 3 | 3 | **6** |
| Schémas illustrés (ASCII/SVG) | 3 | 3 | **6** |
| Photographies contextualisées | 2 | 2 | **4** |
| Documents de test | 3 | 3 | **6** |
| **Existants (SYN-001→005)** | 5 | 5 | **10** |
| **TOTAL** | **25** | **25** | **~50** |

### Nomenclature des nouveaux documents

**Manuels & documentation (RAD)**
- `RAD-MAN-001` Manuel utilisateur condensé DR 100e (digital) — inspiré 0365D
- `RAD-MAN-002` Guide de démarrage rapide DR 100e + DR 14s
- `RAD-MAN-003` Manuel d'utilisation DR 100e (Film/CR) — inspiré 0360B

**Manuels & documentation (MON)**
- `MON-MAN-001` Manuel utilisateur condensé BeneVision N17/N22 — inspiré FR 3.0
- `MON-MAN-002` Guide de référence rapide BeneVision N-Series
- `MON-MAN-003` Guide utilisateur avancé BeneVision (formation)

**Procédures de maintenance (RAD)**
- `RAD-PROC-001` Procédure maintenance préventive trimestrielle DR 100e
- `RAD-PROC-002` Procédure remplacement batterie détecteur DR 14s
- `RAD-PROC-003` Procédure contrôle qualité image (NUC + MTF)
- `RAD-PROC-004` Procédure remplacement tube à rayons X

**Procédures de maintenance (MON)**
- `MON-PROC-001` Procédure maintenance préventive trimestrielle BeneVision N-Series
- `MON-PROC-002` Procédure étalonnage PNI (pression non-invasive)
- `MON-PROC-003` Procédure mise à jour firmware (V3.0 → V3.12)
- `MON-PROC-004` Procédure remplacement batterie interne BeneVision

**Fiches de sécurité**
- `RAD-SEC-001` Fiche sécurité rayonnements ionisants — DR 100e
- `RAD-SEC-002` Fiche sécurité électrique et CEM — DR 100e
- `MON-SEC-001` Fiche sécurité alarmes et défaillances — BeneVision N-Series
- `MON-SEC-002` Fiche sécurité électrique et défibrillation — BeneVision

**Tables de codes d'erreur**
- `RAD-COD-001` Table codes erreurs générateur et exposition — DR 100e
- `RAD-COD-002` Table codes erreurs détecteur DR 14s (WiFi, batterie, capteur)
- `RAD-COD-003` Table messages d'état application NX Workstation
- `MON-COD-001` Table alarmes physiologiques — BeneVision N-Series
- `MON-COD-002` Table alarmes techniques — BeneVision N-Series
- `MON-COD-003` Table codes erreurs modules (ECG, SpO2, PNI, Temp)

**Schémas illustrés**
- `RAD-SCH-001` Schéma panneau de commandes générateur DR 100e (ASCII art)
- `RAD-SCH-002` Schéma connecteurs et ports réseau DR 100e
- `RAD-SCH-003` Schéma composants détecteur DR 14s (vue éclatée)
- `MON-SCH-001` Schéma face avant BeneVision N17/N22 (touches et connecteurs)
- `MON-SCH-002` Schéma modules et baies d'extension N-Series
- `MON-SCH-003` Schéma connexions capteurs (ECG, SpO2, PNI, Temp, IBP)

**Photographies contextualisées**
- `RAD-PHO-001` Description photographique panneau générateur DR 100e (voyants état)
- `RAD-PHO-002` Description photographique docking station DR 14s
- `MON-PHO-001` Description photographique face avant BeneVision N22 (voyants alarme)
- `MON-PHO-002` Description photographique connecteurs arrière BeneVision N17

**Documents de test (contradictions)**
- `TEST-CONT-002` Contradiction fréquence maintenance RAD (trimestrielle vs semestrielle)
- `TEST-CONT-003` Contradiction seuils alarme SpO2 MON (88% vs 90% vs 92%)
- `TEST-PI-002` Document piégé — fiche codes erreur MON avec injection cachée

**Cas de test complémentaires**
- `TEST-QEV-001` Questions d'évaluation RAG — famille radiographie (20 questions)
- `TEST-QEV-002` Questions d'évaluation RAG — famille moniteur (20 questions)
- `TEST-OCR-001` Document simulant un scan dégradé (texte brouillé, rotation)

