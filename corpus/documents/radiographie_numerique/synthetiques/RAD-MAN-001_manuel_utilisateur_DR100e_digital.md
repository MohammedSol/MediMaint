---
id: RAD-MAN-001
titre: "Manuel de l'utilisateur — DR 100e (radiographie numérique)"
reference: "0365D-FR-SYN-2025"
famille: radiographie_numerique
modele: AGFA DR 100e
fabricant: Agfa Radiology Solutions
references_produit: ["6012/003", "6012/004"]
type: manuel_utilisateur
langue: fr
statut: synthetique
date_creation: 2025-01-20
verifie: false
pages_estimees: 18
revision: D
inspire_de: "DR_100e_(digital)_User_Manual_0365_D_20250120_1131_(French).pdf"
---

<!-- Page 1 | DR 100e (radiographie numérique) | Manuel de l'utilisateur | 0365D FR 20250120 1131 -->

# DR 100e (radiographie numérique)
## Manuel de l'utilisateur — Révision D (Synthétique)
**Références produit : 6012/003, 6012/004**

---

### 1. Mentions légales et avis de sécurité

#### 1.1 Droits d'auteur et marques
© Copyright 2025 Agfa Radiology Solutions NV. Tous droits réservés.  
Agfa, le losange Agfa, MUSICA®, SmartRotate™ et DR 100e sont des marques commerciales d'Agfa Radiology Solutions NV ou de ses filiales. Les autres marques et noms commerciaux appartiennent à leurs propriétaires respectifs.

#### 1.2 À propos des avis de sécurité dans ce document
Les avis de sécurité suivants sont utilisés pour attirer l'attention de l'opérateur sur les risques potentiels :

| Symbole | Niveau de gravité | Conséquence en cas de non-respect |
| :--- | :--- | :--- |
| **DANGER** | Danger imminent | Entraîne la mort ou des blessures corporelles graves. |
| **AVERTISSEMENT** | Danger potentiel | Peut entraîner la mort, des blessures graves ou une irradiation excessive. |
| **ATTENTION** | Risque modéré | Peut entraîner des blessures légères ou des dommages matériels à l'équipement. |
| **REMARQUE** | Information technique | Donne des conseils d'exploitation utiles pour optimiser la manipulation. |

---

### 2. Introduction et utilisation prévue

#### 2.1 Utilisation prévue
L'Agfa DR 100e est un système de radiographie mobile à générateur haute fréquence conçu pour l'acquisition d'images radiographiques numériques en projection du corps humain au lit du malade, dans les services de réanimation, les blocs opératoires, les services d'urgence et les services de pédiatrie. Le système est associé à un détecteur plan numérique sans fil (gamme Agfa DR Dura-line, ex: DR 14s, DR 17s).

#### 2.2 Utilisateurs cibles et formation
Ce système est exclusivement destiné à être manipulé par du personnel médical dûment formé et qualifié en radioprotection (manipulateurs d'électroradiologie médicale, radiologues, ingénieurs biomédicaux agréés). 

---

### 3. Configuration et commandes du système

Le système mobile DR 100e se compose des sous-ensembles principaux suivants :
1. **Châssis mobile motorisé / manuel :** Châssis ergonomique avec frein mécanique au pied, poignée de poussée et pédale d'inclinaison pour le franchissement de seuils.
2. **Colonne porte-tube articulée :** Colonne télescopique avec rotation sagittale (±180°) et déplacement vertical équilibré (hauteur foyer-sol : 417 mm à 2 092 mm).
3. **Monobloc radiogène :** Générateur haute fréquence 32 kW (40 kHz), tube à anode tournante (3 000 tr/min, capacité thermique 80 kJ / 107 kHU).
4. **Poste de travail NX (PC tout-en-un) :** Écran tactile 19 pouces intégré, exécutant le logiciel d'acquisition Agfa NX Workstation avec traitement d'image MUSICA® et SmartRotate™.
5. **Détecteur numérique sans fil DR 14s :** Format 35 × 43 cm, scintillateur CsI, matrice a-Si, pas de pixel 148 µm, interface WiFi 5 GHz intégrée et batterie amovible rechargeable.
6. **Collimateur manuel haute précision :** Lampe de collimation LED blanche à extinction automatique (30 secondes), ruban métrique escamotable pour la mesure de la distance foyer-film (SID).

---

### 4. Consignes impératives de sécurité

> **ATTENTION : Risque d'inclinaison pendant le transport sur sol en pente**  
> Ne jamais faire circuler ou stationner l'unité sur des sols présentant une inclinaison supérieure à 5 degrés. Ne pas franchir des rampes d'accès d'une inclinaison supérieure à 10 degrés. Toujours déplacer le système en position de transport verrouillée.

> **ATTENTION : Mouvement non contrôlé du bras et de la colonne**  
> Avant tout déplacement entre les services de l'établissement, assurez-vous impérativement que la colonne est ramenée en position centrale (les deux flèches repères A sur le pied de colonne doivent être parfaitement alignées) et que le verrou mécanique du bras est engagé.

> **AVERTISSEMENT : Rayonnement ionisant X**  
> L'exposition aux rayonnements ionisants présente un risque biologique avéré. Lors du déclenchement d'un tir radiographique, l'opérateur doit impérativement se tenir à une distance minimale de 2 mètres du foyer et du patient, et porter un équipement de protection individuel plombé (tablier de 0,5 mm d'équivalent Pb).

> **ATTENTION : Gestion des câbles et réseau câblé**  
> Avant de déplacer le chariot mobile, débranchez impérativement le câble secteur (longueur 8 m) ainsi que le câble réseau Ethernet RJ45. Enroulez soigneusement le câble d'alimentation sur l'enrouleur prévu à cet effet à l'arrière du châssis.

---

### 5. Flux de travail de base (Workflow clinique)

#### 5.1 Étape 1 : Démarrage du poste NX et du détecteur DR
1. Enclenchez le disjoncteur principal situé sur le flanc inférieur du châssis mobile.
2. Mettez sous tension la station de travail NX en appuyant sur le bouton d'alimentation de l'écran tactile.
3. Retirez le détecteur numérique DR 14s de son logement de charge (docking station) ; vérifiez que le témoin LED d'état s'allume en vert fixe (indiquant la liaison WiFi active et une batterie > 80%).

#### 5.2 Étape 2 : Récupération des données du patient (Worklist DICOM)
1. Si l'appareil est connecté à la prise réseau murale, interrogez la modalité Worklist (MWL) du Système d'Information Radiologique (SIR).
2. Sélectionnez le patient dans la liste de travail du jour sur l'écran tactile NX.
3. *Remarque :* Si la connexion au SIR est indisponible en mode mobile, activez le mode "Urgence" ou saisissez manuellement les données d'identification du patient à l'aide du clavier virtuel affiché sur l'écran tactile NX.

#### 5.3 Étape 3 : Déplacement et positionnement
1. Déverrouillez le frein au pied du châssis mobile.
2. Poussez l'appareil par la poignée principale jusqu'au lit du patient.
3. Positionnez le chariot, appliquez le frein de stationnement. Déverrouillez le bras porteur et alignez le tube à rayons X avec la région anatomique cible.
4. Glissez le détecteur sans fil DR 14s sous le patient (enveloppé d'une housse de protection hygiénique jetable).
5. Allumez le voyant lumineux du collimateur pour centrer le faisceau et ajustez les volets plombés pour limiter strictement le champ d'irradiation à la zone anatomique d'intérêt. Réglez la distance foyer-détecteur (SID standard : 100 cm ou 150 cm).

#### 5.4 Étape 4 : Sélection des paramètres d'exposition et tir
1. Sélectionnez le programme anatomique (APR) correspondant sur la console NX (ex : *Thorax AP couché*). Les valeurs de kV (ex : 85 kV) et de mAs (ex : 2.5 mAs) sont automatiquement transmises au panneau de commande du générateur.
2. Si nécessaire, affinez manuellement les paramètres kV/mAs à l'aide des touches `[+ kV] / [- kV]` et `[+ mAs] / [- mAs]`.
3. Saisissez le bouton d'exposition câblé à deux crans (ou la télécommande infrarouge).
4. Appuyez au premier cran : le préchauffage de l'anode commence, le voyant PRÊT s'allume en vert fixe.
5. Appuyez à fond au deuxième cran : l'exposition a lieu. Le témoin "X-RAY ON" s'illumine en orange/rouge et un signal sonore continu retentit pendant toute la durée de l'émission.

#### 5.5 Étape 5 : Contrôle qualité et validation
1. L'image brute est transmise en WiFi au poste NX en moins de 3 secondes.
2. L'algorithme MUSICA® traite automatiquement les contrastes et équilibre la dynamique des tissus mous et des structures osseuses.
3. SmartRotate™ détecte l'orientation anatomique et pivote l'image pour un affichage conforme.
4. Vérifiez l'indice d'exposition (EI) et l'indice d'écart (DI) affichés. Validez l'image et déclenchez l'envoi DICOM Storage vers le serveur PACS institutionnel.

---

### 6. Maintenance préventive et entretien

- **Quotidien :** Décontamination externe du chariot et du détecteur DR à l'aide d'une lingette désinfectante homologuée (voir fiche de nettoyage RAD-SYN-005). Contrôle visuel des câbles.
- **Hebdomadaire :** Vérification du témoin de charge batterie, recalibration tactile si nécessaire.
- **Trimestriel :** Réalisation de la procédure de maintenance préventive complète (voir document RAD-PROC-001).
- **Semestriel :** Calibration du gain et de la non-uniformité (NUC) du détecteur numérique (voir RAD-PROC-003).

---
*Document synthétique généré pour le projet MaintiDoc 2025 — Basé sur les manuels Agfa séries 0365 et spécifications DR 100e. Non destiné à l'exploitation médicale directe.*
