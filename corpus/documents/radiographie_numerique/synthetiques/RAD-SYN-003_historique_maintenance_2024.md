---
id: RAD-SYN-003
titre: Historique de maintenance préventive 2024 – AGFA DR 100e
famille: radiographie_numerique
modele: AGFA DR 100e
fabricant: Agfa
type: historique_maintenance
langue: fr
statut: synthetique
date_creation: 2025-01-15
verifie: false
pages_estimees: 4
---

# Historique de Maintenance Préventive 2024
## AGFA DR 100e — SN : FR-2024-DR100-0847
### CHU Bordeaux — Service Radiologie Urgences

---

## Informations Générales

| Champ                      | Valeur                                        |
|----------------------------|-----------------------------------------------|
| **Équipement**             | AGFA DR 100e                                  |
| **Numéro de série**        | FR-2024-DR100-0847                            |
| **N° Inventaire GMAO**     | CHU-BX-RAD-0234                               |
| **Détecteur associé**      | AGFA DR 14s — SN : DR14S-FR-20220389          |
| **Service**                | Radiologie — Urgences adultes                 |
| **Responsable équipement** | Dr. Isabelle Rondeau                          |
| **Technicien référent**    | Jean-Marc Lefèvre (BMET-AQ-2021-0047)         |
| **Contrat maintenance**    | Contrat Agfa Full-Service N° AGF-BX-2022-0147 |
| **Période couverte**       | 01/01/2024 — 31/12/2024                       |

---

## Tableau des Interventions de Maintenance 2024

| Date       | Type d'intervention          | Intervenant              | Actions réalisées                                                                                                                                                                                                       | Résultat                                    | Prochaine échéance |
|------------|------------------------------|--------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------|--------------------|
| 15/01/2024 | Maintenance préventive trimestrielle (T1) | Jean-Marc Lefèvre | Inspection mécanique générale (roulettes, freins, bras porte-détecteur) ; vérification connexions électriques ; test du système de freinage d'urgence ; nettoyage complet chassis ; vérification de la batterie principale (capacité résiduelle : 94%) ; test fonctionnel complet | Conforme — aucune anomalie détectée | 15/04/2024 |
| 02/02/2024 | Étalonnage annuel détecteur  | AGFA France (technicien constructeur : P. Moreau) | Calibration NUC complète (dark field + flat field) ; mise à jour de la Dead Pixel Map ; vérification MTF et DQE ; test de linéarité de réponse ; recertification selon norme IEC 62220-1-1 | Conforme — DQE 72% @ 1lp/mm ; MTF 10% : 3,5 lp/mm | 02/02/2025 |
| 18/03/2024 | Nettoyage approfondi + décontamination | Jean-Marc Lefèvre | Démontage des capots latéraux ; nettoyage de la mécanique interne (ventilateurs, grilles de ventilation) ; décontamination complète du chassis et du détecteur avec Surfanios Premium dilué à 0,5% ; vérification de l'état des joints d'étanchéité IP54 du détecteur | Conforme — joints en bon état | 18/06/2024 |
| 10/04/2024 | Maintenance préventive trimestrielle (T2) | Jean-Marc Lefèvre | Vérification état des roues et freins (usure roue avant gauche : 15%) ; test de charge batterie complète (capacité : 91%) ; vérification câblage interne ; contrôle de l'affichage DICOM ; test de la console de commande ; vérification état connecteur docking détecteur | Conforme — usure roue à surveiller | 10/07/2024 |
| 05/06/2024 | Mise à jour logicielle MUSICA | AGFA France (remote + on-site) | Mise à jour MUSICA de la version 3.3.2 vers 3.4.0 ; mise à jour firmware détecteur DR 14s de 2.5.1 vers 2.6.1 ; mise à jour du driver de la console d'acquisition ; reconfiguration des profils d'optimisation d'image (Urgences adultes, Urgences pédiatriques, Trauma) ; validation post-mise à jour sur fantômes | Conforme — amélioration perceptible du contraste sur profil trauma | 05/12/2024 |
| 15/07/2024 | Maintenance préventive trimestrielle (T3) | Jean-Marc Lefèvre | Inspection mécanique ; vérification du système de blocage directionnel ; remplacement de la roue avant gauche (usure > 20% confirmée) ; test fonctionnel complet ; contrôle qualité images sur fantôme LEEDS TOR 18FG ; vérification de l'alignement du collimateur | Conforme après remplacement roue. MTF 3,4 lp/mm | 15/10/2024 |
| 10/09/2024 | Étalonnage semestriel + contrôle qualité | Jean-Marc Lefèvre | Calibration flat field intermédiaire ; recalcul gain table ; vérification Dead Pixel Map (DPM — aucun nouveau pixel défectueux) ; mesure du kerma de référence avec chambre d'ionisation Farmer FC65-G (SN : NE2581A) raccordée au COFRAC ; test reproductibilité (CV = 0,5%) | Conforme — dérive de +1,2% sur flat field, dans les limites | 10/03/2025 |
| 15/10/2024 | Maintenance préventive trimestrielle (T4) | Jean-Marc Lefèvre | Inspection complète de fin d'année ; vérification batterie (capacité : 88%) ; nettoyage général ; test toutes fonctionnalités ; vérification connexion WiFi (signal -58 dBm, SNR 32 dB) ; test de transfer DICOM vers PACS (Orthanc CHU-BX) ; vérification étiquettes et marquages CE | Conforme — batterie à surveiller (prévision remplacement 2025) | 15/01/2025 |

---

## Pièces de Rechange Utilisées en 2024

| Date       | Référence pièce      | Désignation                          | Quantité | N° de lot     | Coût estimé |
|------------|----------------------|--------------------------------------|----------|---------------|-------------|
| 15/07/2024 | AGF-DR100-WHL-003    | Roue directionnelle avant gauche Ø150mm | 1     | WHL-2024-0892 | 85 € HT     |
| **Total**  |                      |                                      |          |               | **85 € HT** |

---

## Indicateurs de Performance 2024

### Disponibilité de l'équipement

| Indicateur                              | Valeur 2024    | Objectif contractuel |
|-----------------------------------------|----------------|----------------------|
| Taux de disponibilité                   | **98,7%**      | ≥ 97%                |
| Nombre d'interventions curatives        | 1              | —                    |
| Nombre d'interventions préventives      | 8              | —                    |
| Durée totale d'arrêt technique          | 11h30          | —                    |
| MTTR moyen (Mean Time To Repair)        | 2h15           | ≤ 4h                 |
| MTBF (Mean Time Between Failures)       | 8 450 h        | —                    |

### Évolution des paramètres clés du détecteur en 2024

| Paramètre                     | Jan 2024 | Avr 2024 | Juil 2024 | Oct 2024 | Tendance   |
|-------------------------------|----------|----------|-----------|----------|------------|
| DQE @ 1lp/mm (%)             | 72       | 71       | 70        | 69       | Décroissance légère normale |
| MTF 10% (lp/mm)              | 3,5      | 3,5      | 3,4       | 3,4      | Stable     |
| Capacité batterie (%)         | 94       | 91       | 89        | 88       | Décroissance prévisible |
| Nombre pixels défectueux      | 9        | 9        | 9         | 12       | Légère augmentation |
| Uniformité spatiale — CV (%)  | 1,5      | 1,6      | 1,7       | 1,8      | Légère dérive |

---

## Commentaires et Tendances Observées

### Observations générales

L'AGFA DR 100e (SN FR-2024-DR100-0847) a démontré un excellent niveau de fiabilité sur l'ensemble de l'année 2024, avec un seul incident curatif mineur (remplacement d'une roue directionnelle). Le taux de disponibilité de **98,7%** dépasse l'objectif contractuel de 97%.

### Tendance batterie — Point de vigilance

La capacité résiduelle de la batterie principale Li-Ion a évolué de 94% en janvier à 88% en octobre, soit une décroissance de **6 points en 10 mois**. Cette évolution est cohérente avec le vieillissement normal des accumulateurs Li-Ion après 2 ans d'utilisation intensive (environ 850 cycles de charge estimés). **Une procédure de remplacement préventif de la batterie est recommandée pour le premier trimestre 2025** avant que la capacité n'atteigne le seuil de 80% (autonomie réduite à moins de 3h par charge).

### Tendance détecteur — Vieillissement du scintillateur CsI

La DQE montre une décroissance progressive de 72% à 69% sur l'année, ce qui est dans les limites normales de dégradation du scintillateur CsI au césium (spécification AGFA : DQE minimale acceptable ≥ 60% @ 1lp/mm). La tendance, si elle se poursuit au même rythme, suggère une durée de vie utile restante estimée à **4-5 ans** avant d'atteindre la limite d'acceptabilité. Aucune action immédiate requise.

### Tendance pixels défectueux

Le passage de 9 à 12 pixels défectueux entre juillet et octobre est à surveiller. Bien que toujours très en deçà des limites acceptables (seuil constructeur : 100 pixels défectueux hors cluster central), l'apparition de nouveaux défauts doit être tracée avec précision lors de chaque contrôle qualité.

### Mise à jour logicielle MUSICA 3.4 — Bilan

La mise à jour de MUSICA vers la version 3.4.0 en juin 2024 a apporté une amélioration notable du traitement d'image sur les profils « Urgences adultes » et « Trauma », en particulier pour la gestion des niveaux de gris en situation de faible exposition (réduction du bruit perceptible de ~12% d'après les mesures SNR). Aucun bug critique n'a été identifié depuis la mise à jour.

---

## Prévisions de Maintenance 2025

| Action prévue                              | Échéance estimée | Priorité |
|--------------------------------------------|------------------|----------|
| Maintenance préventive T1 2025            | 15/01/2025       | Normale  |
| Remplacement batterie principale          | T1 2025          | Haute    |
| Étalonnage annuel constructeur (AGFA)     | 02/02/2025       | Obligatoire |
| Mise à jour firmware détecteur vers 2.7.0 | T2 2025          | Normale  |
| Étalonnage semestriel                     | 10/03/2025       | Normale  |

---

*Document établi par Jean-Marc Lefèvre — Ingénieur biomédical CHU Bordeaux*
*Validé par Henri Beaumont — Responsable service biomédical*
*Date de validation : 05/01/2025*
*Archivé dans GMAO sous référence : HIST-2024-CHU-BX-RAD-0234*
