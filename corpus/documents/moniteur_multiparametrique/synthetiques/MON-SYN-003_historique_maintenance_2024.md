---
id: MON-SYN-003
titre: Historique de maintenance préventive 2024 – Mindray BeneVision N-Series
famille: moniteur_multiparametrique
modele: Mindray BeneVision N-Series
fabricant: Mindray
type: historique_maintenance
langue: fr
statut: synthetique
date_creation: 2025-01-15
verifie: false
pages_estimees: 4
---

# Historique de Maintenance Préventive 2024
## Mindray BeneVision N-Series (N17/N22)
### Clinique Saint-Louis — Lyon — Service Réanimation & USIC

---

## Informations Générales

| Champ                      | Valeur                                              |
|----------------------------|-----------------------------------------------------|
| **Parc d'équipements**     | 6 × BeneVision N17 + 4 × BeneVision N22            |
| **Localisation**           | Réanimation chirurgicale (4 N22) + USIC (6 N17)    |
| **Responsable équipement** | M. Fabrice Dupont (cadre USIC) / Dr. Lemaire (réa) |
| **Technicien référent**    | Sophie Vigneron (BMET-IDF-2020-0112)               |
| **Contrat maintenance**    | Contrat Mindray Care Plus N° MDR-SL-2021-0088       |
| **Période couverte**       | 01/01/2024 — 31/12/2024                             |
| **Équipement de référence**| BeneVision N17 SN ML-N17-20230042 (USIC lit 1)     |

---

## Tableau des Interventions de Maintenance 2024

| Date       | Type d'intervention                  | Intervenant                          | Actions réalisées                                                                                                                                                                                                                                       | Résultat                                                       | Prochaine échéance |
|------------|--------------------------------------|--------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------|--------------------|
| 10/01/2024 | Vérification électrique sécurité     | Sophie Vigneron                      | Mesure courant de fuite à la terre sur les 10 moniteurs (norme CEI 60601-1) ; vérification des fusibles ; test de la continuité de mise à la terre ; inspection des cordons d'alimentation ; contrôle de l'isolation galvanique des modules de mesure ECG, SpO2, PNI | Conformes — courants de fuite max. mesurés : 48 µA (limite : 500 µA) | 10/07/2024 |
| 25/01/2024 | Test complet des alarmes             | Sophie Vigneron + Fabrice Dupont     | Test systématique de toutes les alarmes sonores et visuelles (SpO2, FC, PNI systolique/diastolique, FR, Température, ECG morphologie) sur simulateur patient Fluke ProSim 8 ; vérification des volumes sonores et des seuils configurés ; contrôle alarme d'urgence défibrillateur intégré NX (N22) | Conformes sur 9/10 moniteurs — 1 alarme température non fonctionnelle (N17 lit 3, réparée) | 25/07/2024 |
| 15/03/2024 | Nettoyage capteurs et câbles         | Sophie Vigneron                      | Nettoyage de l'ensemble des capteurs SpO2 (Masimo), câbles ECG 12 dérivations, manchettes PNI (toutes tailles) ; désinfection avec Surfanios 0,5% ; inspection visuelle des isolants de câbles ; remplacement de 3 manchettes PNI taille adulte usées et 1 câble ECG 10-brins détérioré | Conformes — renouvellement accessoires consommables | 15/09/2024 |
| 02/04/2024 | Mise à jour firmware                 | Mindray France (ingénieur P. Lescot) | Mise à jour firmware BeneVision N17 de V03.09.018 vers V03.10.021007 ; mise à jour N22 de V03.11.012 vers V03.12.014003 ; mise à jour modules SpO2 Masimo ; reconfiguration des profils d'alarme post-mise à jour ; tests de non-régression sur 48h | Conformes — amélioration de la gestion des alarmes en mode alarme silence | 02/10/2024 |
| 20/05/2024 | Étalonnage PNI (pression non invasive) | Sophie Vigneron + prestataire métrologique | Étalonnage des 10 brassards PNI avec référence étalon (manomètre Druck DPI 610 raccordé COFRAC) ; mesure des pressions systolique/diastolique/MAP sur simulateur PNI ; ajustement des coefficients de correction si dérive > 3 mmHg | Conformes — dérive maximale observée : +2 mmHg sur N22 lit 7, dans les limites | 20/11/2024 |
| 18/07/2024 | Test batterie interne et UPS         | Sophie Vigneron                      | Test de capacité résiduelle des batteries internes Li-Ion de chaque moniteur (décharge contrôlée depuis 100% jusqu'à coupure) ; mesure de l'autonomie réelle ; vérification du module UPS intégré ; test de transfert sur batterie simulé (coupure secteur) | Conformes sur 8/10 — 2 batteries (N17 lot 2021) à autonomie < 60 min : remplacement planifié | 18/01/2025 |
| 05/09/2024 | Vérification DICOM connectivity      | Sophie Vigneron + DSI Clinique       | Vérification de la connectivité DICOM de chaque moniteur vers le système d'information clinique (Orthanc PACS) et le DME (Dossier Médical Électronique — Crossway®) ; test d'envoi de rapports de tendances et d'alarmes ; vérification de la conformité des UID patients ; test de la fonction Mindray Central Station | Conformes — 1 N22 (lit 8) présentait une désynchro horloge NTP : resynchronisation effectuée | 05/03/2025 |
| 10/10/2024 | Contrôle qualité ECG 12 dérivations  | Sophie Vigneron                      | Test de l'acquisition ECG 12 dérivations sur chaque N22 équipé du module ECG avancé (câble 10 électrodes) ; simulation de morphologies normales et pathologiques (arythmies, ST élévation) avec Fluke ProSim 8 ; vérification des mesures automatiques (PR, QRS, QT/QTc, axe électrique) ; test de l'impression rapports ECG vers imprimante HL7 | Conformes — précision mesure QTc : ±4 ms (spécification Mindray : ±10 ms) | 10/04/2025 |

---

## Pièces de Rechange et Consommables Utilisés en 2024

| Date       | Référence              | Désignation                                    | Quantité | Équipement concerné      | Coût estimé |
|------------|------------------------|------------------------------------------------|----------|--------------------------|-------------|
| 15/03/2024 | ML-PNI-MAN-AD-003      | Manchette PNI adulte standard (22-32 cm)       | 3        | N17 — USIC               | 54 € HT     |
| 15/03/2024 | ML-ECG-CBL-10B-001     | Câble ECG 10 broches AHA/IEC (3m)              | 1        | N22 — Réa, lit 6         | 78 € HT     |
| 25/01/2024 | ML-N17-TEMP-SNS-002    | Sonde température YSI-400 (réparation module)  | 1        | N17 — USIC, lit 3        | 125 € HT    |
| Prévu 2025 | ML-N17-BAT-INT-001     | Batterie interne Li-Ion 11.1V / 4400 mAh       | 2        | N17 — 2 unités lot 2021  | 320 € HT    |
| **Total 2024** |                    |                                                |          |                          | **257 € HT** |

---

## Indicateurs de Performance 2024 — Parc Moniteurs

### Disponibilité du parc

| Indicateur                              | N17 (6 unités) | N22 (4 unités) | Objectif |
|-----------------------------------------|----------------|----------------|----------|
| Taux de disponibilité moyen             | **99,1%**      | **99,4%**      | ≥ 98%    |
| Nombre d'interventions curatives        | 3              | 1              | —        |
| Durée totale d'arrêt technique          | 8h             | 4h15           | —        |
| MTTR moyen                             | 2h40           | 4h15           | ≤ 4h     |

### Évolution des indicateurs clés sur l'année 2024

| Indicateur                               | T1 2024 | T2 2024 | T3 2024 | T4 2024 | Tendance   |
|------------------------------------------|---------|---------|---------|---------|------------|
| Courant de fuite max (µA)                | 48      | 46      | 51      | 49      | Stable     |
| Précision SpO2 (± %, simulateur)         | 1,2     | 1,2     | 1,3     | 1,2     | Stable     |
| Précision PNI systolique (± mmHg)        | 1,8     | 1,5     | 1,9     | 2,0     | Légère dérive |
| Autonomie batterie N17 (min, lot 2021)   | 85      | 78      | 71      | 62      | Décroissance |
| Alarmes test : taux de conformité (%)    | 98      | 100     | 100     | 100     | Amélioré   |

---

## Commentaires et Tendances Observées

### Batteries N17 lot 2021 — Point critique

Deux BeneVision N17 du lot de mise en service 2021 (N17 lits 2 et 5 — USIC) affichent une autonomie batterie en nette décroissance, passant de 85 minutes en début d'année à 62 minutes en fin d'année. Sachant que la spécification Mindray impose une autonomie minimale de **60 minutes** (critère d'acceptabilité), ces deux unités sont **en limite de conformité**. Le remplacement préventif des batteries (réf. ML-N17-BAT-INT-001) est planifié pour **janvier 2025** avant toute nouvelle défaillance en service clinique.

### Mise à jour firmware V03.10/V03.12 — Bilan positif

La mise à jour firmware d'avril 2024 a apporté des améliorations notables dans la gestion du mode « alarme silence » (désormais limité à 2 minutes maximum au lieu de 5 minutes dans la version précédente, conformément à la recommandation de la Haute Autorité de Santé sur la gestion des alarmes en réanimation). Un bug de remontée des alarmes SpO2 vers la station centrale en cas de déconnexion WiFi temporaire a également été corrigé.

### Étalonnage PNI — Surveillance accrue

La dérive PNI observée sur le N22 lit 7 (+2 mmHg sur systolique) reste dans les limites acceptables mais la tendance à la légère dérive doit être surveillée lors du prochain étalonnage semestriel de novembre 2024. Si la dérive dépasse 3 mmHg, une intervention de recalibration du module PNI sera requise.

### Connexions DICOM — Point de vigilance infrastructure

La désynchronisation horloge NTP détectée sur un N22 est révélatrice d'une fragilité potentielle du réseau NTP de la clinique. Recommandation formulée à la DSI : mise en place d'une redondance du serveur NTP pour l'ensemble du parc d'équipements biomédicaux connectés.

### Contrôle qualité ECG 12 dérivations — Excellence de performance

Les N22 équipés du module ECG avancé ont démontré d'excellentes performances en mesure ECG automatisée, avec une précision QTc de ±4 ms, largement dans les spécifications. La morphologie des arythmies simulées était correctement identifiée par l'algorithme Mindray (100% de reconnaissance sur les 8 morphologies testées : TV, FA, flutter, ESV, bloc de branche droit/gauche, BAV 2° et 3°).

---

## Prévisions de Maintenance 2025

| Action prévue                              | Échéance        | Priorité  |
|--------------------------------------------|-----------------|-----------|
| Remplacement batteries N17 lits 2 et 5    | Janvier 2025    | Haute     |
| Vérification électrique sécurité (H1)     | 10/07/2024      | Obligatoire |
| Test alarmes (H1)                          | 25/07/2024      | Obligatoire |
| Étalonnage PNI (H2)                        | 20/11/2024      | Obligatoire |
| Vérification DICOM (H2)                    | 05/03/2025      | Normale   |
| Contrôle qualité ECG (H1 2025)            | 10/04/2025      | Normale   |
| Renouvellement contrat Mindray Care Plus   | 30/06/2025      | Obligatoire |

---

*Document établi par Sophie Vigneron — Ingénieure biomédicale Clinique Saint-Louis*
*Validé par M. Patrick Arnaud — Directeur des services techniques*
*Date de validation : 08/01/2025*
*Archivé GMAO sous référence : HIST-2024-SL-LY-MON-N-SERIES*
