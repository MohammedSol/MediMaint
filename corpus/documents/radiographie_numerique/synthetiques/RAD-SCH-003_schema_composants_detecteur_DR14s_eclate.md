---
id: RAD-SCH-003
titre: "Schéma en vue éclatée — Composants internes du détecteur AGFA DR 14s"
reference: "SCH-DR14s-ECLATE-2025"
famille: radiographie_numerique
modele: AGFA DR 100e
composant: "Détecteur AGFA DR 14s"
type: schema_illustre
sous_type: vue_eclatee_composants
langue: fr
statut: synthetique
date_creation: 2025-01-01
verifie: false
pages_estimees: 4
---

<!-- Exploded View Mechanical Schematics | AGFA Dura-line DR 14s Wireless Panel -->

# Schéma illustré : Vue éclatée et sous-ensembles du capteur DR 14s

### 1. Vue éclatée des couches constitutives du détecteur

```
    [1] COUVERCLE DE PROTECTION AVANT (Fibre de carbone absorbante RX < 0.8 mm Al)
    ────────────────────────────────────────────────────────────────────────────
                                      │
                                      ▼
    [2] SCINTILLATEUR CsI:Tl (Iodure de Césium dopé Thallium - structure aiguillée 600 µm)
    ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░
                                      │
                                      ▼
    [3] MATRICE DE TRANSISTORS EN COUCHES MINCES (a-Si TFT + Photodiodes PIN)
    ┌──────────────────────────────────────────────────────────────────────────┐
    │ 2810 × 2970 pixels utiles | Pas de pixel : 148 µm | Zone sensible 35×43cm│
    └──────────────────────────────────────────────────────────────────────────┘
                                      │
                                      ▼
    [4] BLINDAGE INTERMÉDIAIRE EN FEUILLE DE PLOMB (Écran arrière Pb 0.2 mm)
    ▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒
                                      │
                                      ▼
    [5] CARTE ÉLECTRONIQUE DE NUMÉRISATION RAPIDE & FPGA (Canaux ADC 16 bits)
    ┌──────────────────────┬───────────────────────────┬───────────────────────┐
    │ Amplificateurs ASIC  │ Microprocesseur FPGA Xilinx│ Transceiver WiFi 5GHz │
    └──────────────────────┴───────────────────────────┴───────────────────────┘
                                      │
                                      ▼
    [6] COMPARTIMENT PACK BATTERIE LITHIUM-ION EXTRACTIBLE (11.1V / 4200 mAh)
    [==================== BATTERIE LI-ION AGF-DR14S-BAT ======================]
                                      │
                                      ▼
    [7] CHÂSSIS ARRIÈRE MONOBLOC EN ALLIAGE DE MAGNÉSIUM (Joint d'étanchéité IP54)
    ════════════════════════════════════════════════════════════════════════════
```

---

### 2. Rôle et spécifications techniques des composants

| Réf. | Sous-ensemble constitutif | Matériau / Technologie | Propriété clé / Rôle fonctionnel |
| :---: | :--- | :--- | :--- |
| **[1]** | Face d'entrée faisceau | Résine polymère & fibre de carbone | Transparence maximale aux rayons X (atténuation < 5% à 80 kV). |
| **[2]** | Scintillateur de conversion | Cristaux CsI en micro-colonnes | Convertit les photons X incidents en photons lumineux verts (540 nm). |
| **[3]** | Matrice de photodétection | Silicium amorphe hydrogéné (a-Si)| Transforme la lumière émise en charges électriques proportionnelles. |
| **[4]** | Écran plombé arrière | Feuille laminée Pb pur 99.9% | Empêche le rayonnement rétrodiffusé de parasiter les circuits logiques. |
| **[5]** | Carte de conversion A/N | PCB multicouche HDI 12 couches | Échantillonnage du signal sur 16 bits (65 536 niveaux de gris). |
| **[6]** | Accumulateur d'énergie | 3 cellules Li-ion 18650 en série | Assure une autonomie autonome jusqu'à 4 heures de travail continu. |
| **[7]** | Coque arrière et cadre | Alliage de magnésium usiné CNC | Résistance mécanique aux charges réparties jusqu'à 150 kg (patient). |

---
*Fiche technique descriptive de capteur MaintiDoc 2025.*
