---
id: MON-PHO-002
titre: "Description photographique — Connecteurs arrière Mindray BeneVision N17"
reference: "PHO-BeneVision-N17-CONN-2025"
famille: moniteur_multiparametrique
modele: Mindray BeneVision N-Series
type: document_photographie
contexte: "Vérification connectivité réseau — intégration DICOM"
langue: fr
statut: synthetique
date_creation: 2025-02-15
verifie: false
pages_estimees: 2
---

<!-- Visual Inspection & Photographic Analysis | Mindray BeneVision N17 Rear Panel -->

# Fiche descriptive d'inspection photographique : Connecteurs arrière (BeneVision N17)

### Contexte opérationnel de la prise de vue
- **Établissement :** Hôpital d'Instruction des Armées — Service de Surveillance Continue.
- **Équipement inspecté :** Face arrière du moniteur Mindray BeneVision N17 monté sur bras articulé mural.
- **Date :** 15/02/2025 — Recette technique du raccordement au réseau eGateway.

---

### Analyse détaillée du cliché [Photo Ref : IMG_20250215_N17_REAR_PORTS.JPG]

```
┌────────────────────────────────────────────────────────────────────────┐
│  CLICHÉ : Vue plongeante sur la baie de connectique arrière du N17     │
│                                                                        │
│   [Port LAN RJ45] : Câble bleu Cat 6 enclenché                         │
│                     - LED Verte (Liaison 1 Gbps) : ALLUMÉE FIXE        │
│                     - LED Jaune (Activité données) : CLIGNOTANTE RAPIDE │
│                                                                        │
│   [Port SMR / Bus] : Câble ombilical noir vers rack multiparamètres    │
│                      vis moletée de verrouillage serrée à la main.     │
│                                                                        │
│   [Prise Secteur C14] : Cordon secteur 230V avec étrier métallique de │
│                         retenue anti-arrachement verrouillé.           │
│                                                                        │
│   [Borne Terre] : Câble vert/jaune relié à la barre équipotentielle.   │
└────────────────────────────────────────────────────────────────────────┘
```

1. **Port réseau local Ethernet RJ45 :**
   - Connecteur RJ45 blindé correctement clipsé.
   - Témoin vert allumé fixe confirmant la négociation de vitesse à 1 000 Mbps avec le commutateur Cisco du service.
   - Témoin jaune clignotant confirmant le trafic bidirectionnel continu des trames HL7 vers la passerelle eGateway.
2. **Sécurisation de l'alimentation secteur :**
   - Présence indispensable du cavalier métallique en fil d'acier rabattu sur l'embase du cordon d'alimentation pour empêcher tout débranchement accidentel lors de l'orientation du bras mural.
3. **Mise à la terre équipotentielle :**
   - Écrou moleté de masse bien serré, tresse de masse sans effilochage raccordée au rail support mural.

**Validation d'installation :** Câblage réseau et liaisons de sécurité conformes aux règles de l'art biomédical.

---
*Rapport d'inspection photographique MaintiDoc 2025.*
