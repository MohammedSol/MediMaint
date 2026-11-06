---
id: MON-COD-001
titre: "Table des alarmes physiologiques — BeneVision N-Series"
reference: "COD-BeneVision-PHYS-2025"
famille: moniteur_multiparametrique
modele: Mindray BeneVision N-Series
type: table_alarmes
sous_type: alarmes_physiologiques
langue: fr
statut: synthetique
date_creation: 2025-01-01
verifie: false
pages_estimees: 6
---

<!-- Physiological Alarm Reference | Mindray BeneVision N-Series -->

# Table des alarmes physiologiques : BeneVision N-Series

Ce recueil détaille les critères d'activation, les priorités normatives (CEI 60601-1-8), les seuils d'usine standards et les conduites à tenir pour les alarmes physiologiques surveillées par les moniteurs Mindray BeneVision N-Series.

| Code alarme | Paramètre | Libellé affiché | Priorité usine | Seuil usine (Adulte) | Condition clinique déclenchante | Action clinique immédiate |
| :---: | :---: | :--- | :---: | :---: | :--- | :--- |
| **AL-P01** | ECG | *ASYSTOLIE* | HAUTE (Latchée) | Pas de QRS pendant > 4 s | Arrêt cardiocirculatoire brutal. | Débuter massage cardiaque (RCP), appel chariot d'urgence. |
| **AL-P02** | ECG | *VFIB / VTACH* | HAUTE (Latchée) | Fibrillation ventriculaire | Fibrillation ou TV rapide sans pouls. | Préparer défibrillation immédiate, vérifier conscience. |
| **AL-P03** | ECG | *FC TROP HAUTE* | HAUTE | FC > 120 bpm | Tachycardie sinusale ou supraventriculaire. | Évaluer cause (douleur, hypovolémie, fièvre). |
| **AL-P04** | ECG | *FC TROP BASSE* | HAUTE | FC < 50 bpm | Bradycardie sévère ou bloc auriculo-ventriculaire. | Préparer atropine / entraînement électrosystolique. |
| **AL-P05** | SpO2 | *SPO2 TROP BASSE* | HAUTE | SpO2 < 90% | Hypoxémie modérée à sévère. | Majorer l'oxygénothérapie, vérifier liberté voies aériennes. |
| **AL-P06** | SpO2 | *DESAT EXTRÊME* | HAUTE (Verrouillée)| SpO2 < 85% | Désaturation critique menaçant le pronostic vital. | Ventilation en O2 pur au ballon auto-remplisseur (BAVU). |
| **AL-P07** | PNI | *SYS TROP HAUTE* | MOYENNE | PNI_Sys > 160 mmHg | Poussée hypertensive aiguë. | Contrôler sédation, administration d'antihypertenseurs. |
| **AL-P08** | PNI | *SYS TROP BASSE* | HAUTE | PNI_Sys < 90 mmHg | Choc hémodynamique, collapsus tensionnel. | Remplissage vasculaire immédiat, recours aux catécholamines. |
| **AL-P09** | PNI | *DIA TROP HAUTE* | MOYENNE | PNI_Dia > 95 mmHg | Résistances vasculaires systémiques élevées. | Évaluation cardiologique approfondie. |
| **AL-P10** | Resp | *APNÉE DÉTECTÉE* | HAUTE | Absence respiration > 20 s | Arrêt respiratoire, obstruction trachéale. | Stimulation du patient, sécurisation voie aérienne. |
| **AL-P11** | Resp | *FR TROP HAUTE* | MOYENNE | FR > 30 rpm | Tachypnée, détresse respiratoire naissante. | Auscultation pulmonaire, gazométrie artérielle. |
| **AL-P12** | Resp | *FR TROP BASSE* | HAUTE | FR < 8 rpm | Dépression respiratoire centrale (ex: surdosage morphinique). | Envisager antagoniste (Naloxone), ventilation assistée. |
| **AL-P13** | Temp | *HYPERTHERMIE* | MOYENNE | T1 / Tcore > 38,5 °C | Syndrome fébrile, choc septique. | Hémocultures, antipyrétiques, refroidissement cutané. |
| **AL-P14** | Temp | *HYPOTHERMIE* | MOYENNE | T1 / Tcore < 35,0 °C | Hypothermie per-opératoire ou accidentelle. | Couverture chauffante à air pulsé, réchauffement perfusions. |
| **AL-P15** | IBP | *PAM TROP BASSE* | HAUTE | P_Art_Moy < 65 mmHg | Pression de perfusion d'organe insuffisante. | Titration des vasopresseurs (Noradrénaline). |
| **AL-P16** | EtCO2 | *HYPERCAPNIE* | MOYENNE | EtCO2 > 50 mmHg | Hypoventilation alvéolaire. | Augmentation du volume courant ou de la fréquence respirateur. |
| **AL-P17** | EtCO2 | *HYPOCAPNIE* | MOYENNE | EtCO2 < 25 mmHg | Hyperventilation ou embolie pulmonaire massive. | Ajustement paramètres ventilation mécanique. |
| **AL-P18** | ECG | *SALVE DE PVC* | MOYENNE | ≥ 3 extrasystoles consécutives | Foyer d'échappement ventriculaire ectopique. | Ionogramme sanguin (recherche hypokaliémie). |

---
*Table des alarmes physiologiques hospitalières MaintiDoc 2025.*
