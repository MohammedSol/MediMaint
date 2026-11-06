---
id: RAD-SCH-001
titre: "Schéma du panneau de commandes du générateur — AGFA DR 100e"
reference: "SCH-DR100e-GEN-2025"
famille: radiographie_numerique
modele: AGFA DR 100e
type: schema_illustre
sous_type: panneau_commandes
langue: fr
statut: synthetique
date_creation: 2025-01-01
verifie: false
pages_estimees: 4
---

<!-- Technical Diagram | AGFA DR 100e Generator Console Layout -->

# Schéma illustré : Pupitre de commandes du générateur AGFA DR 100e

### 1. Représentation schématique du panneau de contrôle

```
╔════════════════════════════════════════════════════════════════════════════════════════╗
║                       AGFA DR 100e — CONSOLE GÉNÉRATEUR RX 32 kW                       ║
╠════════════════════════════════════════════╦═══════════════════════════════════════════╣
║    [A] AFFICHAGE PARAMÈTRES EXPOSITION     ║        [B] VOYANTS D'ÉTAT SYSTÈME         ║
║  ┌──────────────────┐  ┌────────────────┐  ║  ┌─────────────────────────────────────┐  ║
║  │   [1] 100 kV     │  │  [2] 12.5 mAs  │  ║  │  (5) ● PRÊT (READY)       - VERT    │  ║
║  └──────────────────┘  └────────────────┘  ║  │  (6) ● EXPOSITION (X-RAY) - ORANGE  │  ║
║    Tension Anodique      Charge Tube       ║  │  (7) ● ALARME (FAULT)     - ROUGE   │  ║
║                                            ║  │  (8) ● ATTENTE THERMIQUE  - JAUNE   │  ║
╠════════════════════════════════════════════╣  └─────────────────────────────────────┘  ║
║    [C] COMMANDES DE RÉGLAGE MANUEL         ╠═══════════════════════════════════════════╣
║  ┌───────────────┐   ┌──────────────────┐  ║    [D] SÉLECTION DES FOYERS & SÉCURITÉ    ║
║  │ [3]  [▲]  [▼] │   │ [4]   [▲]   [▼]  │  ║  ┌─────────────────────────────────────┐  ║
║  │   kV Pas 1kV  │   │   mAs Pas 12.5%  │  ║  │  (9)  [•] PETIT FOYER  (0.6 mm)    │  ║
║  └───────────────┘   └──────────────────┘  ║  │  (10) [•] GRAND FOYER  (1.3 mm)    │  ║
╠════════════════════════════════════════════╣  │  (11) [⏻] ARRÊT D'URGENCE / DISJ.  │  ║
║    [E] CONNECTEUR DÉCLENCHEUR À MAIN       ║  └─────────────────────────────────────┘  ║
║  ┌──────────────────────────────────────┐  ╠═══════════════════════════════════════════╣
║  │ [12] PRISE JACK VERROUILLABLE        │  ║  (13) PRISE TÉLÉCOMMANDE IR (FAÇADE)     ║
║  │      Poire d'exposition à 2 crans    │  ║       Capteur infrarouge grand angle      ║
║  └──────────────────────────────────────┘  ║       Portée utile : 8 mètres             ║
╚════════════════════════════════════════════╩═══════════════════════════════════════════╝
```

---

### 2. Légende technique et fonctions opérationnelles

| Repère | Organe de commande / Signal | Plage de fonctionnement | Fonction technique détaillée |
| :---: | :--- | :--- | :--- |
| **(1)** | Afficheur digital des kV | 40 à 125 kV (pas de 1 kV) | Affiche la haute tension de crête sélectionnée pour le tir. |
| **(2)** | Afficheur digital des mAs | 0.1 à 110 mAs (ext. 220 mAs)| Affiche le produit courant × temps calculé pour l'exposition. |
| **(3)** | Touches d'ajustement kV | Pression incrémentale / rapide | Permet la modification manuelle de la dureté du faisceau. |
| **(4)** | Touches d'ajustement mAs | Échelle normalisée Renard 12% | Ajuste la quantité totale de photons de rayonnement émis. |
| **(5)** | Voyant vert "PRÊT" | Témoin fixe | Confirme la vitesse de rotation de l'anode (3 000 rpm) et filament chaud. |
| **(6)** | Voyant orange "EXPOSITION" | Témoin fixe + signal sonore | Signale la présence active de haute tension et l'émission RX. |
| **(7)** | Voyant rouge "ALARME" | Clignotant ou fixe | Signale un défaut générateur (voir table RAD-COD-001). |
| **(8)** | Voyant jaune "THERMIQUE" | Fixe | Alerte charge thermique monobloc > 80% HU ; tirs bloqués temporairement. |
| **(9)** | Bouton sélecteur Petit Foyer | Foyer optique 0.6 mm / 16 kW | Sélectionné pour les extrémités et la pédiatrie haute netteté. |
| **(10)**| Bouton sélecteur Grand Foyer | Foyer optique 1.3 mm / 32 kW | Sélectionné pour le thorax adulte, le rachis et le bassin. |
| **(11)**| Disjoncteur / Arrêt d'urgence| Calibre 20 A instantané | Coupe immédiatement l'alimentation générale secteur et condensateurs. |
| **(12)**| Embase poire déclenchement | Connecteur étanche 4 pôles | Raccordement du câble spiralé de la commande d'exposition manuelle. |
| **(13)**| Capteur récepteur IR | Angle de réception 120° | Réceptionne les ordres de tir de la télécommande infrarouge déportée. |

---
*Document d'architecture matérielle MaintiDoc 2025.*
