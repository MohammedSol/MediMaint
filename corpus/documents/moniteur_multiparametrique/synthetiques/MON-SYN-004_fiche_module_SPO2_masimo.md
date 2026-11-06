---
id: MON-SYN-004
titre: Fiche composant – Module SpO2 Masimo SET intégré Mindray BeneVision N-Series
famille: moniteur_multiparametrique
modele: Mindray BeneVision N-Series
fabricant: Mindray
type: fiche_composant
langue: fr
statut: synthetique
date_creation: 2025-01-15
verifie: false
pages_estimees: 3
---

# Fiche Descriptive de Composant
## Module SpO2 Masimo SET® — Mindray BeneVision N-Series (N17/N22)

---

## 1. Description et Principe de Mesure

### 1.1 Présentation générale

Le **module SpO2 Masimo SET®** (Signal Extraction Technology) est le composant chargé de la mesure continue et non invasive de la saturation en oxygène du sang artériel (SpO2) sur les moniteurs multiparamétriques Mindray BeneVision N17 et N22. Il est intégré directement dans le chassis du moniteur sous forme de module extractible (slot SpO2 dédié) et connecté au capteur externe par un câble patient multibrins à connecteur propriétaire Masimo LNOP®.

Contrairement aux technologies de photopléthysmographie conventionnelles (Nellcor, Nonin), la technologie **Masimo SET®** (Signal Extraction Technology) utilise des algorithmes propriétaires de séparation des signaux artériels et veineux pour maintenir une mesure fiable même en présence de mouvements du patient, de faible perfusion périphérique, ou d'interférences lumineuses. Cette capacité est particulièrement précieuse en réanimation et en soins intensifs où les patients sont souvent agités et présentent une mauvaise perfusion distale.

### 1.2 Principe physique de la mesure

La SpO2 est mesurée par **spectrophotométrie à deux longueurs d'onde** :
- **660 nm** (rouge) : absorbance différentielle entre hémoglobine oxygénée (HbO₂) et désoxygénée (Hb).
- **940 nm** (infrarouge) : longueur d'onde de référence isosbestique.

Le rapport R des absorptions aux deux longueurs d'onde est converti en valeur de SpO2 par une courbe d'étalonnage empirique (courbe de saturation). Le signal PPG (photopléthysmographie) est simultanément extrait pour le calcul de la fréquence de pouls.

La technologie Masimo SET® introduit une **troisième LED** ou un traitement de signal permettant de distinguer le signal artériel pulsatile (utile) du signal veineux et des artefacts de mouvement (bruit de fond), via la technique de décomposition orthogonale des signaux.

---

## 2. Spécifications Techniques

### 2.1 Paramètres de mesure

| Paramètre                             | Plage                 | Précision              | Résolution |
|---------------------------------------|-----------------------|------------------------|------------|
| **SpO2 (saturation en oxygène)**      | **0% à 100%**         | **±2% (70-100%)**      | 1%         |
| **Fréquence de pouls**                | **20 à 250 bpm**      | **±3 bpm**             | 1 bpm      |
| **Index de perfusion (PI)**           | 0,02% à 20%           | Indicatif              | 0,01%      |
| **Pleth Variability Index (PVI)**     | 0% à 100%             | Indicatif              | 1%         |

> **Note clinique :** La précision de ±2% est spécifiée pour des valeurs de SpO2 comprises entre 70% et 100% sur des sujets à peau de carnation variée, en conditions de faible mouvement (norme ISO 80601-2-61). En dessous de 70%, la précision n'est pas garantie et la valeur doit être interprétée avec précaution.

### 2.2 Performances de la technologie Masimo SET®

| Capacité                                       | Niveau de performance                    |
|------------------------------------------------|------------------------------------------|
| Tolérance aux mouvements                       | Haute (algorithme BIST — Motion Tolerance) |
| Tolérance à la faible perfusion (PI < 1%)      | Oui — maintien mesure jusqu'à PI = 0,05% |
| Tolérance aux lumières ambiantes intenses      | Oui — filtrage actif lumière parasite    |
| Délai de réponse (90% step response)           | ≤ 7 secondes (mode sensibilité normale)  |
| Délai de réponse (mode sensibilité rapide)     | ≤ 2 secondes                             |

### 2.3 Spécifications électriques et techniques du module

| Paramètre                     | Valeur                                        |
|-------------------------------|-----------------------------------------------|
| **Type de module**            | Module extractible — slot SpO2 BeneVision     |
| **Connecteur patient**        | Masimo LNOP® — connecteur 9 broches           |
| **Longueur d'onde LED**       | 660 nm (rouge) et 940 nm (infrarouge)         |
| **Puissance émetteur**        | < 5 mW (classe LED 1 — sécurité patient)      |
| **Courant de fuite patient**  | < 10 µA (CEI 60601-1, partie appliquée type CF) |
| **Classification**            | Partie appliquée type **CF** (défibrilable)   |
| **Isolement galvanique**      | ≥ 4 kV (CEI 60601-1)                         |

---

## 3. Compatibilité des Capteurs

Le module Masimo SET® intégré aux BeneVision N17/N22 est compatible avec l'ensemble des capteurs de la gamme **Masimo LNOP®** et **LNCS®** :

| Référence capteur         | Type            | Usage clinique                          | Remarque |
|---------------------------|-----------------|-----------------------------------------|----------|
| LNOP Adt (réf. 1863)      | Adhesif adulte  | Doigt adulte, utilisation courte durée  | Monopationt |
| LNOP Pdt (réf. 1884)      | Adhésif pédiatrique | Doigt enfant 10-50 kg               | Monopationt |
| LNOP Ndt (réf. 1861)      | Néonatal wrap   | Pied néonatal < 3 kg                   | Monopationt |
| LNCS Adtx (réf. 7000-0.)  | Réutilisable adulte | Doigt adulte — longue durée         | Multipatient (décontamination requise) |
| LNCS Pdtx (réf. 7001-0.)  | Réutilisable pédiatrique | Doigt enfant               | Multipatient |
| LNCS DCI (réf. 7006-0.)   | Clip doigt adulte | Alternative moins sensible au mouvement | Multipatient |

> ⚠️ Utiliser **exclusivement** des capteurs compatibles Masimo LNOP® ou LNCS®. L'utilisation de capteurs génériques ou de marques tierces (Nellcor, Nonin) est incompatible avec le module Masimo SET® et peut produire des mesures erronées ou endommager le module.

---

## 4. Procédure de Test Journalier

Le test journalier du module SpO2 doit être réalisé par le personnel soignant à chaque prise de poste (matin et nuit) ou après tout événement susceptible d'affecter la mesure.

### 4.1 Test fonctionnel rapide (2 minutes)

1. Brancher un capteur LNOP Adtx propre et fonctionnel sur le connecteur SpO2 du moniteur.
2. Placer le capteur sur le doigt d'un opérateur ou d'un patient-test.
3. Vérifier l'affichage des valeurs dans les plages physiologiques normales :
   - SpO2 ≥ **96%** pour un opérateur sain
   - Fréquence de pouls : 50–100 bpm (au repos)
   - Index de perfusion (PI) ≥ **1%** (perfusion acceptable)
4. Observer la courbe de pléthysmographie (PPG) : la courbe doit être régulière, avec une amplitude stable et une morphologie caractéristique (montée rapide, descente progressive).
5. Vérifier la stabilité de la mesure pendant 60 secondes : pas d'affichage « ??? » ou de messages d'erreur.

### 4.2 Test de déclenchement d'alarme

Simuler une désaturation en retirant le capteur du doigt (simulation de perte de signal) :
- Le moniteur doit afficher l'alarme **« Capteur SpO2 déconnecté »** dans les 5 secondes.
- Le signal sonore d'alarme doit être audible (ne pas être en mode silence ou volume = 0).
- Reconnecter le capteur : le signal doit se rétablir en moins de 10 secondes.

---

## 5. Alertes de Dysfonctionnement Fréquentes

| Message d'erreur affiché         | Cause probable                                              | Action recommandée                                               |
|----------------------------------|-------------------------------------------------------------|------------------------------------------------------------------|
| `SpO2 : ???`                     | Perfusion insuffisante, mouvement excessif, capteur mal positionné | Repositionner le capteur, réchauffer l'extrémité, vérifier PI  |
| `Capteur déconnecté`             | Câble patient débranché ou capteur défaillant              | Vérifier connexion, remplacer capteur                            |
| `Vérifier capteur`               | Capteur incompatible, endommagé ou expiré                  | Remplacer par capteur LNOP/LNCS homologué                        |
| `Signal faible – Low PI`         | Perfusion distale < 0,05% (hypothermie, vasospasme, choc) | Envisager mesure alternative (SaO2 gazométrie artérielle)        |
| `Interférence lumineuse`         | Luminosité ambiante excessive sur le site de mesure         | Couvrir le capteur avec un drap ou tissu opaque                 |
| `Module SpO2 défaillant`         | Défaillance interne du module                              | Contacter service biomédical — remplacement module               |
| Valeur SpO2 > mesure réelle     | Carboxyhémoglobine (CO) ou methémoglobinémie               | Confirmer par gazométrie artérielle — SpO2 ne différencie pas HbCO/MetHb |

---

## 6. Maintenance Préventive du Module SpO2

| Tâche de maintenance                              | Fréquence        | Responsable              |
|---------------------------------------------------|------------------|--------------------------|
| Nettoyage du connecteur patient LNOP (IPA 70%)   | Mensuelle        | Technicien biomédical    |
| Inspection visuelle du câble patient              | Trimestrielle    | Infirmier + biomédical   |
| Remplacement capteurs réutilisables usés           | Annuelle ou si dégradation | Infirmier + biomédical |
| Test de précision sur simulateur patient          | Semestrielle     | Technicien biomédical    |
| Vérification courant de fuite patient             | Annuelle (IEC 60601-1) | Technicien biomédical |
| Mise à jour firmware module Masimo                | Selon recommandation Mindray | Technicien biomédical |

> **Durée de vie du module** : Le module SpO2 Masimo SET® intégré est conçu pour une durée de vie de **8 ans** ou 50 000 heures de fonctionnement. Le remplacement est effectué en atelier par un technicien Mindray agréé. Référence pièce de rechange : ML-N17-SPO2-MSM-001.

---

*Fiche établie par le service biomédical Clinique Saint-Louis — Janvier 2025*
*Source : Mindray BeneVision N-Series Technical Manual, PN 046-011178-00 Rev 2.0 ; Masimo SET Technology White Paper, Masimo Corp. 2023*
