---
id: RAD-SYN-001
titre: Rapport d'intervention – Calibration du détecteur DR 14s sur AGFA DR 100e
famille: radiographie_numerique
modele: AGFA DR 100e
fabricant: Agfa
type: rapport_intervention
langue: fr
statut: synthetique
date_creation: 2025-01-15
verifie: false
pages_estimees: 3
---

# Rapport d'Intervention Technique
## Calibration du Détecteur Numérique DR 14s — AGFA DR 100e

---

| Champ               | Valeur                                      |
|---------------------|---------------------------------------------|
| **N° Rapport**      | RAP-2025-0315-001                           |
| **Date**            | 15/03/2025                                  |
| **Heure début**     | 08h30                                       |
| **Heure fin**       | 11h00                                       |
| **Durée totale**    | 2h30                                        |
| **Technicien**      | Jean-Marc Lefèvre                           |
| **N° Habilitation** | BMET-AQ-2021-0047                           |
| **Établissement**   | CHU Bordeaux — Service Radiologie Urgences  |
| **Contact site**    | Dr. Isabelle Rondeau, Cadre de santé        |
| **Équipement**      | AGFA DR 100e                                |
| **Numéro de série** | FR-2024-DR100-0847                          |
| **N° Inventaire**   | CHU-BX-RAD-0234                             |
| **Version logiciel**| MUSICA 3.4.1 / Firmware 2.6.3              |

---

## 1. Motif de l'Intervention

Suite à la détection d'une dérive de sensibilité lors du contrôle qualité quotidien effectué par le manipulateur radio en date du 13/03/2025, une intervention de calibration complète du détecteur numérique sans fil **AGFA DR 14s** (SN : DR14S-FR-20220389) a été programmée. Les valeurs de pixel moyen mesurées sur le fantôme de référence LEEDS TOR 18FG présentaient un écart de **+8,2%** par rapport aux valeurs nominales enregistrées lors de la réception de l'équipement, dépassant le seuil d'alerte fixé à ±5%.

La calibration inclut la mise à jour des tables de correction de non-uniformité (NUC – Non-Uniformity Correction), la remise à zéro du fichier d'offset thermique, le recalibrage du gain du panneau plat et la vérification des paramètres MUSICA associés au profil d'utilisation « Urgences adultes ».

---

## 2. Actions Réalisées

### Étape 1 — Mise en sécurité et vérification préliminaire (08h30 – 08h50)

Avant toute intervention, l'équipement a été mis en mode veille sécurisée. Vérification visuelle de l'état mécanique du détecteur DR 14s : aucun choc apparent, connectique WiFi/docking intact, voyant de charge batterie à 87%. Connexion au logiciel MUSICA QC via le PC d'acquisition (Windows 10 Professionnel, MUSICA version 3.4.1). Lancement du module de diagnostic « Detector Health Check » : statut initial signalé comme **DEGRADED** sur le canal de correction de gain.

Relevé des valeurs de référence initiales :
- Pixel moyen dark field (sans exposition) : **210 ± 3 ADU** (nominal : 205 ± 5 ADU) ✓
- Pixel moyen flat field (exposition 10 µGy) : **32 410 ADU** (nominal attendu : 29 950 ADU) → **écart : +8,2%** ✗
- Uniformité spatiale (CV) : **3,1%** (seuil acceptable : ≤2,5%) ✗

### Étape 2 — Acquisition des images de calibration Dark Field (09h00 – 09h20)

Le détecteur a été placé dans le berceau de calibration dédié, isolé de toute source lumineuse. Acquisition de **32 images dark field** successives via le module « NUC Calibration Wizard » de MUSICA, conformément à la procédure AGFA référencée **SOP-NUC-DR14-003** (révision 2).

Paramètres d'acquisition dark field :
- Nombre d'images : 32
- Température ambiante enregistrée : **21,4°C**
- Humidité relative : **48%**
- Temps d'acquisition par image : 4 secondes

Résultat : génération du nouveau fichier d'offset thermique `dark_offset_DR14S_FR20220389_20250315.bin`. Valeur moyenne recalculée : **204 ± 2 ADU** — conforme.

### Étape 3 — Acquisition des images de calibration Flat Field (09h25 – 09h55)

Positionnement du tube radiogène à 180 cm de distance foyer-détecteur (DFD). Collimation maximale couvrant la totalité du détecteur 35×43 cm. Utilisation du fantôme de lissage homogène en PMMA (épaisseur 10 mm) pour garantir une exposition uniforme.

Paramètres d'exposition pour le flat field :
- Tension : **70 kV**
- Charge : **5 mAs**
- Filtration additionnelle : 1 mm Cu + 2 mm Al
- Kerma air mesuré au niveau du détecteur : **10,2 µGy** (cible : 10 ± 0,5 µGy) ✓

Acquisition de **16 images flat field** à trois niveaux d'exposition différents (5, 10 et 20 µGy) pour construction de la table de gain multi-niveau. Génération du fichier `gain_table_DR14S_FR20220389_20250315.bin`. Après application de la nouvelle table de gain :
- Pixel moyen flat field (10 µGy) : **29 985 ADU** → écart résiduel : **+0,12%** ✓
- Uniformité spatiale (CV) : **1,8%** ✓

### Étape 4 — Vérification des pixels défectueux et mise à jour de la Dead Pixel Map (10h00 – 10h20)

Exécution de l'algorithme de détection des pixels défectueux intégré à MUSICA. La carte des pixels défectueux (DPM – Dead Pixel Map) a été régénérée et comparée à la DPM de référence datée du 12/09/2024.

Résultats :
- Pixels morts confirmés (inchangés) : **12** (sur 17 614 752 pixels au total, soit 0,00007%) ✓
- Nouveaux pixels défectueux détectés : **3** (en cluster isolé, hors zone d'intérêt anatomique centrale)
- Pixels récupérés : **0**
- DPM mise à jour et enregistrée : `dpm_DR14S_FR20220389_20250315.xml`

Le cluster de 3 pixels défectueux est localisé dans le coin inférieur gauche du détecteur (zone non cliniquement significative). Un signalement est effectué en base de données GMAO pour suivi évolutif à 6 mois.

### Étape 5 — Validation finale et tests de performance (10h25 – 11h00)

Réalisation du protocole de contrôle qualité complet avec le fantôme LEEDS TOR 18FG :
- **Résolution spatiale (MTF à 10%)** : **3,4 paires de lignes/mm** (spécification AGFA : ≥3,0 lp/mm) ✓
- **DQE à 1 lp/mm** : **68%** (spécification : ≥65%) ✓
- **Rapport signal/bruit (SNR)** à 10 µGy : **42,1** (référence : ≥38) ✓
- **Linéarité de réponse** (R²) : **0,9998** (spécification : ≥0,999) ✓
- **Reproductibilité** (5 expositions identiques, CV) : **0,4%** (seuil : ≤1%) ✓

Mise à jour du profil de calibration dans MUSICA et enregistrement du rapport de calibration électronique N° CAL-DR14S-20250315 dans le système documentaire.

---

## 3. Pièces et Consommables Utilisés

| Référence       | Désignation                                   | Quantité | N° de lot     |
|-----------------|-----------------------------------------------|----------|---------------|
| —               | Aucune pièce de rechange requise              | —        | —             |
| AGFA-PMMA-10    | Fantôme PMMA 10 mm (utilisation en prêt)     | 1        | —             |
| LEEDS-TOR18FG   | Fantôme de contrôle qualité (utilisation)     | 1        | —             |

> Intervention réalisée sans remplacement de pièce. La calibration logicielle a suffi à restaurer les performances nominales du détecteur.

---

## 4. Résultat et Conclusion

L'intervention de calibration complète du détecteur AGFA DR 14s (SN : DR14S-FR-20220389) est **réussie**. L'ensemble des paramètres mesurés après calibration sont conformes aux spécifications constructeur et aux exigences du programme de contrôle qualité interne du CHU Bordeaux.

La dérive initiale de +8,2% sur le flat field était due à une dérive progressive des tables de gain liée à l'évolution thermique et à l'usure naturelle du scintillateur CsI après 18 mois d'utilisation intensive. La nouvelle procédure de calibration est programmée tous les **6 mois** (prochaine échéance : 15/09/2025) ou en cas de remplacement de batterie ou de choc mécanique.

**Statut de l'équipement après intervention : OPÉRATIONNEL — Remis en service clinique le 15/03/2025 à 11h15.**

---

## 5. Prochaines Actions Recommandées

- Surveiller l'évolution du cluster de 3 pixels défectueux lors du prochain contrôle qualité trimestriel.
- Envisager le remplacement préventif de la batterie Li-ion du détecteur (cyclecount actuel : 847 cycles / durée de vie estimée : 1200 cycles).
- Mettre à jour le firmware du détecteur vers la version 2.7.0 lors de la prochaine intervention planifiée.

---

## Signature

| Technicien intervenant | Responsable biomédical site |
|------------------------|-----------------------------|
| Jean-Marc Lefèvre      | M. Henri Beaumont           |
| BMET-AQ-2021-0047      | Ingénieur biomédical CHU BX |
| _Signé électroniquement_ | _Visa requis_             |
| 15/03/2025 — 11h05     |                             |

---
*Document généré et archivé dans le GMAO CHU Bordeaux. Référence d'archivage : GMAO-BX-2025-RAP-0315-001.*
