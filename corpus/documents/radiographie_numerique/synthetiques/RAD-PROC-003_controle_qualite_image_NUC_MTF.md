---
id: RAD-PROC-003
titre: "Procédure de contrôle qualité — NUC et MTF (DR 100e)"
reference: "PROC-DR100e-QC-NUC-MTF-2025"
famille: radiographie_numerique
modele: AGFA DR 100e
type: procedure_controle_qualite
periodicite: semestrielle
duree_estimee: "2h00"
qualification_requise: "Physicien médical ou technicien certifié Agfa"
langue: fr
statut: synthetique
date_creation: 2025-01-15
verifie: false
pages_estimees: 5
---

<!-- Quality Assurance Protocol | AGFA DR 100e / DR 14s Detector | NUC & MTF Protocol -->

# Procédure de contrôle qualité semestriel : Calibration NUC et Résolution MTF

### 1. Objectifs de la procédure
Cette procédure définit le protocole standardisé pour vérifier et calibrer la correction de non-uniformité (NUC - Non-Uniformity Correction) et mesurer la fonction de transfert de modulation (MTF) du détecteur numérique DR 14s couplé à l'unité mobile AGFA DR 100e, conformément à la norme internationale CEI 62220-1-1.

---

### 2. Dispositifs de mesure et conditions d'essai
- **Filtre cuivre normalisé :** Plaque de cuivre pur (Cu) de 21 mm ou 1,5 mm selon le faisceau d'essai RQA-5.
- **Mire de résolution spatiale :** Mire à fentes en plomb de type Huttner (0,5 à 5,0 paires de lignes par millimètre - lp/mm) ou arête biseautée certifiée pour calcul MTF par FFT.
- **Distance foyer-détecteur (SID) :** Rigoureusement fixée à 150 cm pour limiter les effets de pénombre focale.
- **Centrage :** Faisceau orthogonal au détecteur, collimateur entièrement ouvert pour couvrir la totalité du champ utile (35 × 43 cm).

---

### 3. Protocole d'acquisition et calibration NUC

#### Étape 3.1 : Préchauffage et conditionnement
1. Réalisez une série de 3 tirs de préchauffage du tube à rayons X à 70 kV / 10 mAs.
2. Laissez le détecteur DR 14s sous tension pendant 15 minutes minimum afin de stabiliser la température interne du capteur (cible nominale : 35 °C ± 2 °C).

#### Étape 3.2 : Acquisition des trames d'obscurité (Offset / Dark field)
1. Lancez l'utilitaire **NX Calibration Service Tool**.
2. Sélectionnez `Étalonnage Détecteur -> Dark Field`.
3. Le système acquiert automatiquement 8 trames consécutives sans aucun rayonnement X pour soustraire le bruit thermique du silicium amorphe.

#### Étape 3.3 : Acquisition des trames de faisceau plat (Gain / Flat field)
1. Placez le filtre de cuivre de 1,5 mm de Cu en sortie immédiate du collimateur.
2. Paramétrez le générateur à **70 kV** et ajustez les mAs pour obtenir un niveau de signal moyen de 30 000 ADU (Unités Analogiques-Numériques) au centre du détecteur.
3. Déclenchez 6 expositions successives avec un intervalle de 30 secondes entre chaque tir.
4. L'algorithme calcule la matrice de gain pixel par pixel et identifie les éventuels pixels défectueux isolés ou lignes ouvertes.

---

### 4. Critères d'acceptabilité métrologique

| Indicateur mesuré | Seuil de conformité nominal | Seuil d'alerte / Action requise |
| :--- | :--- | :--- |
| **Bruit de fond résiduel (Dark Noise)** | < 15 ADU | > 25 ADU : contrôler blindage et température |
| **Non-uniformité résiduelle (Flatness)** | Écart-type relatif < 1,5% | > 2,0% : renouveler la procédure NUC |
| **Pixels défectueux regroupés (Cluster)**| 0 cluster de plus de 4 pixels | Remplacement détecteur sous garantie |
| **MTF à 1,0 lp/mm** | ≥ 62% | < 55% : vérifier foyer ou scintillateur CsI |
| **MTF à 2,0 lp/mm** | ≥ 32% | < 28% : nettoyer surface optique |
| **MTF à 3,0 lp/mm** | ≥ 15% | < 12% : dégradation résolution |
| **DQE à 0 lp/mm (Efficacité quantique)** | ≥ 65% | < 58% : capteur usagé |

---

### 5. Archivage et signature
Le rapport numérique généré par le logiciel NX contenant la cartographie des gains et la courbe MTF doit être exporté sous format PDF et archivé dans le dossier technique biomédical de l'appareil pour présentation aux autorités de tutelle (ASN).

---
*Protocole Assurance Qualité MaintiDoc 2025.*
