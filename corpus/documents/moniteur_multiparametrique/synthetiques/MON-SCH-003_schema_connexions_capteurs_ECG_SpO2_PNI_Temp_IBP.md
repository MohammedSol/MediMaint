---
id: MON-SCH-003
titre: "Schéma de connexion des capteurs — ECG, SpO2, PNI, Température, IBP — BeneVision N-Series"
reference: "SCH-BeneVision-CAPT-2025"
famille: moniteur_multiparametrique
modele: Mindray BeneVision N-Series
type: schema_illustre
sous_type: connexions_capteurs
langue: fr
statut: synthetique
date_creation: 2025-01-01
verifie: false
pages_estimees: 5
---

<!-- Sensor Cabling & Patient Interconnection Layout | Mindray BeneVision N-Series -->

# Schéma illustré : Câblage et raccordement des capteurs patients (BeneVision)

### 1. Schéma d'interconnexion globale du patient avec le moniteur

```
                                  ┌──────────────────────────────┐
                                  │      PATIENT SURVEILLÉ       │
                                  └──────────────┬───────────────┘
                                                 │
            ┌────────────────────┬───────────────┼───────────────┬───────────────────┐
            │                    │               │               │                   │
            ▼                    ▼               ▼               ▼                   ▼
    ┌───────────────┐    ┌───────────────┐ ┌───────────┐ ┌───────────────┐   ┌───────────────┐
    │ ÉLECTRODES    │    │ CAPTEUR SpO2  │ │ BRASSARD  │ │ SONDE TEMP.   │   │ TRANSDUCTEUR  │
    │ ECG 5 BRINS   │    │ Pince Doigt   │ │ PNI ADULTE│ │ Œsophagienne  │   │ IBP ARTÉRIEL  │
    └───────┬───────┘    └───────┬───────┘ └─────┬─────┘ └───────┬───────┘   └───────┬───────┘
            │                    │               │               │                   │
            │ Cordon 5 fils      │ Câble blindé  │ Tuyau souple  │ Câble thermistance│ Ligne de raccord
            ▼                    ▼               ▼               ▼                   ▼
    ┌───────────────┐    ┌───────────────┐ ┌───────────┐ ┌───────────────┐   ┌───────────────┐
    │ PORT ECG 12 PIN│   │ PORT SpO2 7 PIN││ RACCORD PNI││ PRISES JACK T1 │  │ PORTS IBP 1/2 │
    │ (Repère Vert) │    │ (Repère Bleu) │ │ (Baïonnette)│ (Mini-Jack)   │   │ (Connecteur 6P│
    └───────┬───────┘    └───────┬───────┘ └─────┬─────┘ └───────┬───────┘   └───────┬───────┘
            │                    │               │               │                   │
            └────────────────────┴───────┬───────┴───────────────┴───────────────────┘
                                         ▼
                      ┌──────────────────────────────────────┐
                      │ MODULE MULTIPARAMÉTRIQUE MPM MINDRAY │
                      └──────────────────────────────────────┘
```

---

### 2. Code couleur et positionnement des électrodes ECG (Norme Européenne IEC)

| Électrode | Marquage IEC (EU) | Marquage AHA (USA) | Couleur IEC | Position anatomique recommandée |
| :---: | :---: | :---: | :---: | :--- |
| **R** | R | RA | **Rouge** | Sous la clavicule droite, près de l'épaule droite. |
| **L** | L | LA | **Jaune** | Sous la clavicule gauche, près de l'épaule gauche. |
| **F** | F | LL | **Vert** | Flanc abdominal inférieur gauche ou crête iliaque gauche. |
| **N** | N | RL | **Noir** | Flanc abdominal inférieur droit (électrode de référence/terre). |
| **C** | C | V | **Blanc** | Précordiale sur le thorax (4e espace intercostal droit pour C1/V1). |

---

### 3. Tableau des connecteurs rapides du module MPM

| Port capteur | Type d'embase physique | Détrompage mécanique | Consigne de manipulation |
| :--- | :--- | :--- | :--- |
| **Entrée ECG** | Connecteur circulaire 12 contacts étanche | Repère rouge vers le haut | Aligner la flèche du câble avec le point rouge de l'embase. |
| **Entrée SpO2** | Connecteur rectangulaire verrouillable 7 contacts| Verrou à bascule plastique | Enfoncer jusqu'au clic ; pincer les clips latéraux pour extraire. |
| **Prise PNI** | Raccord rapide quart de tour baïonnette métal | Bague de verrouillage chromée | Pousser et tourner d'un quart de tour à droite pour étanchéité. |
| **Entrées Temp** | 2 embases Jack standardisées 6,35 mm | Sans détrompeur | Brancher à fond ; ne pas tirer sur le fil fin pour débrancher. |
| **Entrées IBP** | Embases circulaires 6 contacts push-pull | Encoche axiale | Tirer sur le collier métallique du câble pour déverrouiller. |

---
*Fiche de câblage clinique MaintiDoc 2025.*
