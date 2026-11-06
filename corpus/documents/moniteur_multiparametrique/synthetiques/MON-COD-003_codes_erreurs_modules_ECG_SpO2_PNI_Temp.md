---
id: MON-COD-003
titre: "Table des codes d'erreur modules — ECG, SpO2, PNI, Température — BeneVision N-Series"
reference: "COD-BeneVision-MOD-2025"
famille: moniteur_multiparametrique
modele: Mindray BeneVision N-Series
type: table_codes_erreur
sous_type: modules_parametres
langue: fr
statut: synthetique
date_creation: 2025-01-01
verifie: false
pages_estimees: 6
---

<!-- Module Parameter Low-Level Codes | Mindray BeneVision Subsystems -->

# Codes d'erreur bas niveau par module physiologique (BeneVision N-Series)

Ce document répertorie les codes de diagnostic interne générés par les processeurs numériques de signaux (DSP) propres à chaque chaîne de mesure modulaire des moniteurs BeneVision.

---

### 1. Module ECG et Respiration par impédance (Sous-système MPM-ECG)

| Code interne | Libellé hexadécimal | Cause technique hardware | Action corrective préconisée |
| :---: | :--- | :--- | :--- |
| **ECG-001** | `0x1001_LEAD_OFF_RA` | Électrode Bras Droit (RA) décollée ou impédance contact > 100 kΩ. | Remplacer l'électrode RA et préparer la peau. |
| **ECG-002** | `0x1002_LEAD_OFF_LA` | Électrode Bras Gauche (LA) décollée. | Remplacer l'électrode LA. |
| **ECG-003** | `0x1003_LEAD_OFF_LL` | Électrode Jambe Gauche (LL) décollée. | Remplacer l'électrode LL. |
| **ECG-004** | `0x1004_LEAD_OFF_V` | Une ou plusieurs électrodes précordiales (V1-V6) décollées. | Vérifier le faisceau 5 ou 12 brins. |
| **ECG-005** | `0x1008_SATURATION` | Saturation de l'amplificateur différentiel d'entrée (> 5 mV). | Vérifier absence de bistouri électrique ou problème de masse. |
| **ECG-006** | `0x1010_NOISE_50HZ` | Parasitage secteur 50 Hz excessif sur le tracé. | Activer le filtre Notch 50 Hz dans le menu ECG Réglages. |
| **ECG-007** | `0x1020_PACE_MISSED` | Impulsions de stimulateur cardiaque indétectables. | Activer le mode Stimulateur (Paced = Oui) et baisser seuil. |
| **ECG-008** | `0x1040_DSP_FAIL` | Échec de communication avec le microprocesseur de détection arythmie. | Réinitialiser le module MPM en l'éjectant du rack. |

---

### 2. Module SpO2 (Technologie Masimo SET® / Mindray SpO2)

| Code interne | Libellé hexadécimal | Cause technique hardware | Action corrective préconisée |
| :---: | :--- | :--- | :--- |
| **SPO-001** | `0x2001_NO_SENSOR` | Pas de capteur optique détecté sur le port SpO2. | Brancher un capteur compatible Masimo LNCS ou Mindray 7 pins. |
| **SPO-002** | `0x2002_BAD_SENSOR` | Diode rouge 660 nm ou infrarouge 940 nm coupée. | Remplacer le capteur optique défectueux. |
| **SPO-003** | `0x2004_LOW_PERF` | Indice de perfusion (PI) mesuré inférieur à 0,05%. | Réchauffer l'extrémité du membre ou poser sonde auriculaire. |
| **SPO-004** | `0x2008_PULSE_LOST` | Signal pulsatile trop faible pour discriminer la FC. | Repositionner le capteur sur un autre site anatomique. |
| **SPO-005** | `0x2010_CABLE_ERR` | Puce d'identification du câble adaptateur corrompue. | Remplacer le câble intermédiaire d'extension SpO2. |
| **SPO-006** | `0x2020_INTERFERENCE`| Lumière parasite externe saturant le photorécepteur. | Protéger le site de mesure avec un pansement opaque. |

---

### 3. Module Pression Non Invasive (PNI / NIBP Pneumatique)

| Code interne | Libellé hexadécimal | Cause technique hardware | Action corrective préconisée |
| :---: | :--- | :--- | :--- |
| **PNI-001** | `0x3001_AIR_LEAK` | Chute de pression supérieure à 15 mmHg en phase de gonflage. | Vérifier la tubulure, les connecteurs rapides et le brassard. |
| **PNI-002** | `0x3002_OVER_PRESS`| Pression instantanée mesurée supérieure à 300 mmHg. | Électrovanne de sécurité ouverte d'urgence ; vérifier valve. |
| **PNI-003** | `0x3004_TIMEOUT` | Durée totale de la mesure excédant 120 secondes (adulte). | Répéter la mesure après 2 min de repos veino-capillaire. |
| **PNI-004** | `0x3008_CUFF_LOOSE` | Brassard trop grand ou insuffisamment serré autour du bras. | Remplacer par un brassard de circonférence adaptée. |
| **PNI-005** | `0x3010_PUMP_FAIL` | Pompe électrique à membrane bloquée ou débit insuffisant. | Contrôler la tension d'alimentation 12 V de la pompe interne. |
| **PNI-006** | `0x3020_CALIB_REQ` | Décalage du point zéro du capteur piézorésistif (> 5 mmHg). | Exécuter la procédure de calibration d'usine (MON-PROC-002). |

---

### 4. Module Température et Débit Cardiaque (Voies T1, T2, CCO)

| Code interne | Libellé hexadécimal | Cause technique hardware | Action corrective préconisée |
| :---: | :--- | :--- | :--- |
| **TMP-001** | `0x4001_PROBE_OPEN` | Sonde thermistance YSI 400 coupée (résistance infinie). | Remplacer la sonde thermique réutilisable ou jetable. |
| **TMP-002** | `0x4002_PROBE_SHORT`| Court-circuit interne dans la tige de la sonde thermique. | Remplacer la sonde ; ne pas immerger la fiche de raccordement. |
| **TMP-003** | `0x4004_OUT_OF_RANGE`| Température mesurée < 0,0 °C ou > 50,0 °C. | Vérifier que la sonde est appliquée sur un site physiologique. |
| **TMP-004** | `0x4008_CAL_DRIFT` | Dérive de la source de courant de référence interne du canal.| Retour atelier biomédical pour ré-étalonnage de la carte mère. |

---
*Table de dépannage avancée des modules Mindray MaintiDoc 2025.*
