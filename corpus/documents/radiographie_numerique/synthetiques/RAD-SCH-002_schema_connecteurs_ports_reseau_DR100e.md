---
id: RAD-SCH-002
titre: "Schéma des connecteurs et ports réseau — AGFA DR 100e + NX Workstation"
reference: "SCH-DR100e-CONN-2025"
famille: radiographie_numerique
modele: AGFA DR 100e
type: schema_illustre
sous_type: connecteurs_reseau
langue: fr
statut: synthetique
date_creation: 2025-01-01
verifie: false
pages_estimees: 3
---

<!-- Interfacing & Connector Map | AGFA DR 100e / NX Workstation Base -->

# Schéma illustré : Connectique et interfaces réseau (DR 100e & Poste NX)

### 1. Panneau de connectique arrière du poste de travail NX

```
┌────────────────────────────────────────────────────────────────────────────────────────┐
│                      PANNEAU D'INTERFACES ARRIÈRE — POSTE NX PC TOUT-EN-UN             │
├────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                        │
│   [1] ETHERNET RJ45     [2] USB 3.0    [3] USB 2.0     [4] SORTIE VIDÉO   [5] ALIM 24V │
│   ┌───────────────┐     ┌─────────┐    ┌─────────┐     ┌──────────────┐   ┌─────────┐  │
│   │ █ █ █ █ █ █ █ │     │ ══ USB1 ══   │ ══ USB3 ══    │  (● ● ● ● ●) │   │ (O) (O) │  │
│   │ 1000BASE-T    │     │ ══ USB2 ══   │ ══ USB4 ══    │    Display   │   │  +24VDC │  │
│   │ Réseau PACS   │     │ Périphériques│ Clavier/Souris│     Port     │   │ Entrée  │  │
│   └───────────────┘     └─────────┘    └─────────┘     └──────────────┘   └─────────┘  │
│                                                                                        │
│   [6] BUS CAN GÉNÉRATEUR     [7] INTERFACE DOCKING DR 14s    [8] BORNE ÉQUIPOTENTIELLE │
│   ┌─────────────────────┐    ┌──────────────────────────┐    ┌───────────────────────┐ │
│   │ DB9 Blindé          │    │ Connecteur ruban multi-pt│    │ Tige filetée M6       │ │
│   │ Contrôle Générateur │    │ Liaison filaire tether   │    │ Masse de sécurité     │ │
│   └─────────────────────┘    └──────────────────────────┘    └───────────────────────┘ │
└────────────────────────────────────────────────────────────────────────────────────────┘
```

---

### 2. Architecture des flux réseau et liaisons point à point

```
┌─────────────────────────┐               ┌────────────────────────┐
│  DÉTECTEUR DR 14s CsI   │  WiFi 5 GHz   │   POSTE DE TRAVAIL NX   │
│  Liaison Ad-hoc WPA2-PSK├══════════════>│   IP: 192.168.10.100   │
└─────────────────────────┘ (Image brute) └───────────┬────────────┘
                                                      │
                                                      │ Câble Ethernet RJ45
                                                      │ Cat 6 (8 mètres)
                                                      ▼
                                          ┌────────────────────────┐
                                          │   COMMUTATEUR RÉSEAU   │
                                          │   HÔPITAL (VLAN RADIO) │
                                          └───────┬────────┬───────┘
                                                  │        │
                   Protocole DICOM C-STORE        │        │ Protocole DICOM C-FIND
                   (Port TCP 104 / TLS)           │        │ (Modality Worklist MWL)
                                                  ▼        ▼
                                       ┌────────────┐    ┌────────────┐
                                       │ ARCHIVAGE  │    │  SERVEUR   │
                                       │ PACS CHU   │    │  SIR / RIS │
                                       └────────────┘    └────────────┘
```

---

### 3. Spécifications techniques des ports

| Réf. | Interface | Type de connecteur | Protocole / Signal | Rôle fonctionnel |
| :---: | :--- | :--- | :--- | :--- |
| **[1]** | Réseau hospitalier | RJ45 femelle blindé Cat 6 | IEEE 802.3ab (1 Gbps) | Communication DICOM 3.0 avec PACS et SIR. |
| **[2]** | Ports USB rapides | 2× USB 3.0 Type A bleu | 5 Gbps / 5V 900 mA | Export sécurisé des examens et logs vers support amovible. |
| **[3]** | Ports USB périph. | 2× USB 2.0 Type A noir | 480 Mbps | Raccordement du lecteur code-barres et clavier virtuel. |
| **[4]** | Sortie Moniteur | DisplayPort 1.2 femelle | Numérique 1920×1080 | Raccordement éventuel d'un écran de rappel déporté. |
| **[5]** | Alimentation DC | Embase Molex Mini-Fit 2 broches | 24 V DC régulé (8 A) | Alimentation générale délivrée par le convertisseur châssis. |
| **[6]** | Bus CAN interne | D-Sub 9 broches mâle blindé | CAN Bus 2.0B (500 kbps)| Ordres de commande kV/mAs et retours de télémétrie du générateur. |
| **[7]** | Port Docking DR 14s| Fiche propriétaire multi-contacts| Ethernet 100 Mbps + 12V| Chargement de la batterie et appairage filaire sécurisé. |
| **[8]** | Prise équipotentielle| Borne laiton M6 normalisée DIN | Terre de protection | Égalisation des potentiels avec la table d'examen ou le lit. |

---
*Schéma de connectivité réseau MaintiDoc 2025.*
