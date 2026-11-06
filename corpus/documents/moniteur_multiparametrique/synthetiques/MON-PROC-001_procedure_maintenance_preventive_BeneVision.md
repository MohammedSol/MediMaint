---
id: MON-PROC-001
titre: "Procédure de maintenance préventive — Mindray BeneVision N-Series"
reference: "MP-BeneVision-TRIM-2025"
famille: moniteur_multiparametrique
modele: Mindray BeneVision N-Series
fabricant: Mindray
type: procedure_maintenance
periodicite: trimestrielle
duree_estimee: "2h30"
qualification_requise: "Technicien biomédical"
langue: fr
statut: synthetique
date_creation: 2025-01-01
verifie: false
pages_estimees: 6
---

<!-- Preventive Maintenance Guide | Mindray BeneVision N-Series Patient Monitors -->

# Procédure de maintenance préventive trimestrielle : Mindray BeneVision N-Series

### 1. Champ d'application
La présente procédure s'applique aux moniteurs patients multiparamétriques de soins critiques Mindray BeneVision N12, N15, N17, N19 et N22 ainsi qu'à leurs modules satellites de mesure multiparamétrique MPM.

---

### 2. Équipements de métrologie et simulateurs patients requis
- **Simulateur multiparamétrique de patient :** Fluke Biomedical ProSim 8 ou Rigel Uni-Sim (génération signaux ECG, SpO2, PNI, Température, IBP, Respiration).
- **Testeur de sécurité électrique médical :** Dédié appareils classe I type CF (Fluke ESA620 ou Bender).
- **Manomètre étalon numérique :** Gamme 0-350 mmHg, précision ±0,5 mmHg, raccordé COFRAC.

---

### 3. Protocole d'essais et relevé métrologique trimestriel

| N° | Point de contrôle | Spécification Mindray | Valeur mesurée | Statut |
| :---: | :--- | :--- | :--- | :---: |
| **01** | État mécanique du boîtier et de la dalle | Absence de fêle, dalle tactile capacitive réactive | Examen visuel | ☐ OK ☐ NOK |
| **02** | Test d'impédance de terre (PE) | R_pe ≤ 0,10 Ω avec cordon secteur détachable | Mesuré : _____ Ω | ☐ OK ☐ NOK |
| **03** | Courant de fuite châssis (Touch Current) | I_fuite < 100 µA en condition normale (NC) | Mesuré : _____ µA | ☐ OK ☐ NOK |
| **04** | Courant de fuite patient type CF (ECG/IBP)| I_patient < 10 µA (NC), < 50 µA (SFC défaut unique)| Mesuré : _____ µA | ☐ OK ☐ NOK |
| **05** | Exactitude fréquence cardiaque ECG (ProSim)| 60 bpm et 120 bpm (tolérance ±1 bpm) | Relevé : _____ bpm | ☐ OK ☐ NOK |
| **06** | Test détection arythmie (Asystolie) | Déclenchement alarme haute rouge sous ≤ 4 s | Temps : _____ s | ☐ OK ☐ NOK |
| **07** | Saturation SpO2 Masimo / Mindray (70%) | Mesure affichée 70% ± 2% | Relevé : _____ % | ☐ OK ☐ NOK |
| **08** | Saturation SpO2 Masimo / Mindray (95%) | Mesure affichée 95% ± 2% | Relevé : _____ % | ☐ OK ☐ NOK |
| **09** | PNI : Fuite pneumatique du circuit étanche | Perte de pression < 6 mmHg en 60 s à 250 mmHg | Fuite : _____ mmHg | ☐ OK ☐ NOK |
| **10** | PNI : Exactitude de mesure statique (150) | 150 mmHg ± 3 mmHg contre manomètre étalon | Étalon : _____ mmHg | ☐ OK ☐ NOK |
| **11** | Pression invasive IBP : Linéarité du zéro | Zéro stable à 0 mmHg ± 1 mmHg, 100 mmHg ± 1 | Mesure : _____ mmHg | ☐ OK ☐ NOK |
| **12** | Température voie T1 / T2 à 37,0 °C | Valeur lue 37,0 °C ± 0,1 °C | Relevé : _____ °C | ☐ OK ☐ NOK |
| **13** | Avertisseurs d'alarme sonore et visuelle | Tonalité haute audible à 65 dBA, voyant LED rouge | Test auditif/visuel | ☐ OK ☐ NOK |
| **14** | Test autonomie batterie interne Li-ion | Fonctionnement sans secteur > 60 min | Durée : _____ min | ☐ OK ☐ NOK |
| **15** | Connectivité réseau eGateway et CMS | Ping central de surveillance < 10 ms, synchro NTP | Connecté | ☐ OK ☐ NOK |

---

### 4. Critères de remise en service
L'appareil est déclaré conforme pour un nouveau trimestre de surveillance clinique si l'ensemble des 15 items est validé sans réserve. L'étiquette de contrôle périodique datée est apposée sur le flanc du moniteur.

---
*Rapport de maintenance préventive MaintiDoc 2025.*
