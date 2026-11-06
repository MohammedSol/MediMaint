# MaintiDoc — Assistant Documentaire Multimodal et Agentique pour la Maintenance Biomédicale

> **Projet Académique & Professionnel** | Durée : 6 semaines | 6 Livrables  
> **Livrable 1 :** Cadrage, Constitution du Corpus et Architecture Cible

---

## 📋 Présentation Générale

**MaintiDoc** est un assistant documentaire agentique et multimodal conçu pour accompagner les techniciens et ingénieurs biomédicaux dans leurs opérations d'urgence et de maintenance préventive. Le système permet d'interroger en langage naturel (texte et images de pupitres/voyants) un corpus documentaire hautement qualifié portant sur deux équipements hospitaliers critiques :

1. **Radiographie numérique mobile :** **AGFA DR 100e** (générateur 32 kW, détecteur plat sans fil CsI DR 14s, logiciel NX Workstation).
2. **Moniteur patient multiparamétrique :** **Mindray BeneVision N-Series** (modèles N12, N15, N17, N19 et N22 avec modules satellites MPM, capnographie et SpO2 Masimo SET®).

---

## 🏥 Équipements de Référence & Couverture Technique

| Famille | Équipement | Fabricant | Particularités Techniques |
| :--- | :--- | :--- | :--- |
| **Radiographie Numérique** | **AGFA DR 100e** | Agfa Radiology Solutions | Système mobile motorisé, 40-125 kV, 32 kW, tube anode tournante 3 000 rpm, détecteur Wi-Fi DR 14s (148 µm), traitement d'image MUSICA® et SmartRotate™. |
| **Moniteur Multiparamétrique** | **BeneVision N-Series** | Mindray Bio-Medical | Écrans tactiles 12,1" à 21,5" pivotables Full HD, analyse ECG 12 dérivations (Glasgow), SpO2 Masimo SET®, PNI oscillométrique, surveillance des arythmies et compatibilité eGateway/HL7/DICOM. |

---

## 📁 Structure du Projet

```
MediMaint_AI/
├── corpus/
│   ├── inventaire.csv                     # Inventaire officiel des 63 documents (métadonnées complètes)
│   ├── prompts_corpus.md                  # Registre d'audit et traçabilité des prompts IA
│   │
│   ├── documents/
│   │   ├── radiographie_numerique/
│   │   │   ├── reels/                     # 6 manuels officiels Agfa réels (0360B, 0365B, 0365C, 0365D)
│   │   │   └── synthetiques/              # Manuels condensés, protocoles maintenance, codes d'erreur, sécurité
│   │   │
│   │   └── moniteur_multiparametrique/
│   │       ├── reels/                     # Manuel officiel Mindray N-Series Rév 3.0 FR (482 pages)
│   │       ├── reels_anglais/             # Guides de formation, nettoyage officiel, quick guide FDA
│   │       └── synthetiques/              # Manuels condensés, étalonnage PNI, firmware V3.12, codes modules
│   │
│   ├── images/
│   │   ├── radiographie_numerique/        # Fiches d'inspection photographique pupitre et docking DR 100e
│   │   └── moniteur_multiparametrique/    # Fiches photographiques face avant N22 et connecteurs N17
│   │
│   └── tests/
│       ├── contradictions/                # Documents contenant des divergences de révision (tensions, fréquences, seuils)
│       ├── prompt_injection/              # Documents piégés avec tentatives d'injection indirecte de prompt
│       ├── questions_evaluation/          # Banques de 40 questions métrologiques (5 niveaux de difficulté)
│       └── ocr/                           # Simulation de rapport scanné dégradé pour test de robustesse
│
├── rapport/
│   ├── L1_MaintiDoc_Rapport_Cadrage_Architecture.md  # Rapport de cadrage et conception (12-15 pages)
│   └── Architecture_Cible_MaintiDoc.md               # Spécification détaillée de l'architecture 5 couches
│
└── README.md                              # Guide d'accueil du dépôt
```

---

## 📊 État et Métriques du Corpus (Objectif 30-50 Documents)

| Catégorie | Réels (PDFs) | Synthétiques (.md) | Tests & Évaluation | Total par catégorie |
| :--- | :---: | :---: | :---: | :---: |
| **Manuels d'utilisation & Guides officiels** | 7 | 6 | 0 | **13** |
| **Procédures de maintenance & métrologie** | 0 | 8 | 0 | **8** |
| **Fiches de sécurité réglementaires** | 0 | 4 | 0 | **4** |
| **Tables de codes d'erreur & alarmes** | 0 | 6 | 0 | **6** |
| **Schémas d'architecture & connectique (ASCII)**| 0 | 6 | 0 | **6** |
| **Fiches d'inspection photographique** | 0 | 4 | 0 | **4** |
| **Rapports d'intervention & fiches d'incident**| 0 | 10 | 0 | **10** |
| **Documents de test (Contradictions, Injections, OCR)**| 0 | 0 | 4 | **4** |
| **Banques de questions d'évaluation RAG** | 0 | 0 | 2 | **2** |
| **Guides de nettoyage et formation** | 4 | 2 | 0 | **6** |
| **TOTAL GÉNÉRAL** | **11 PDFs (1 267 p.)** | **46 docs** | **6 docs** | 🎯 **63 DOCUMENTS** |

> **Statut de validation :** L'objectif initial de 30 à 50 documents est largement dépassé (**126% de l'objectif max**). L'intégralité des entrées est répertoriée dans [`corpus/inventaire.csv`](corpus/inventaire.csv).

---

## 🏗️ Architecture Cible du Système

L'architecture MaintiDoc repose sur **5 couches logiques étanches** :
1. **Couche Présentation :** Interface Web/Mobile réactive avec upload de photos et affichage des sources avec badges de criticité.
2. **Couche Sécurité & Garde-fous :** Détecteur d'injections de prompt, filtre de périmètre (AGFA DR 100e & Mindray BeneVision exclusifs), anonymisation automatique RGPD des données patients et audit trail.
3. **Couche Orchestration Agentique :** Routeur de requêtes, décomposeur de tâches, outils d'appel RAG, OCR visuel, lookup déterministe de codes d'erreur et détecteur de contradictions entre versions de manuels.
4. **Couche RAG & Vector Store :** Découpage sémantique 512 tokens / recouvrement 128, embeddings multilingues BGE-M3 (1024 d), indexation ChromaDB/Qdrant et re-ranking par cross-encoder.
5. **Couche Données & Corpus :** Entrepôt immuable du corpus réel et synthétique.

---

## 📅 Calendrier des 6 Livrables

| Livrable | Semaines | Objet | Statut |
| :---: | :---: | :--- | :---: |
| **L1** | S1 – S2 | Cadrage opérationnel, constitution du corpus (63 docs) et architecture cible | 🟢 **TERMINÉ** |
| **L2** | S3 | Pipeline RAG, chunking hiérarchique et indexation vectorielle ChromaDB | 🟡 Prochain jalon |
| **L3** | S3 – S4 | Traitement multimodal, module OCR et analyse des photos de pupitres | ⚪ Planifié |
| **L4** | S4 – S5 | Orchestration agentique, outillage spécialisé et lookup de codes d'erreur | ⚪ Planifié |
| **L5** | S5 | Banc d'évaluation quantitative RAGAS, résistance aux injections et contradictions | ⚪ Planifié |
| **L6** | S6 | Rapport final de projet, vidéo de démonstration et soutenance | ⚪ Planifié |

---

## ⚖️ Avertissement Légal & Licence

- Les documents originaux constructeurs (PDFs) sont la propriété exclusive d'**Agfa Radiology Solutions NV** et de **Shenzhen Mindray Bio-Medical Electronics Co., Ltd.** et sont exploités dans un cadre strictement pédagogique et de recherche universitaire.
- Les documents synthétiques, grilles de maintenance, fiches de sécurité et codes d'erreur créés pour le projet sont mis à disposition sous licence **Creative Commons Attribution - Partage dans les Mêmes Conditions 4.0 International (CC BY-SA 4.0)**.
- **Avertissement :** Les documents synthétiques générés par IA ne doivent en aucun cas se substituer aux manuels d'origine pour des actes médicaux ou des interventions chirurgicales réelles.
