---
id: MON-SCH-002
titre: "Schéma des modules et baies d'extension — BeneVision N-Series"
reference: "SCH-BeneVision-MOD-2025"
famille: moniteur_multiparametrique
modele: Mindray BeneVision N-Series
type: schema_illustre
sous_type: modules_extension
langue: fr
statut: synthetique
date_creation: 2025-01-01
verifie: false
pages_estimees: 4
---

<!-- Modular Architecture Layout | Mindray BeneVision SMR & MPM Modules -->

# Schéma illustré : Baies d'extension et modules satellites (BeneVision N-Series)

### 1. Architecture modulaire et rack d'extension déporté (SMR)

```
┌────────────────────────────────────────────────────────────────────────────────────────┐
│              RACK DE MODULES SATELLITE DÉPORTÉ (SATELLITE MODULE RACK - SMR)           │
├───────────────────┬───────────────────┬───────────────────┬────────────────────────────┤
│   SLOT N°1        │   SLOT N°2        │   SLOT N°3        │   SLOT N°4                 │
│ ┌───────────────┐ │ ┌───────────────┐ │ ┌───────────────┐ │ ┌────────────────────────┐ │
│ │ MODULE MPM    │ │ │ MODULE IBP    │ │ │ MODULE EtCO2  │ │ │ MODULE BIS / NMT       │ │
│ │ MULTI-PARAM   │ │ │ PRESSION ART. │ │ │ CAPNOGRAPHIE  │ │ │ PROFONDEUR ANESTHÉSIE  │ │
│ │               │ │ │               │ │ │               │ │ │                        │ │
│ │ (o) ECG 12D   │ │ │ (o) Art IBP1  │ │ │ [~] Piège à   │ │ │ (o) Capteur EEG BIS    │ │
│ │ (o) SpO2 Mas. │ │ │ (o) PVC IBP2  │ │ │     eau Dryline││ │ (o) Stimulateur NMT    │ │
│ │ [=] Port PNI  │ │ │               │ │ │               │ │ │                        │ │
│ │ (o) Temp 1/2  │ │ │               │ │ │               │ │ │                        │ │
│ │               │ │ │               │ │ │               │ │ │                        │ │
│ │ [Déverrouil.] │ │ │ [Déverrouil.] │ │ │ [Déverrouil.] │ │ │ [Déverrouillage]       │ │
│ └───────────────┘ │ └───────────────┘ │ └───────────────┘ │ └────────────────────────┘ │
├───────────────────┴───────────────────┴───────────────────┴────────────────────────────┤
│ [LIAISON RACK-MONITEUR] Câble ombilical blindé haute vitesse (Bus CAN + Alimentation)  │
└────────────────────────────────────────────────────────────────────────────────────────┘
```

---

### 2. Guide d'insertion et verrouillage mécanique d'un module
1. **Alignement :** Présentez le module dans les rails de guidage supérieurs et inférieurs de la baie du moniteur ou du rack SMR.
2. **Engagement :** Poussez le module horizontalement sans forcer jusqu'au contact avec le connecteur fond de panier (Backplane).
3. **Verrouillage :** Enfoncez le module jusqu'à entendre le clic audible du loquet à ressort inférieur.
4. **Reconnaissance :** Le moniteur émet une tonalité courte d'accueil et fait apparaître les paramètres correspondants sur l'écran en moins de **2 secondes** (Hot-Swap supporté à chaud).
5. **Extraction :** Pour retirer un module, abaissez fermement le levier de déverrouillage situé sous la façade du module et tirez vers vous.

---

### 3. Matrice de compatibilité des modules BeneVision

| Module | Référence Mindray | Paramètres mesurés | Usage clinique principal |
| :--- | :---: | :--- | :--- |
| **Module MPM standard** | MPM-01 | ECG 3/5/6/12D, SpO2, PNI, Temp 2 voies, Resp | Standard pour tout lit de surveillance. |
| **Module SpO2 Masimo** | M-SPO2-MAS | SpO2 Masimo SET®, SpCO, SpMet, PI | Réanimation adulte / néonatale sévère. |
| **Module IBP double voie**| M-IBP2 | Pression artérielle invasive, PVC, PAP | Choc septique, chirurgie lourde. |
| **Module Capnographie** | M-CO2-DL | EtCO2 en flux latéral (Sidestream) avec Dryline| Patient ventilé ou sous sédation profonde. |
| **Module Débit CCO/SvO2**| M-CCO-EDW | Débit continu via cathéter Edwards Swan-Ganz | Réanimation chirurgicale cardiaque. |
| **Module Curarisation** | M-NMT | Monitorage de la curarisation (Train de Quatre)| Bloc opératoire / Anesthésie. |

---
*Spécification d'architecture modulaire MaintiDoc 2025.*
