---
id: MON-MAN-002
titre: "Guide de référence rapide — BeneVision N22/N19/N17/N15/N12"
reference: "H-046-011260-FR-SYN-2.0"
famille: moniteur_multiparametrique
modele: Mindray BeneVision N-Series
fabricant: Mindray
type: guide_reference_rapide
langue: fr
statut: synthetique
date_creation: 2025-02-01
verifie: false
pages_estimees: 6
inspire_de: "H-046-011260-00-N-Series-Quick-Guide-FDA-2.0.pdf"
---

<!-- Quick Reference Guide | Mindray BeneVision N-Series Moniteur Patient -->

# Guide de référence rapide : BeneVision N-Series

Ce guide synthétique regroupe les actions immédiates et raccourcis essentiels pour configurer et exploiter un moniteur BeneVision N-Series au chevet du patient.

---

### 1. Touches de raccourci (Quick Keys) de la barre inférieure

| Raccourci | Symbole / Icône | Description fonctionnelle |
| :--- | :---: | :--- |
| **Alarm Setup** | 🔔 | Ouvre la fenêtre de réglage global des seuils et volumes d'alarmes. |
| **Alarm Reset** | 🔕✓ | Acquitte les alarmes en cours et réarme le système d'alarme. |
| **Audio Pause** | 🔇 | Coupe la tonalité des alarmes pendant une durée temporisée (120 s par défaut). |
| **NIBP Start/Stop**| 🩺 | Lance ou interrompt immédiatement une mesure de pression non invasive. |
| **NIBP Interv.** | ⏱️ | Sélectionne la fréquence de mesure cyclique PNI (Off, 5 min, 15 min, 30 min...). |
| **Zero IBP** | ⇥0⇤ | Lance la mise à zéro des transducteurs de pression invasive raccordés. |
| **Standby** | 🛌 | Place le moniteur en mode veille clinique (patient en examen ou transport). |
| **Freeze** | ❄️ | Gèle instantanément les tracés à l'écran pour examen rétrospectif. |
| **Main Menu** | ☰ | Accède à la configuration générale de l'appareil et aux outils de service. |

---

### 2. Gestes tactiles sur écran capacitif
- **Toucher (Tap) :** Sélectionne un pavé de paramètre ou valide un menu contextuel.
- **Glisser horizontal (Swipe) :** Fait défiler les pages d'écrans configurées ou l'historique des tendances.
- **Pincer / Écarter (Pinch to zoom) :** Ajuste l'échelle d'amplitude des tracés ECG ou EEG.
- **Appui long :** Ouvre directement le menu de configuration avancée du paramètre visé.

---

### 3. Gestion du patient : Admission et Décharge

#### Admission d'un nouveau patient :
1. Touchez le bandeau supérieur d'information patient.
2. Appuyez sur **Admettre patient**.
3. Choisissez la catégorie patient impérative : **Adulte**, **Pédiatrique** ou **Néonatal** *(cette sélection définit les seuils d'alarmes usine et la limitation de pression du brassard PNI)*.
4. Saisissez l'IPP / Nom / Sexe ou interrogez le serveur d'admission ADT via la passerelle eGateway.

#### Décharge du patient :
1. Touchez **Décharger patient** dans le menu patient.
2. Confirmez : la mémoire tampon des tendances et tracés précédents est effacée, et les seuils d'alarme standard du service sont réappliqués.

---

### 4. Procédure rapide de zéro de pression invasive (IBP)

1. Connectez le câble d'interface au module IBP et raccordez la tête de transducteur.
2. Ouvrez le robinet trois voies du transducteur à l'air libre (niveau de la ligne phlébostatique).
3. Appuyez sur la touche physique **Zéro** du module ou touchez le raccourci **Zéro IBP** sur l'écran.
4. Le message *"Mise à zéro en cours"* s'affiche, suivi de *"Zéro IBP OK"* sous 3 secondes.
5. Refermez le robinet vers le patient pour débuter la mesure continue de pression artérielle.

---

### 5. Seuils d'alarme par défaut (Profil Adulte standard)

| Paramètre | Seuil Bas | Seuil Haut | Priorité par défaut |
| :--- | :--- | :--- | :--- |
| **Fréquence cardiaque (FC)** | 50 bpm | 120 bpm | HAUTE |
| **SpO2** | 90% | 100% | HAUTE |
| **Désaturation (DeSat)** | 85% | — | HAUTE (verrouillée) |
| **PNI Systolique (SYS)** | 90 mmHg | 160 mmHg | MOYENNE |
| **PNI Diastolique (DIA)** | 50 mmHg | 95 mmHg | MOYENNE |
| **Fréquence respiratoire (FR)**| 8 rpm | 30 rpm | MOYENNE |
| **Apnée** | 20 secondes | — | HAUTE |

---
*Fiche réflexe de poche pour personnel biomédical et clinique — Projet MaintiDoc 2025.*
