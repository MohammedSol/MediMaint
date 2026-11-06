---
id: MON-SYN-005
titre: Guide de configuration des alarmes – Mindray BeneVision N17/N22
famille: moniteur_multiparametrique
modele: Mindray BeneVision N-Series
fabricant: Mindray
type: guide
langue: fr
statut: synthetique
date_creation: 2025-01-15
verifie: false
pages_estimees: 4
---

# Guide de Configuration des Alarmes
## Mindray BeneVision N17/N22

---

> **⚠️ DOCUMENT RÉSERVÉ AU PERSONNEL HABILITÉ** — La configuration des alarmes doit être réalisée ou validée par un professionnel de santé formé et/ou le technicien biomédical. Une alarme incorrectement configurée peut constituer un risque direct pour la vie des patients.

---

## 1. Introduction — Importance des Alarmes en Clinique

Les alarmes des moniteurs multiparamétriques constituent le premier filet de sécurité pour la détection des dégradations soudaines de l'état d'un patient. Sur les unités de soins intensifs, de réanimation et les blocs opératoires, le moniteur est l'unique source d'alerte entre deux passages infirmiers : un défaut d'alarme ou un réglage inadapté peut aboutir à un retard de prise en charge aux conséquences graves.

La Haute Autorité de Santé (HAS) et la Joint Commission International (JCI) ont identifié la **mauvaise gestion des alarmes** comme l'une des causes les plus fréquentes d'incidents évitables en établissements de santé. Le phénomène de « fatigue aux alarmes » — provoqué par un excès de fausses alarmes — est également reconnu comme un risque majeur : un personnel épuisé par des alarmes intempestives tend à inhiber ou ignorer les alertes, y compris les alertes pertinentes.

Une politique d'alarme bien conçue doit donc équilibrer deux impératifs contradictoires :
- **Sensibilité suffisante** : ne manquer aucun événement cliniquement significatif.
- **Spécificité suffisante** : limiter les fausses alarmes pour maintenir l'attention des soignants.

Le Mindray BeneVision N17/N22 offre un système d'alarme hautement configurable permettant d'adapter les seuils à chaque type de patient et à chaque contexte clinique.

---

## 2. Paramètres Configurables

Le BeneVision N17/N22 permet la configuration d'alarmes sur les paramètres vitaux suivants :

| Paramètre          | Désignation                        | Niveaux d'alarme configurables           | Délai d'alarme ajustable |
|--------------------|------------------------------------|------------------------------------------|--------------------------|
| **SpO2**           | Saturation en oxygène              | Seuil bas, seuil très bas               | Oui (5–60 s)             |
| **FC**             | Fréquence cardiaque                | Seuil bas, seuil haut, seuil très bas    | Oui (5–30 s)             |
| **PNI Sys.**       | Pression artérielle systolique     | Seuil bas, seuil haut                   | Non (mesure ponctuelle)  |
| **PNI Dias.**      | Pression artérielle diastolique    | Seuil bas, seuil haut                   | Non (mesure ponctuelle)  |
| **PNI MAP**        | Pression artérielle moyenne        | Seuil bas, seuil haut                   | Non (mesure ponctuelle)  |
| **FR**             | Fréquence respiratoire             | Seuil bas, seuil haut, apnée            | Oui (10–60 s)            |
| **Température**    | Température corporelle             | Seuil bas, seuil haut                   | Oui (non ajustable)      |
| **ECG**            | Morphologie et rythme              | Arythmies (liste sélectionnable)         | Oui (selon arythmie)     |
| **EtCO2**          | CO₂ expiré (N22 avec capno)        | Seuil bas, seuil haut, apnée             | Oui                      |
| **IBP**            | Pression invasive (N22)            | Seuil systolique/diastolique/MAP         | Oui                      |

---

## 3. Tableau des Seuils Recommandés par Type de Patient

Le tableau suivant présente les **valeurs de seuils recommandées** par la politique d'alarme de la Clinique Saint-Louis (réf. POL-CLIN-SL-ALARM-V3-2024), conformes aux recommandations de la SFAR (Société Française d'Anesthésie-Réanimation) et aux préréglages usine Mindray.

> Ces valeurs sont indicatives et doivent être adaptées par le médecin responsable à la situation clinique individuelle de chaque patient.

| Paramètre         | Seuil            | Adulte (> 15 ans)    | Pédiatrique (1–15 ans) | Néonatal (< 1 mois) |
|-------------------|------------------|----------------------|------------------------|----------------------|
| **SpO2**          | Bas              | **92%**              | 93%                    | 93%                  |
|                   | Très bas         | 85%                  | 88%                    | 88%                  |
| **FC**            | Bas              | 50 bpm               | 60 bpm                 | 100 bpm              |
|                   | Haut             | 120 bpm              | 160 bpm                | 200 bpm              |
|                   | Très bas         | 40 bpm               | 50 bpm                 | 80 bpm               |
| **PNI Sys.**      | Bas              | 90 mmHg              | 70 mmHg                | 55 mmHg              |
|                   | Haut             | 180 mmHg             | 140 mmHg               | 90 mmHg              |
| **PNI Dias.**     | Bas              | 50 mmHg              | 40 mmHg                | 30 mmHg              |
|                   | Haut             | 110 mmHg             | 90 mmHg                | 60 mmHg              |
| **FR**            | Bas              | 8 cycles/min         | 12 cycles/min          | 25 cycles/min        |
|                   | Haut             | 30 cycles/min        | 40 cycles/min          | 70 cycles/min        |
|                   | Apnée            | 20 s                 | 20 s                   | 15 s                 |
| **Température**   | Bas              | 36,0°C               | 36,0°C                 | 36,5°C               |
|                   | Haut             | 38,5°C               | 38,5°C                 | 37,8°C               |

---

## 4. Procédure de Configuration Pas à Pas

### Pré-requis

- Être connecté avec un compte utilisateur de niveau **Infirmier superviseur** ou **Technicien biomédical** (accès au menu de configuration complet).
- Connaître le profil patient à configurer (adulte / pédiatrique / néonatal).
- Avoir pris connaissance de la prescription médicale et des objectifs thérapeutiques pour le patient concerné.

### Étape 1 — Accès au menu de configuration des alarmes

Sur le BeneVision N17/N22, depuis l'écran principal :
1. Appuyer sur la touche physique **[Alarme]** (icône cloche) sur le panneau avant **OU** appuyer sur l'icône **[Paramètre]** dans la barre d'état supérieure.
2. Sélectionner **[Réglages alarmes]** dans le menu contextuel.
3. Si un code d'accès est demandé, saisir le code superviseur (4 chiffres, défini lors de la configuration initiale par le biomédical — voir SOP-MON-CONFIG-001).
4. L'écran de configuration des alarmes s'affiche avec la liste de tous les paramètres configurables.

### Étape 2 — Sélection du profil patient

5. Dans l'onglet **[Profil patient]**, sélectionner le profil correspondant :
   - **Adulte** : pour patients > 15 ans et > 30 kg
   - **Pédiatrique** : pour patients de 1 à 15 ans
   - **Néonatal** : pour patients < 1 mois ou < 5 kg
6. La sélection d'un profil charge automatiquement les seuils par défaut du profil. Ces seuils peuvent ensuite être personnalisés à l'étape suivante.

### Étape 3 — Configuration des seuils SpO2

7. Sélectionner **[SpO2]** dans la liste des paramètres.
8. L'écran SpO2 affiche les curseurs de réglage :
   - Faire glisser le curseur **[Seuil bas SpO2]** à la valeur souhaitée (ex. : 92% pour un adulte en USIC). Confirmer avec le bouton rotatif ou en appuyant sur la valeur.
   - Faire glisser le curseur **[Seuil très bas SpO2]** (ex. : 85%). Ce seuil déclenche une alarme de priorité haute (rouge + son fort).
   - Régler le **délai d'alarme SpO2** : valeur recommandée 10 secondes (évite les fausses alarmes sur artefacts de mouvement de courte durée).
9. Vérifier que l'option **[Alarme SpO2 active]** est cochée (case verte).

### Étape 4 — Configuration des seuils FC et PNI

10. Sélectionner **[Fréquence cardiaque]** : régler seuil bas, seuil haut et seuil très bas selon le tableau section 3.
11. Sélectionner **[PNI]** : régler séparément les seuils PNI systolique bas/haut, diastolique bas/haut, et MAP bas/haut. Sélectionner également l'intervalle de mesure automatique PNI (ex. : toutes les 15 min en USIC, toutes les 30 min en chambre standard).

### Étape 5 — Configuration des seuils FR et Température

12. Sélectionner **[Fréquence respiratoire]** : régler seuil bas, seuil haut, et durée d'apnée déclenchant l'alarme.
13. Sélectionner **[Température]** : régler seuil bas et seuil haut selon la voie de mesure utilisée (rectale / axillaire / tympanique — compenser si nécessaire).

### Étape 6 — Réglage du volume et de la priorité sonore

14. Dans l'onglet **[Alarmes sonores]**, régler :
   - **Volume alarmes haute priorité** (rouge) : minimum niveau 4/6 recommandé.
   - **Volume alarmes moyenne priorité** (jaune) : niveau 3/6 recommandé.
   - **Volume alarmes basse priorité** (bleu) : niveau 2/6 recommandé.
15. Ne jamais régler le volume à 0, même temporairement, sans utiliser la fonction **[Silence temporaire]** (2 minutes maximum).

### Étape 7 — Activation du mode de gestion intelligente des alarmes (Smart Alarm)

16. Dans l'onglet **[Options avancées]**, activer l'option **[Smart Alarm Management]** si disponible (firmware ≥ V03.10) : cette fonction retarde de 15 secondes les alarmes de priorité intermédiaire en cas d'artefact de mouvement confirmé, réduisant les fausses alarmes de ~40%.
17. Activer l'option **[Alarme de rappel]** : le moniteur émet une alarme de rappel sonore toutes les 2 minutes si une alarme active n'a pas été acquittée.

### Étape 8 — Sauvegarde et validation

18. Appuyer sur **[Enregistrer]** pour sauvegarder la configuration.
19. Sélectionner si la configuration est :
    - **Spécifique au patient actuel** (sera perdue à la décharge du patient).
    - **Comme nouveau profil par défaut du service** (écriture protégée — nécessite code superviseur).
20. Effectuer un **test de validation** : simuler manuellement une valeur hors seuil (par ex., SpO2 affichée en dessous du seuil bas en déconnectant le capteur) et vérifier le déclenchement de l'alarme.
21. Documenter la configuration dans la **fiche de configuration alarmes patient** (disponible dans le dossier patient informatisé).

---

## 5. Sauvegarde et Chargement de Profils

### 5.1 Sauvegarder un profil de configuration

Le BeneVision N17/N22 permet de sauvegarder des profils de configuration nommés (ex. « USIC adulte standard », « Réa néonatale », « Post-op chirurgie cardiaque ») :

1. Accéder à `Menu > Configuration > Profils d'alarme > Sauvegarder profil`.
2. Nommer le profil (20 caractères maximum).
3. Sélectionner si le profil est sauvegardé en mémoire interne (jusqu'à 10 profils) ou exporté sur clé USB (format .BVP).
4. Confirmer la sauvegarde.

### 5.2 Charger un profil de configuration existant

1. Accéder à `Menu > Configuration > Profils d'alarme > Charger profil`.
2. Sélectionner le profil dans la liste ou depuis la clé USB.
3. Confirmer le chargement : **attention**, le chargement écrase immédiatement la configuration en cours.
4. Vérifier les seuils chargés avant application clinique.

> **Recommandation :** Maintenir une copie USB des profils de configuration dans le local biomédical et sur le serveur de sauvegarde de la DSI, avec datation et versioning.

---

## 6. Erreurs Courantes et Points de Vigilance

| Erreur courante                                       | Risque clinique                     | Solution                                              |
|-------------------------------------------------------|-------------------------------------|-------------------------------------------------------|
| Volume sonore alarme = 0 (mute permanent)             | Alarme silencieuse non perçue       | Toujours utiliser la fonction Silence temporaire (2 min max) |
| Seuil SpO2 bas trop bas (ex. 75% au lieu de 92%)     | Non-détection désaturation précoce  | Vérifier le seuil à chaque changement de patient      |
| Seuil FC haut trop élevé (ex. 200 bpm en adulte)     | Tachycardie non signalée            | Adapter le seuil au contexte clinique                 |
| Profil patient inadapté (ex. profil adulte sur néonatal) | Seuils complètement inadaptés    | Vérifier et sélectionner le profil approprié          |
| Délai d'alarme FR apnée > 30s                        | Détection tardive d'apnée           | Ne pas dépasser 20s pour les patients à risque        |
| Non-réactivation des alarmes après silence           | Alarme restée muette                | Vérifier systématiquement l'état du système d'alarme après fin de silence |
| Modification des seuils par du personnel non habilité | Configuration incorrecte non tracée | Protéger le menu de configuration par mot de passe superviseur |

---

*Document établi par Sophie Vigneron — Ingénieure biomédicale Clinique Saint-Louis*
*Références : Mindray BeneVision N-Series Operator's Manual PN 046-011178-00 Rev 2.0 ; HAS Guide « Prévention de la fatigue aux alarmes » 2022 ; SFAR Recommandations monitorage continu 2023*
*Validé par Dr. Mathieu Lemaire (Chef service réanimation) et M. Patrick Arnaud (DT)*
*Date de validation : 10/01/2025 — Révision : 10/01/2026*
