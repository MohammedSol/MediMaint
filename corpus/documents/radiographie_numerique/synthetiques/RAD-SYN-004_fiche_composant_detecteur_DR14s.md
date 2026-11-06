---
id: RAD-SYN-004
titre: Fiche composant – Détecteur numérique sans fil AGFA DR 14s
famille: radiographie_numerique
modele: AGFA DR 100e
fabricant: Agfa
type: fiche_composant
langue: fr
statut: synthetique
date_creation: 2025-01-15
verifie: false
pages_estimees: 3
---

# Fiche Descriptive de Composant
## Détecteur Numérique Sans Fil AGFA DR 14s

---

## 1. Description Générale

Le **détecteur numérique sans fil AGFA DR 14s** est un panneau plat radiographique portable de format 35×43 cm (14×17 pouces), conçu pour une utilisation avec le système de radiographie mobile AGFA DR 100e et les pupitres de radiographie fixes compatibles de la gamme DR. Il constitue le composant central du système d'acquisition d'image, transformant le rayonnement X transmis par le patient en signal numérique traitable.

Le DR 14s repose sur une technologie de scintillateur indirect à **iodure de césium (CsI)** couplé à une matrice active de **silicium amorphe (a-Si)**, offrant un compromis optimal entre efficacité de détection quantique (DQE), résolution spatiale et robustesse mécanique pour un usage en environnement hospitalier intensif. La liaison sans fil utilise le protocole **WiFi 802.11ac (5 GHz)** pour la transmission des images vers la console d'acquisition, avec une alternative de connexion par docking filaire via connecteur propriétaire Agfa 24 broches.

Le détecteur est conçu pour résister aux contraintes des environnements de soins intensifs et d'urgence : indice de protection **IP54** (protection contre les projections d'eau et la poussière), traitement de surface antibactérien, et robustesse aux chocs (certifié pour une chute de 1 m selon les tests internes Agfa).

---

## 2. Spécifications Techniques

### 2.1 Caractéristiques du panneau plat

| Paramètre                         | Valeur                                      |
|-----------------------------------|---------------------------------------------|
| **Format actif**                  | 35 × 43 cm (13,8 × 17 in)                  |
| **Résolution native**             | 2 368 × 2 912 pixels                        |
| **Taille de pixel (pixel pitch)** | **148 µm**                                  |
| **Profondeur de bit**             | 14 bits (16 384 niveaux de gris)            |
| **Scintillateur**                 | CsI (iodure de césium) structuré, dépôt CVD |
| **Couche photodiode**             | Silicium amorphe (a-Si)                     |
| **DQE @ 1 µGy, 1 lp/mm**         | ≥ 68% (IEC 62220-1-1)                       |
| **MTF à 10%**                     | ≥ 3,0 paires de lignes/mm                  |
| **Plage dynamique**               | > 25 000:1                                  |
| **Temps de lecture par image**    | < 4 secondes                                |
| **Fréquence d'images**            | 2,5 images/min en mode mobile sans fil      |

### 2.2 Dimensions et masse

| Paramètre        | Valeur                    |
|------------------|---------------------------|
| **Dimensions**   | 380 × 460 × 15 mm         |
| **Masse**        | 3,8 kg (avec batterie)    |
| **Épaisseur**    | 15 mm                     |

### 2.3 Alimentation et batterie

| Paramètre                          | Valeur                                    |
|------------------------------------|-------------------------------------------|
| **Type de batterie**               | Li-Ion rechargeable, 7,4 V — 6 600 mAh   |
| **Autonomie (pleine charge)**      | **≥ 4 heures** (environ 400 expositions)  |
| **Durée de charge complète**       | ≤ 3 heures via station docking            |
| **Durée de vie batterie**          | ≈ 1 200 cycles de charge (80% capacité)  |
| **Charge via docking**             | Oui — Chargeur intégré station DR 100e    |
| **Indication niveau batterie**     | LED multicolore (vert/orange/rouge)       |

### 2.4 Connectivité et transmission

| Paramètre                     | Valeur                                            |
|-------------------------------|---------------------------------------------------|
| **Transmission sans fil**     | WiFi 802.11a/b/g/n/ac (2,4 GHz et 5 GHz)         |
| **Chiffrement**               | WPA2-Enterprise (802.1X/EAP-TLS)                 |
| **Connecteur filaire**        | Connecteur propriétaire Agfa 24 broches (docking) |
| **Protocoles**                | DICOM 3.0 (DICOM Storage, DICOM Print)            |
| **Compatible**                | AGFA DR 100e, DR 100, NX, DX-S, grilles d'acquisition compatibles |

### 2.5 Environnement et protection

| Paramètre                         | Valeur                               |
|-----------------------------------|--------------------------------------|
| **Indice de protection**          | **IP54** (CEI 60529)                 |
| **Température de fonctionnement** | +10°C à +40°C                        |
| **Humidité de fonctionnement**    | 20% à 80% HR (sans condensation)     |
| **Température de stockage**       | -20°C à +60°C                        |
| **Résistance aux chocs**          | 1 m (surface dure) — tests internes  |
| **Surface**                       | Traitement antibactérien intégré     |

---

## 3. Procédure de Connexion à l'AGFA DR 100e

### 3.1 Connexion sans fil (WiFi — mode opérationnel standard)

1. **Mettre en service** la console DR 100e et vérifier que le réseau WiFi dédié imagerie est actif (SSID paramétré en usine ou par le technicien biomédical).
2. **Allumer le détecteur** en maintenant le bouton Power enfoncé pendant 2 secondes jusqu'à l'allumage du voyant LED (vert clignotant = démarrage, vert fixe = prêt).
3. **Vérifier l'association** : sur la console DR 100e, le détecteur doit apparaître dans la liste des détecteurs disponibles sous l'onglet `Detector > Wireless`. L'icône WiFi passe au vert et affiche le niveau de signal.
4. **Sélectionner le détecteur** dans la console et confirmer la connexion. Un bip sonore confirme l'association réussie.
5. **Effectuer une exposition test** (sans patient) pour confirmer la transmission d'image (délai nominal < 4 secondes).

### 3.2 Connexion filaire via docking

Insérer le détecteur dans la baie de docking intégrée au chassis du DR 100e. La connexion filaire est automatique et prioritaire sur le WiFi. Le voyant LED du détecteur passe en bleu fixe. Le mode docking permet également la charge simultanée de la batterie.

### 3.3 Points de vérification avant connexion

- Vérifier que la version firmware du détecteur est compatible avec la version logicielle MUSICA installée (consulter la matrice de compatibilité AGFA, réf. SOP-COMPAT-MUSICA-DR14).
- S'assurer que l'adresse IP du détecteur est dans le même sous-réseau que la console (plage 192.168.100.x recommandée pour le réseau imagerie isolé).

---

## 4. Points de Vigilance Maintenance

| Point de vigilance                        | Fréquence de vérification | Action recommandée                                               |
|-------------------------------------------|---------------------------|------------------------------------------------------------------|
| État des contacts du connecteur docking   | Trimestrielle             | Inspection visuelle + nettoyage si oxydation (spray IPA 99,9%)  |
| Intégrité des joints IP54                 | Semestrielle              | Inspection visuelle sur tout le pourtour du panneau              |
| Niveau de charge et capacité batterie     | Mensuelle                 | Test de charge complète et mesure autonomie réelle               |
| Dead Pixel Map (DPM)                      | Trimestrielle             | Acquisition dark field + analyse via MUSICA QC                   |
| Calibration NUC (gain + offset)           | Semestrielle              | Recalibration complète si dérive > 3% sur flat field             |
| État de la surface du panneau             | Mensuelle                 | Inspection pour microfissures, impacts, délamination surface      |
| Firmware détecteur                        | Annuelle                  | Vérification et mise à jour selon recommandations AGFA           |
| Niveau de signal WiFi en salle d'usage    | Annuelle                  | Mesure RSSI (seuil minimum acceptable : -70 dBm)                 |

> **⚠️ ATTENTION :** Ne jamais utiliser de solvants organiques (acétone, alcool méthylique, chlore > 0,1%) ni de produits abrasifs sur la surface du détecteur. Risque de dégradation du traitement antibactérien et des joints IP54.

---

## 5. Pièces de Rechange Référencées

| Référence AGFA         | Désignation                                       | Durée de vie estimée |
|------------------------|---------------------------------------------------|----------------------|
| AGF-DR14-BAT-001       | Batterie Li-Ion 6 600 mAh (7,4 V)                | 1 200 cycles / ~3 ans |
| AGF-DR14-CON-002       | Connecteur docking 24 broches                    | 5 ans                |
| AGF-DR14-COV-003       | Capot de protection arrière                       | Sur choc             |
| AGF-DR14-JNT-004       | Kit joints IP54 complet (3 joints)               | 4 ans                |
| AGF-DR14-PWR-005       | Module de gestion d'alimentation (BMS)           | 7 ans                |
| AGF-DR14-WIF-006       | Module WiFi 802.11ac (remplacement en atelier)   | 7 ans                |

> **Note :** Le remplacement du panneau plat TFT/CsI (réf. AGF-DR14-TFT-010) ne peut être effectué qu'en atelier constructeur agréé. Cette opération nécessite une recertification complète selon IEC 62220-1-1.

---

## 6. Durée de Vie Estimée

La durée de vie utile du détecteur AGFA DR 14s est estimée par le constructeur à **8 à 10 ans** dans des conditions d'utilisation et de maintenance normales, soit environ **150 000 à 200 000 expositions** au total. La principale cause de fin de vie utile est la dégradation du scintillateur CsI, qui se traduit par une décroissance progressive de la DQE. Lorsque la DQE mesurée tombe en dessous de **60% @ 1 lp/mm**, le remplacement ou la rénovation complète du panneau est recommandée.

La batterie, en tant que consommable, doit être remplacée tous les 3 ans ou lorsque sa capacité résiduelle tombe en dessous de 80% de la capacité nominale (< 5 280 mAh).

---

*Fiche établie par le service biomédical CHU Bordeaux — Mise à jour : janvier 2025*
*Source : Documentation technique AGFA DR 14s — PN 5784-AGF-DR14-TM-FR, Rev. 4*
