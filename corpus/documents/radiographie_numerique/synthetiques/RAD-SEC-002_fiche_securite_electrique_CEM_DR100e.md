---
id: RAD-SEC-002
titre: "Fiche de sécurité — Électrique et Compatibilité Électromagnétique — AGFA DR 100e"
reference: "SEC-DR100e-ELEC-CEM-2025"
famille: radiographie_numerique
modele: AGFA DR 100e
type: fiche_securite
categorie_securite: electrique_CEM
langue: fr
statut: synthetique
date_creation: 2025-01-01
verifie: false
pages_estimees: 4
---

<!-- Electrical & EMC Safety Sheet | AGFA DR 100e Digital Mobile Unit -->

# Fiche de sécurité : Sécurité électrique et CEM (AGFA DR 100e)

### 1. Classification de sécurité électrique (CEI 60601-1)
- **Classe de protection contre les chocs électriques :** Appareil de **Classe I** avec conducteur de protection relié à la terre.
- **Partie appliquée :** Détecteur DR 14s considéré comme partie appliquée de **Type B**.
- **Indice de protection des enveloppes :** 
  - Châssis mobile DR 100e : **IP20** (protégé contre les corps solides > 12 mm, non étanche aux liquides).
  - Détecteur portable DR 14s : **IP54** (protégé contre les poussières et les projections d'eau).
- **Mode d'exploitation :** Service intermittent avec charge continue de l'électronique de contrôle.

---

### 2. Spécifications du réseau d'alimentation et branchement

| Paramètre électrique | Exigence technique constructeur | Risque en cas de non-conformité |
| :--- | :--- | :--- |
| **Tension nominale réseau** | 230 V AC monophasé ±10% (207 V à 253 V) | Erreur E-001, blocage de l'onduleur haute tension. |
| **Fréquence industrielle** | 50 / 60 Hz ± 1 Hz | Instabilité de régulation haute fréquence (40 kHz). |
| **Calibre disjoncteur mural** | Disjoncteur différentiel 16 A courbe C | Déclenchement intempestif de ligne lors de la charge condensateur. |
| **Résistance maximale de ligne**| < 1,0 Ω (mesurée à la prise murale) | Chute de tension lors du tir -> artéfacts de sous-exposition. |
| **Câble secteur d'origine** | Câble surmoulé 3G2.5 mm² blindé, longueur 8 m | Échauffement de ligne, risque d'incendie si section sous-dimensionnée. |

---

### 3. Avertissements majeurs pour la sécurité électrique

> **DANGER : Présence de haute tension interne (125 kV)**  
> Ne jamais ouvrir les capots du compartiment générateur ou de la colonne. Seul un technicien biomédical agréé et habilité aux risques haute tension est autorisé à intervenir à l'intérieur du châssis.

> **ATTENTION : Raccordement exclusif sur socle de prise avec terre certifiée**  
> L'appareil ne doit être raccordé qu'à des prises de courant conformes aux normes hospitalières munies d'une broche de terre efficace (résistance de terre inférieure à 0,2 Ω). Ne jamais utiliser de bloc multiprise mobile ou de rallonge non homologuée.

> **ATTENTION : Présence d'eau ou de sol mouillé**  
> Ne jamais circuler ni faire fonctionner l'appareil sur des flaques de liquides ou dans des locaux mouillés (ex: douches, zones de lavage). En cas de pénétration accidentelle de liquide à l'intérieur du pupitre, couper le disjoncteur général et faire vérifier le système avant réarmement.

---

### 4. Compatibilité électromagnétique (CEM) — Directive CEI 60601-1-2

L'Agfa DR 100e a été conçu et certifié pour un environnement électromagnétique hospitalier de Classe A / Groupe 1.

#### 4.1 Distances de séparation minimales recommandées

| Émetteur RF / Dispositif perturbateur | Bande de fréquences | Distance minimale de sécurité |
| :--- | :---: | :---: |
| **Téléphones portables 4G / 5G / Smartphones** | 800 MHz – 5,8 GHz | **0,30 mètre** |
| **Talkies-walkies professionnels de sécurité** | 136 – 470 MHz (5 W) | **1,50 mètre** |
| **Bistouri électrique / Générateur HF électrochirurgical**| 300 kHz – 3 MHz | **2,00 mètres** |
| **Tunnel d'IRM (Résonance Magnétique)** | Champ magnétique statique > 0,5 mT | **INTERDIT dans la salle d'examen IRM (Zone 4)** |

---
*Fiche de conformité CEM & Sécurité électrique MaintiDoc 2025.*
