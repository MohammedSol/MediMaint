---
id: MON-SCH-001
titre: "Schéma de la face avant — Mindray BeneVision N17 et N22"
reference: "SCH-BeneVision-FRONT-2025"
famille: moniteur_multiparametrique
modele: Mindray BeneVision N-Series
modeles_couverts: ["N17", "N22"]
type: schema_illustre
sous_type: face_avant_connecteurs
langue: fr
statut: synthetique
date_creation: 2025-01-01
verifie: false
pages_estimees: 5
---

<!-- Front Bezel & User Interface Architecture | Mindray BeneVision N17 / N22 -->

# Schéma illustré : Face avant et ergonomie des moniteurs BeneVision N17 & N22

### 1. Disposition de l'interface utilisateur sur la face avant (Modèle N17)

```
╔═════════════════════════════════════════════════════════════════════════════════════════╗
║ [1] VOYANT D'ALARME PHYSIQUE 360° (Rouge/Jaune/Cyan)          MINDRAY BeneVision N17   ║
╠═════════════════════════════════════════════════════════════════════════════════════════╣
║  ┌───────────────────────────────────────────────────────────────────────────────────┐  ║
║  │ [2] BANDEAU D'ÉTAT SUPÉRIEUR : Nom Patient | IPP | Lit 12A | Mode Adulte | 14:32  │  ║
║  ├───────────────────────────────────────────────────────────────────────────────────┤  ║
║  │                                             │ [3] PAVÉ FRÉQUENCE CARDIAQUE        │  ║
║  │ [7] TRACÉ ECG DÉRIVATION II (Vert)          │     FC : 75 bpm (Seuils: 50 - 120)  │  ║
║  │    /\    /\    /\                           │                                     │  ║
║  │ ──/  \──/  \──/  \───────────────────────── │                                     │  ║
║  ├─────────────────────────────────────────────┼─────────────────────────────────────┤  ║
║  │ [8] TRACÉ PLÉTHYSMOGRAPHIQUE SpO2 (Cyan)    │ [4] PAVÉ SATURATION EN O2           │  ║
║  │    _.~~._.~~._.~~._                         │     SpO2 : 98 %  (Seuil: 90%)       │  ║
║  ├─────────────────────────────────────────────┼─────────────────────────────────────┤  ║
║  │ [9] TRACÉ RESPIRATOIRE PAR IMPÉDANCE (Jaune)│ [5] PAVÉ PRESSION NON INVASIVE      │  ║
║  │    ~-._.-~~-._.-~                           │     PNI : 120 / 80 mmHg (PAM: 93)   │  ║
║  ├─────────────────────────────────────────────┼─────────────────────────────────────┤  ║
║  │ [10] TRACÉ PRESSION ARTÉRIELLE IBP (Rouge)  │ [6] PAVÉ TEMPÉRATURE & DÉBIT        │  ║
║  │    /\__/\__/\                               │     T1: 37.1 °C  | T2: 36.8 °C      │  ║
║  ├───────────────────────────────────────────────────────────────────────────────────┤  ║
║  │ [11] BARRE DE RACCOURCIS RAPIDES (QUICK KEYS TACTILES) :                          │  ║
║  │ [Alarm Setup] [Alarm Reset] [Audio Pause] [NIBP Start] [Zero IBP] [Freeze] [Menu] │  ║
║  └───────────────────────────────────────────────────────────────────────────────────┘  ║
╠═════════════════════════════════════════════════════════════════════════════════════════╣
║ [12] VOYANT SECTEUR (Vert)  |  [13] VOYANT BATTERIE (Orange/Vert)  |  [14] TOUCHE MARCHE║
╚═════════════════════════════════════════════════════════════════════════════════════════╝
```

---

### 2. Particularités du modèle N22 (Écran géant 21,5 pouces pivotable)
Le moniteur haut de gamme **BeneVision N22** reprend l'ensemble des éléments ci-dessus avec les ajouts majeurs suivants :
- **Dalle Full HD 21,5 pouces :** Affichage simultané jusqu'à 16 courbes en temps réel.
- **Capteur gyroscopique de rotation d'écran :** Basculement automatique en mode portrait pour les applications de cardiologie (tracé 12 dérivations déroulant en pleine page).
- **Double affichage indépendant :** Possibilité de raccorder un second écran tactile esclave N19/N22 via liaison HDMI/DisplayPort pour affichage déporté hors de la chambre d'isolement.

---

### 3. Nomenclature des voyants et commandes physiques de façade

| Réf. | Organe de contrôle | Technologie / Couleur | Comportement fonctionnel |
| :---: | :--- | :--- | :--- |
| **[1]** | Alarme lumineuse haute | Barre LED transversale 360° | Rouge clignotant (Haute), Jaune clignotant (Moyenne), Jaune fixe (Faible). |
| **[2]** | Bandeau d'état système | Zone tactile capacitive | Rappel d'admission patient, profil d'alarme actif et connectivité réseau. |
| **[3-6]**| Pavés numériques paramètres | Fenêtres tactiles dynamiques | Affiche la valeur instantanée ; un appui ouvre la configuration du capteur. |
| **[7-10]**| Tracés physiologiques | Rafraîchissement 25 / 50 mm/s| Formes d'onde continues synchronisées avec repère temporel. |
| **[11]**| Barre de touches rapides | Raccourcis configurables | Accès en un clic aux fonctions critiques du service d'hospitalisation. |
| **[12]**| Témoin présence secteur | LED verte sérigraphiée prise | Allumé fixe lorsque le moniteur est raccordé au réseau 230 V alternatif. |
| **[13]**| Témoin état batterie | LED bicolore verte / orange | Vert : batterie chargée ; Orange : charge en cours ; Rouge : panne batterie.|
| **[14]**| Interrupteur principal | Bouton poussoir à impulsion | Mise sous tension / passage en veille profonde assistée. |

---
*Spécification ergonomique et matérielle MaintiDoc 2025.*
