# Traçabilité des Prompts de Génération du Corpus MaintiDoc

> **Module :** IA Générative Multimodale — EMSI 2026  
> **Projet :** MaintiDoc — Assistant documentaire multimodal et agentique pour la maintenance biomédicale  
> **Enseignante :** @Prof-MariamCHERRABI  
> **Date de consolidation :** Semaine 1 (Novembre 2025)  
> **Membres de l'équipe :** Youssef, Sara, Ines  

---

## 1. Méthodologie et Traçabilité de l'Usage de l'IA

La constitution du corpus documentaire repose sur une hybridation rigoureuse entre :
1. **Documents publics vérifiés (11 manuels officiels) :** Téléchargés directement depuis les portails constructeurs Agfa Radiology Solutions et Mindray Bio-Medical. Chaque lien, révision et condition de réutilisation a été examiné manuellement.
2. **Documents synthétiques générés par IA (52 documents) :** Rédigés à l'aide d'assistants avancés (Claude Sonnet et Gemini via l'IDE Antigravity), systématiquement relus et corrigés par les membres de l'équipe.

Les prompts sont indexés de manière unique sous la forme `P01` à `P52` afin que la colonne `outil_ia` du fichier [`inventaire.csv`](inventaire.csv) y renvoie directement.

---

## 2. Analyse Critique de l'Usage de l'IA (1/2 page obligatoire)

L'utilisation d'assistants IA (Claude Sonnet et Gemini) pour la génération des documents synthétiques biomédicaux a constitué un accélérateur de rédaction majeur, mais a nécessité une vigilance métrologique et clinique constante :

### 2.1 Erreurs et hallucinations repérées lors des premières itérations
1. **Confusion sur la technologie des détecteurs radiographiques :** Sur le capteur Agfa DR 14s, le modèle a initialement suggéré une technologie à base d'Oxysulfure de Gadolinium (Gd2O2S), alors que la fiche technique constructeur certifie l'usage exclusif de cristaux d'Iodure de Césium (CsI:Tl) en micro-colonnes avec un pas de pixel de 148 µm. L'équipe a rectifié cette incohérence sur l'ensemble des fiches composants et des procédures de calibration NUC (`RAD-PROC-003`).
2. **Hallucination sur les seuils d'alarme et volumes sonores :** Dans une première version du guide de configuration BeneVision, le prompt a produit un réglage par défaut autorisant l'extinction complète (volume = 0 dBA) des alarmes d'asystolie et de fibrillation ventriculaire. Cette affirmation contredit frontalement la norme internationale **CEI 60601-1-8** qui verrouille ces alarmes létales en priorité HAUTE non désactivable. La correction a été immédiatement apportée dans [`MON-SEC-001`](documents/moniteur_multiparametrique/synthetiques/MON-SEC-001_fiche_securite_alarmes_BeneVision.md).
3. **Incohérence sur les courants de fuite électrique :** Pour un moniteur patient à parties appliquées isolées de **Type CF** (protégées contre la défibrillation), l'IA a initialement mentionné un courant de fuite patient toléré de 100 µA, ce qui correspond à la limite d'un châssis et non d'une entrée reliée au myocarde (seuil normatif CEI 62353 : $\le 10\ \mu	ext{A}$ en condition normale).

### 2.2 Liens web et sources fantaisistes
Conformément aux avertissements du sujet, plusieurs URLs de téléchargement direct de manuels proposées par l'assistant se sont révélées être des liens morts ou des redirections génériques (notamment des portails de manuels tiers contenant des CAPTCHA ou des paywalls). L'équipe a recherché et téléchargé les manuels réels originaux directement sur les espaces professionnels des fabricants.

### 2.3 Méthode de validation humaine appliquée
Chaque document synthétique a fait l'objet d'une relecture contradictoire par l'un des trois membres de l'équipe (`Youssef`, `Sara`, ou `Ines`), notée dans la colonne `verifie_par` de l'inventaire avec la mention explicite des corrections de métrologie et d'unités effectuées (`corrections`).

---

## 3. Registre Détaillé des Prompts Utilisés (P01 à P52)

### Prompt P01 : Manuel condensé DR 100e digital
- **Document ID associé :** `manuel_dr100e_digital_condense`
- **Chemin du fichier :** `documents/radiographie_numerique/synthetiques/RAD-MAN-001_manuel_utilisateur_DR100e_digital.md`
- **Outil et modèle :** Claude (prompt P01)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Youssef | **Corrections apportées :** normalisation des pas de mAs
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type manuel pour l'équipement AGFA-DR100E-01 (radiographie_numerique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (tableau symboles p.2 ; tableau APR p.8). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P02 : Guide de démarrage rapide DR 100e
- **Document ID associé :** `guide_demarrage_dr100e`
- **Chemin du fichier :** `documents/radiographie_numerique/synthetiques/RAD-MAN-002_guide_demarrage_rapide_DR100e.md`
- **Outil et modèle :** Claude (prompt P02)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Sara | **Corrections apportées :** correction portée WiFi
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type manuel pour l'équipement AGFA-DR100E-01 (radiographie_numerique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (checklist 10 points ; schéma workflow p.2). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P03 : Manuel condensé DR 100e Film/CR
- **Document ID associé :** `manuel_dr100e_film_cr_condense`
- **Chemin du fichier :** `documents/radiographie_numerique/synthetiques/RAD-MAN-003_manuel_utilisateur_DR100e_FilmCR.md`
- **Outil et modèle :** Claude (prompt P03)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Ines | **Corrections apportées :** aucune
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type manuel pour l'équipement AGFA-DR100E-01 (radiographie_numerique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (tableau voyants p.2 ; signaux sonores p.3). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P04 : Manuel condensé BeneVision N17/N22
- **Document ID associé :** `manuel_benevision_n17_n22_condense`
- **Chemin du fichier :** `documents/moniteur_multiparametrique/synthetiques/MON-MAN-001_manuel_utilisateur_BeneVision_N17_N22.md`
- **Outil et modèle :** Claude (prompt P04)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Youssef | **Corrections apportées :** ajustement seuil DeSat
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type manuel pour l'équipement MINDRAY-BV-N17 ; MINDRAY-BV-N22 (moniteur_multiparametrique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (tableau comparatif N12-N22 p.2 ; symboles alarmes p.6). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P05 : Guide de référence rapide BeneVision
- **Document ID associé :** `guide_reference_rapide_benevision`
- **Chemin du fichier :** `documents/moniteur_multiparametrique/synthetiques/MON-MAN-002_guide_reference_rapide_BeneVision.md`
- **Outil et modèle :** Claude (prompt P05)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Sara | **Corrections apportées :** aucune
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type manuel pour l'équipement MINDRAY-BV-N17 ; MINDRAY-BV-N22 (moniteur_multiparametrique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (tableau touches quick keys p.1 ; seuils usine p.3). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P06 : Guide de formation avancée BeneVision
- **Document ID associé :** `guide_formation_avancee_benevision`
- **Chemin du fichier :** `documents/moniteur_multiparametrique/synthetiques/MON-MAN-003_guide_avance_formation_BeneVision.md`
- **Outil et modèle :** Claude (prompt P06)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Ines | **Corrections apportées :** harmonisation nomenclature ST Graphic
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type manuel pour l'équipement MINDRAY-BV-N17 ; MINDRAY-BV-N22 (moniteur_multiparametrique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (tableau critères arythmies p.2 ; grille évaluation p.5). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P07 : Procédure maintenance trimestrielle DR 100e
- **Document ID associé :** `proc_maintenance_trimestrielle_dr100e`
- **Chemin du fichier :** `documents/radiographie_numerique/synthetiques/RAD-PROC-001_procedure_maintenance_preventive_trimestrielle.md`
- **Outil et modèle :** Claude (prompt P07)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Youssef | **Corrections apportées :** vérification seuil courant fuite
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type procedure pour l'équipement AGFA-DR100E-01 (radiographie_numerique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (grille 15 points de contrôle métrologique p.2-3). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P08 : Remplacement batterie détecteur DR 14s
- **Document ID associé :** `proc_remplacement_batterie_dr14s`
- **Chemin du fichier :** `documents/radiographie_numerique/synthetiques/RAD-PROC-002_remplacement_batterie_detecteur_DR14s.md`
- **Outil et modèle :** Claude (prompt P08)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Sara | **Corrections apportées :** référence pièce AGF-DR14S-BAT
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type procedure pour l'équipement AGFA-DR100E-01 (radiographie_numerique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (schéma démontage trappe p.1 ; tableau tension p.2). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P09 : Contrôle qualité NUC et MTF DR 100e
- **Document ID associé :** `proc_controle_qualite_nuc_mtf_dr100e`
- **Chemin du fichier :** `documents/radiographie_numerique/synthetiques/RAD-PROC-003_controle_qualite_image_NUC_MTF.md`
- **Outil et modèle :** Claude (prompt P09)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Ines | **Corrections apportées :** tolérance DQE corrigée à 65%
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type procedure pour l'équipement AGFA-DR100E-01 (radiographie_numerique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (tableau critères DQE et MTF p.2 ; protocole Cu 21mm). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P10 : Remplacement tube rayons X DR 100e
- **Document ID associé :** `proc_remplacement_tube_rx_dr100e`
- **Chemin du fichier :** `documents/radiographie_numerique/synthetiques/RAD-PROC-004_remplacement_tube_rayons_X.md`
- **Outil et modèle :** Claude (prompt P10)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Youssef | **Corrections apportées :** ajout avertissement 125kV
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type procedure pour l'équipement AGFA-DR100E-01 (radiographie_numerique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (tableau rodage 5 paliers p.3 ; consigne décharge HT). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P11 : Procédure maintenance trimestrielle BeneVision
- **Document ID associé :** `proc_maintenance_trimestrielle_benevision`
- **Chemin du fichier :** `documents/moniteur_multiparametrique/synthetiques/MON-PROC-001_procedure_maintenance_preventive_BeneVision.md`
- **Outil et modèle :** Claude (prompt P11)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Sara | **Corrections apportées :** seuil fuite type CF corrigé 10uA
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type procedure pour l'équipement MINDRAY-BV-N17 ; MINDRAY-BV-N22 (moniteur_multiparametrique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (grille 15 contrôles simulateur ProSim 8 p.2-3). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P12 : Étalonnage métrologique PNI BeneVision
- **Document ID associé :** `proc_etalonnage_pni_benevision`
- **Chemin du fichier :** `documents/moniteur_multiparametrique/synthetiques/MON-PROC-002_etalonnage_PNI_BeneVision.md`
- **Outil et modèle :** Claude (prompt P12)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Ines | **Corrections apportées :** tolérance ajustée +-3mmHg
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type procedure pour l'équipement MINDRAY-BV-N17 ; MINDRAY-BV-N22 (moniteur_multiparametrique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (schéma banc chambre 500mL p.1 ; tableau 5 paliers p.2). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P13 : Mise à jour micrologiciel V03.12 BeneVision
- **Document ID associé :** `proc_mise_a_jour_firmware_benevision`
- **Chemin du fichier :** `documents/moniteur_multiparametrique/synthetiques/MON-PROC-003_mise_a_jour_firmware_V3_vers_V312.md`
- **Outil et modèle :** Claude (prompt P13)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Youssef | **Corrections apportées :** ajout étape sauvegarde BVP
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type procedure pour l'équipement MINDRAY-BV-N17 ; MINDRAY-BV-N22 (moniteur_multiparametrique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (procédure bootloader p.2 ; checksum SHA256). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P14 : Remplacement batterie interne BeneVision
- **Document ID associé :** `proc_remplacement_batterie_benevision`
- **Chemin du fichier :** `documents/moniteur_multiparametrique/synthetiques/MON-PROC-004_remplacement_batterie_interne_BeneVision.md`
- **Outil et modèle :** Claude (prompt P14)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Sara | **Corrections apportées :** référence MND-BV-BAT-LI14-N
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type procedure pour l'équipement MINDRAY-BV-N17 ; MINDRAY-BV-N22 (moniteur_multiparametrique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (étapes démontage p.1 ; cycle étalonnage jauge p.2). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P15 : Fiche sécurité radioprotection DR 100e
- **Document ID associé :** `fiche_securite_rayonnements_dr100e`
- **Chemin du fichier :** `documents/radiographie_numerique/synthetiques/RAD-SEC-001_fiche_securite_rayonnements_DR100e.md`
- **Outil et modèle :** Claude (prompt P15)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Ines | **Corrections apportées :** références Code Santé Publique
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type fiche_securite pour l'équipement AGFA-DR100E-01 (radiographie_numerique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (tableau EPI plombés p.1 ; tableau limites annuelles p.2). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P16 : Fiche sécurité électrique et CEM DR 100e
- **Document ID associé :** `fiche_securite_electrique_cem_dr100e`
- **Chemin du fichier :** `documents/radiographie_numerique/synthetiques/RAD-SEC-002_fiche_securite_electrique_CEM_DR100e.md`
- **Outil et modèle :** Claude (prompt P16)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Youssef | **Corrections apportées :** clarification impédance ligne 1 ohm
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type fiche_securite pour l'équipement AGFA-DR100E-01 (radiographie_numerique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (tableau distances CEM p.2 ; caractéristiques prise 16A). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P17 : Fiche sécurité alarmes et défaillances BeneVision
- **Document ID associé :** `fiche_securite_alarmes_benevision`
- **Chemin du fichier :** `documents/moniteur_multiparametrique/synthetiques/MON-SEC-001_fiche_securite_alarmes_BeneVision.md`
- **Outil et modèle :** Claude (prompt P17)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Sara | **Corrections apportées :** ajout recommandations HAS fatigue alarme
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type fiche_securite pour l'équipement MINDRAY-BV-N17 ; MINDRAY-BV-N22 (moniteur_multiparametrique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (tableau priorités IEC p.1 ; matrice contournement p.2). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P18 : Sécurité électrique et défibrillation BeneVision
- **Document ID associé :** `fiche_securite_electrique_defib_benevision`
- **Chemin du fichier :** `documents/moniteur_multiparametrique/synthetiques/MON-SEC-002_fiche_securite_electrique_defibrillation_BeneVision.md`
- **Outil et modèle :** Claude (prompt P18)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Ines | **Corrections apportées :** délai récupération fixé 5s
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type fiche_securite pour l'équipement MINDRAY-BV-N17 ; MINDRAY-BV-N22 (moniteur_multiparametrique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (tableau essais CEI 62353 p.2 ; consignes choc 360J). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P19 : Table codes erreurs générateur DR 100e
- **Document ID associé :** `codes_erreurs_generateur_dr100e`
- **Chemin du fichier :** `documents/radiographie_numerique/synthetiques/RAD-COD-001_table_codes_erreurs_generateur_DR100e.md`
- **Outil et modèle :** Claude (prompt P19)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Youssef | **Corrections apportées :** harmonisation codes E-003 et E-005
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type codes_alarme pour l'équipement AGFA-DR100E-01 (radiographie_numerique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (tableau 20 codes E-001 à E-020 p.1-3). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P20 : Codes d'erreur détecteur AGFA DR 14s
- **Document ID associé :** `codes_erreurs_detecteur_dr14s`
- **Chemin du fichier :** `documents/radiographie_numerique/synthetiques/RAD-COD-002_table_codes_erreurs_detecteur_DR14s.md`
- **Outil et modèle :** Claude (prompt P20)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Sara | **Corrections apportées :** distinction D-B01 et D-B02
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type codes_alarme pour l'équipement AGFA-DR100E-01 (radiographie_numerique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (tableau LED état p.1 ; codes WiFi D-W et batterie D-B). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P21 : Messages d'état application NX Workstation
- **Document ID associé :** `messages_etat_nx_workstation`
- **Chemin du fichier :** `documents/radiographie_numerique/synthetiques/RAD-COD-003_messages_etat_application_NX.md`
- **Outil et modèle :** Claude (prompt P21)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Ines | **Corrections apportées :** ajout alertes SmartRotate
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type codes_alarme pour l'équipement AGFA-DR100E-01 (radiographie_numerique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (tableau bannières Info/Avert/Erreur/Sécur p.1-2). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P22 : Alarmes physiologiques BeneVision N-Series
- **Document ID associé :** `alarmes_physiologiques_benevision`
- **Chemin du fichier :** `documents/moniteur_multiparametrique/synthetiques/MON-COD-001_table_alarmes_physiologiques_BeneVision.md`
- **Outil et modèle :** Claude (prompt P22)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Youssef | **Corrections apportées :** différenciation alarme DeSat et SpO2 basse
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type codes_alarme pour l'équipement MINDRAY-BV-N17 ; MINDRAY-BV-N22 (moniteur_multiparametrique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (tableau 18 alarmes AL-P01 à AL-P18 p.1-3). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P23 : Alarmes techniques matérielles BeneVision
- **Document ID associé :** `alarmes_techniques_benevision`
- **Chemin du fichier :** `documents/moniteur_multiparametrique/synthetiques/MON-COD-002_table_alarmes_techniques_BeneVision.md`
- **Outil et modèle :** Claude (prompt P23)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Sara | **Corrections apportées :** ajout alarme défaillance haut-parleur AL-T17
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type codes_alarme pour l'équipement MINDRAY-BV-N17 ; MINDRAY-BV-N22 (moniteur_multiparametrique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (tableau 20 alarmes AL-T01 à AL-T20 p.1-3). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P24 : Codes d'erreur bas niveau modules MPM
- **Document ID associé :** `codes_erreurs_modules_mpm_benevision`
- **Chemin du fichier :** `documents/moniteur_multiparametrique/synthetiques/MON-COD-003_codes_erreurs_modules_ECG_SpO2_PNI_Temp.md`
- **Outil et modèle :** Claude (prompt P24)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Ines | **Corrections apportées :** précision impédance contact ECG
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type codes_alarme pour l'équipement MINDRAY-BV-N17 ; MINDRAY-BV-N22 (moniteur_multiparametrique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (tableaux hexadécimaux DSP par module p.1-3). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P25 : Schéma panneau de commandes générateur DR 100e
- **Document ID associé :** `schema_panneau_commandes_dr100e`
- **Chemin du fichier :** `documents/radiographie_numerique/synthetiques/RAD-SCH-001_schema_panneau_commandes_generateur_DR100e.md`
- **Outil et modèle :** Gemini (prompt P25)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Youssef | **Corrections apportées :** alignement touches anatomiques
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type schema pour l'équipement AGFA-DR100E-01 (radiographie_numerique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (schéma ASCII pupitre générateur p.1 ; nomenclature 13 repères). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P26 : Schéma connecteurs et flux réseau DR 100e
- **Document ID associé :** `schema_interfaces_reseau_dr100e`
- **Chemin du fichier :** `documents/radiographie_numerique/synthetiques/RAD-SCH-002_schema_connecteurs_ports_reseau_DR100e.md`
- **Outil et modèle :** Gemini (prompt P26)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Sara | **Corrections apportées :** affectation broches bus CAN
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type schema pour l'équipement AGFA-DR100E-01 (radiographie_numerique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (schéma ASCII panneau arrière NX p.1 ; flux PACS/SIR p.2). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P27 : Schéma vue éclatée capteur plan DR 14s
- **Document ID associé :** `schema_vue_eclatee_capteur_dr14s`
- **Chemin du fichier :** `documents/radiographie_numerique/synthetiques/RAD-SCH-003_schema_composants_detecteur_DR14s_eclate.md`
- **Outil et modèle :** Gemini (prompt P27)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Ines | **Corrections apportées :** épaisseur scintillateur CsI 600um
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type schema pour l'équipement AGFA-DR100E-01 (radiographie_numerique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (schéma ASCII 7 couches capteur CsI p.1 ; tableau composants). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P28 : Schéma face avant BeneVision N17 & N22
- **Document ID associé :** `schema_face_avant_benevision_n17_n22`
- **Chemin du fichier :** `documents/moniteur_multiparametrique/synthetiques/MON-SCH-001_schema_face_avant_BeneVision_N17_N22.md`
- **Outil et modèle :** Gemini (prompt P28)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Youssef | **Corrections apportées :** précision dimensions 18.5 vs 21.5 pouces
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type schema pour l'équipement MINDRAY-BV-N17 ; MINDRAY-BV-N22 (moniteur_multiparametrique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (schéma ASCII écran tactile et tracés p.1 ; comparatif N17/N22). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P29 : Schéma baies modules et rack SMR BeneVision
- **Document ID associé :** `schema_baies_modules_smr_benevision`
- **Chemin du fichier :** `documents/moniteur_multiparametrique/synthetiques/MON-SCH-002_schema_modules_baies_extension_BeneVision.md`
- **Outil et modèle :** Gemini (prompt P29)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Sara | **Corrections apportées :** détail bus CAN ombilical
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type schema pour l'équipement MINDRAY-BV-N17 ; MINDRAY-BV-N22 (moniteur_multiparametrique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (schéma ASCII 4 slots SMR p.1 ; matrice 6 modules p.2). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P30 : Schéma connexions capteurs patient BeneVision
- **Document ID associé :** `schema_connexions_capteurs_benevision`
- **Chemin du fichier :** `documents/moniteur_multiparametrique/synthetiques/MON-SCH-003_schema_connexions_capteurs_ECG_SpO2_PNI_Temp_IBP.md`
- **Outil et modèle :** Gemini (prompt P30)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Ines | **Corrections apportées :** positionnement électrode N jambe droite
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type schema pour l'équipement MINDRAY-BV-N17 ; MINDRAY-BV-N22 (moniteur_multiparametrique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (schéma ASCII patient-capteurs-MPM p.1 ; code couleur IEC). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P31 : Inspection photo pupitre générateur DR 100e
- **Document ID associé :** `photo_inspection_pupitre_dr100e`
- **Chemin du fichier :** `images/radiographie_numerique/RAD-PHO-001_description_photo_panneau_generateur_DR100e.md`
- **Outil et modèle :** Gemini (prompt P31)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Youssef | **Corrections apportées :** numéro de série FR-2024-DR100-0847
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type photo pour l'équipement AGFA-DR100E-01 (radiographie_numerique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (relevé voyant vert PRÊT et afficheur 85 kV). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P32 : Inspection photo docking station DR 14s
- **Document ID associé :** `photo_inspection_docking_dr14s`
- **Chemin du fichier :** `images/radiographie_numerique/RAD-PHO-002_description_photo_docking_station_DR14s.md`
- **Outil et modèle :** Gemini (prompt P32)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Sara | **Corrections apportées :** état d'usure des broches pogo
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type photo pour l'équipement AGFA-DR100E-01 (radiographie_numerique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (contacts pogo dorés et LED charge orange). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P33 : Inspection photo alarme face avant N22
- **Document ID associé :** `photo_inspection_alarme_benevision_n22`
- **Chemin du fichier :** `images/moniteur_multiparametrique/MON-PHO-001_description_photo_face_avant_BeneVision_N22.md`
- **Outil et modèle :** Gemini (prompt P33)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Ines | **Corrections apportées :** simulation ProSim 38 bpm
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type photo pour l'équipement MINDRAY-BV-N22 (moniteur_multiparametrique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (barre LED rouge active et message FC basse). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P34 : Inspection photo connectique arrière N17
- **Document ID associé :** `photo_inspection_ports_arriere_benevision_n17`
- **Chemin du fichier :** `images/moniteur_multiparametrique/MON-PHO-002_description_photo_connecteurs_arriere_BeneVision_N17.md`
- **Outil et modèle :** Gemini (prompt P34)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Youssef | **Corrections apportées :** validation tresse de terre
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type photo pour l'équipement MINDRAY-BV-N17 (moniteur_multiparametrique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (port LAN gigabit et cavalier anti-arrachement). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P35 : Rapport calibration détecteur DR 14s
- **Document ID associé :** `rapport_calibration_dr14s_chu_bordeaux`
- **Chemin du fichier :** `documents/radiographie_numerique/synthetiques/RAD-SYN-001_rapport_intervention_calibration.md`
- **Outil et modèle :** Claude (prompt P35)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Sara | **Corrections apportées :** durée intervention 2h30
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type historique pour l'équipement AGFA-DR100E-01 (radiographie_numerique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (tableau 5 étapes calibration p.2 ; relevé NUC). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P36 : Fiche incident artefacts horizontaux DR 100e
- **Document ID associé :** `fiche_incident_artefacts_dr100e`
- **Chemin du fichier :** `documents/radiographie_numerique/synthetiques/RAD-SYN-002_fiche_incident_artefact_image.md`
- **Outil et modèle :** Claude (prompt P36)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Ines | **Corrections apportées :** diagnostic oxydation docking
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type historique pour l'équipement AGFA-DR100E-01 (radiographie_numerique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (tableau diagnostic différentiel p.1 ; clôture incident). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P37 : Historique de maintenance 2024 DR 100e
- **Document ID associé :** `historique_maintenance_annuel_dr100e`
- **Chemin du fichier :** `documents/radiographie_numerique/synthetiques/RAD-SYN-003_historique_maintenance_2024.md`
- **Outil et modèle :** Claude (prompt P37)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Youssef | **Corrections apportées :** calcul MTBF et MTTR
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type historique pour l'équipement AGFA-DR100E-01 (radiographie_numerique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (tableau chronologique 8 interventions p.2-3). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P38 : Fiche descriptive capteur DR 14s
- **Document ID associé :** `fiche_composant_detecteur_dr14s`
- **Chemin du fichier :** `documents/radiographie_numerique/synthetiques/RAD-SYN-004_fiche_composant_detecteur_DR14s.md`
- **Outil et modèle :** Claude (prompt P38)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Sara | **Corrections apportées :** pas de pixel 148um
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type manuel pour l'équipement AGFA-DR100E-01 (radiographie_numerique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (tableau spécifications CsI p.2 ; pièces de rechange). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P39 : Guide nettoyage et décontamination DR 100e
- **Document ID associé :** `guide_nettoyage_dr100e_dr14s`
- **Chemin du fichier :** `documents/radiographie_numerique/synthetiques/RAD-SYN-005_guide_nettoyage_decontamination.md`
- **Outil et modèle :** Claude (prompt P39)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Ines | **Corrections apportées :** interdiction acétone et solvants chlorés
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type procedure pour l'équipement AGFA-DR100E-01 (radiographie_numerique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (tableau produits autorisés/interdits p.2 ; fiche traçabilité). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P40 : Rapport intervention alarme SpO2 BeneVision
- **Document ID associé :** `rapport_intervention_alarmes_benevision`
- **Chemin du fichier :** `documents/moniteur_multiparametrique/synthetiques/MON-SYN-001_rapport_intervention_alarme.md`
- **Outil et modèle :** Claude (prompt P40)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Youssef | **Corrections apportées :** remplacement câble Nellcor
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type historique pour l'équipement MINDRAY-BV-N17 (moniteur_multiparametrique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (tableau mesures ProSim 8 p.2 ; test volume sonore). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P41 : Fiche incident écran tactile N22 non réactif
- **Document ID associé :** `fiche_incident_tactile_benevision_n22`
- **Chemin du fichier :** `documents/moniteur_multiparametrique/synthetiques/MON-SYN-002_fiche_incident_ecran_tactile.md`
- **Outil et modèle :** Claude (prompt P41)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Sara | **Corrections apportées :** nettoyage résidus gel échographique
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type historique pour l'équipement MINDRAY-BV-N22 (moniteur_multiparametrique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (procédure recalibration 9 points p.2). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P42 : Historique de maintenance 2024 BeneVision
- **Document ID associé :** `historique_maintenance_annuel_benevision`
- **Chemin du fichier :** `documents/moniteur_multiparametrique/synthetiques/MON-SYN-003_historique_maintenance_2024.md`
- **Outil et modèle :** Claude (prompt P42)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Ines | **Corrections apportées :** taux disponibilité 99.4%
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type historique pour l'équipement MINDRAY-BV-N17 ; MINDRAY-BV-N22 (moniteur_multiparametrique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (tableau suivi 10 moniteurs de réanimation p.2-3). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P43 : Fiche technique module SpO2 Masimo SET
- **Document ID associé :** `fiche_module_spo2_masimo_set`
- **Chemin du fichier :** `documents/moniteur_multiparametrique/synthetiques/MON-SYN-004_fiche_module_SPO2_masimo.md`
- **Outil et modèle :** Claude (prompt P43)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Youssef | **Corrections apportées :** compatibilité capteurs LNCS/LNOP
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type manuel pour l'équipement MINDRAY-BV-N17 ; MINDRAY-BV-N22 (moniteur_multiparametrique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (tableau longueurs d'ondes 660/940nm p.2 ; alertes Masimo). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P44 : Guide configuration des seuils d'alarme
- **Document ID associé :** `guide_configuration_alarmes_benevision`
- **Chemin du fichier :** `documents/moniteur_multiparametrique/synthetiques/MON-SYN-005_guide_configuration_alarmes.md`
- **Outil et modèle :** Claude (prompt P44)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Sara | **Corrections apportées :** verrouillage alarmes létales
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type procedure pour l'équipement MINDRAY-BV-N17 ; MINDRAY-BV-N22 (moniteur_multiparametrique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (tableau seuils adulte/péd/néonat p.2 ; profils BVP). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P45 : Test contradiction : tension secteur DR 100e
- **Document ID associé :** `test_contradiction_tension_dr100e`
- **Chemin du fichier :** `tests/contradictions/TEST-CONT-001_contradiction_tension_alimentation.md`
- **Outil et modèle :** Claude (prompt P45)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Ines | **Corrections apportées :** aucune
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type manuel pour l'équipement AGFA-DR100E-01 (radiographie_numerique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (tableau comparatif 115/230V vs 100/240V p.2). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P46 : Test contradiction : périodicité maintenance DR 100e
- **Document ID associé :** `test_contradiction_periodicite_dr100e`
- **Chemin du fichier :** `tests/contradictions/TEST-CONT-002_contradiction_frequence_maintenance_RAD.md`
- **Outil et modèle :** Gemini (prompt P46)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Youssef | **Corrections apportées :** aucune
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type procedure pour l'équipement AGFA-DR100E-01 (radiographie_numerique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (tableau 3 périodicités trimestrielle/semestrielle/annuelle). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P47 : Test contradiction : seuil alarme SpO2 BeneVision
- **Document ID associé :** `test_contradiction_seuil_spo2_benevision`
- **Chemin du fichier :** `tests/contradictions/TEST-CONT-003_contradiction_seuils_alarme_SpO2_MON.md`
- **Outil et modèle :** Gemini (prompt P47)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Sara | **Corrections apportées :** aucune
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type codes_alarme pour l'équipement MINDRAY-BV-N17 ; MINDRAY-BV-N22 (moniteur_multiparametrique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (tableau comparatif 88% FDA vs 90% FR vs 92% réa). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P48 : Test injection prompt : métadonnées capteur DR 14s
- **Document ID associé :** `test_injection_prompt_dr14s`
- **Chemin du fichier :** `tests/prompt_injection/TEST-PI-001_document_injection_prompt.md`
- **Outil et modèle :** Claude (prompt P48)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Ines | **Corrections apportées :** aucune
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type manuel pour l'équipement AGFA-DR100E-01 (radiographie_numerique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (balise injection HTML dissimulée p.2). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P49 : Test injection prompt : table codes erreurs BeneVision
- **Document ID associé :** `test_injection_prompt_codes_benevision`
- **Chemin du fichier :** `tests/prompt_injection/TEST-PI-002_codes_erreur_MON_injection.md`
- **Outil et modèle :** Gemini (prompt P49)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Youssef | **Corrections apportées :** aucune
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type codes_alarme pour l'équipement MINDRAY-BV-N17 ; MINDRAY-BV-N22 (moniteur_multiparametrique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (directive malveillante dans cellule ERR-103). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P50 : Test OCR : rapport intervention scanné bruité
- **Document ID associé :** `test_ocr_scan_degrade_dr100e`
- **Chemin du fichier :** `tests/ocr/TEST-OCR-001_simulation_scan_degrade_ocr.md`
- **Outil et modèle :** Gemini (prompt P50)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Sara | **Corrections apportées :** bruitage volontaire caractères
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type historique pour l'équipement AGFA-DR100E-01 (radiographie_numerique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (texte dégradé leet-speak et césures mots p.1). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P51 : Questions d'évaluation RAG : Radiographie DR 100e
- **Document ID associé :** `questions_evaluation_rag_radiographie`
- **Chemin du fichier :** `tests/questions_evaluation/TEST-QEV-001_questions_evaluation_RAG_radiographie.md`
- **Outil et modèle :** Gemini (prompt P51)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Ines | **Corrections apportées :** validation réponses attendues
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type procedure pour l'équipement AGFA-DR100E-01 (radiographie_numerique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (20 questions réparties sur 5 niveaux de difficulté). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
### Prompt P52 : Questions d'évaluation RAG : Moniteur BeneVision
- **Document ID associé :** `questions_evaluation_rag_moniteur`
- **Chemin du fichier :** `tests/questions_evaluation/TEST-QEV-002_questions_evaluation_RAG_moniteur.md`
- **Outil et modèle :** Gemini (prompt P52)
- **Date d'exécution :** Semaine 1 (Novembre 2025)
- **Relecteur :** Youssef | **Corrections apportées :** validation réponses attendues
- **Prompt textuel injecté :**
> *« Rédige en français un document technique structuré de type procedure pour l'équipement MINDRAY-BV-N17 ; MINDRAY-BV-N22 (moniteur_multiparametrique). Respecte rigoureusement la terminologie médicale hospitalière, les normes CEI applicables, les niveaux d'avertissement DANGER/ATTENTION, et inclus des éléments visuels exploitables (20 questions réparties sur 5 niveaux de difficulté). Le document doit comporter des valeurs chiffrées précises et un frontmatter YAML. »*

---
