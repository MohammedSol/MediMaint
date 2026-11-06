---
id: MON-SYN-001
titre: Rapport d'intervention – Dysfonctionnement alarmes SpO2 sur Mindray BeneVision N17
famille: moniteur_multiparametrique
modele: Mindray BeneVision N-Series
fabricant: Mindray
type: rapport_intervention
langue: fr
statut: synthetique
date_creation: 2025-01-15
verifie: false
pages_estimees: 3
---

# Rapport d'Intervention Technique
## Dysfonctionnement des Alarmes SpO2 — Mindray BeneVision N17

---

| Champ               | Valeur                                            |
|---------------------|---------------------------------------------------|
| **N° Rapport**      | RAP-2025-0208-001                                 |
| **Date**            | 08/02/2025                                        |
| **Heure début**     | 10h00                                             |
| **Heure fin**       | 14h15                                             |
| **Durée totale**    | 4h15                                              |
| **Technicien**      | Sophie Vigneron                                   |
| **N° Habilitation** | BMET-IDF-2020-0112                                |
| **Établissement**   | Clinique Saint-Louis — Lyon 3ème                  |
| **Service**         | Soins Intensifs de Cardiologie (USIC)             |
| **Contact site**    | M. Fabrice Dupont, Cadre infirmier USIC           |
| **Équipement**      | Mindray BeneVision N17                            |
| **Numéro de série** | ML-N17-20230042                                   |
| **N° Inventaire**   | SL-LY-MON-0089                                    |
| **Version firmware**| BeneVision N17 — Software V03.10.021007           |
| **Module SpO2**     | Masimo SET® — SN intégré : MSM-N17-0042           |

---

## 1. Motif de l'Intervention

Le service des soins intensifs de cardiologie a signalé une **défaillance critique du système d'alarme SpO2** sur le moniteur multiparamétrique Mindray BeneVision N17 (SN : ML-N17-20230042). La défaillance a été constatée le 06/02/2025 lors d'une garde de nuit : une infirmière a noté que l'alarme sonore et visuelle liée à la saturation en oxygène ne se déclenchait **pas** lorsque la SpO2 du patient descendait en dessous de 90%, seuil cliniquement critique.

La fiche de signalement qualité NC-MON-2025-0023 a été ouverte immédiatement par la direction des soins, avec priorisation **URGENTE** compte tenu du risque direct pour la sécurité des patients en USIC. L'équipement a été temporairement mis hors service clinique et remplacé par un moniteur de réserve jusqu'à résolution du problème.

---

## 2. Diagnostic

### 2.1 Vérification préliminaire sur site (10h00 – 10h45)

À l'arrivée sur site, recueil d'information auprès de l'infirmière cadre : le problème aurait débuté après une manipulation du menu de configuration par un interne en médecine lors d'une formation au moniteur. Vérification de l'état général du moniteur : aucun dommage physique apparent ; firmware à jour (version V03.10.021007).

Connexion du simulateur patient Fluke ProSim 8 (SN : PSM8-2024-FR-0021) :
- Simulation SpO2 = **98%** : affichage correct → alarme muette (attendu) ✓
- Simulation SpO2 = **88%** (< seuil critique 90%) : **aucune alarme déclenchée** ✗
- Simulation SpO2 = **75%** : affichage de la valeur 75%, voyant rouge actif, mais **aucun signal sonore** ✗

Accès au menu de configuration alarmes (`Menu > Paramètre > SpO2 > Réglages alarmes`) :

**Anomalie 1 identifiée** : Le seuil bas d'alarme SpO2 était configuré à **75%** au lieu des **92%** (valeur standard USIC adulte). La valeur avait été modifiée manuellement, vraisemblablement par erreur lors de la session de formation.

**Anomalie 2 identifiée** : La sortie sonore des alarmes SpO2 était configurée en **volume = 0** (alarme muette), suite à une manipulation du volume général des alarmes. Le voyant visuel fonctionnait, mais sans alarme sonore, l'alerte était cliniquement insuffisante.

### 2.2 Inspection du câble et capteur SpO2 Nellcor (10h45 – 11h30)

Lors du test avec le simulateur, des **interruptions intermittentes** du signal SpO2 ont été détectées (affichage « — » pendant 3 à 8 secondes toutes les 1 à 2 minutes). Ces interruptions ne semblaient pas liées aux réglages d'alarme, mais à un problème matériel.

Inspection physique du câble d'extension SpO2 Nellcor OxiMax (réf. ML-SpO2-EXT-NL-003, longueur 3 m) :
- Traces d'usure importante au niveau du connecteur proximal (côté moniteur) : **gaine extérieure fissurée** sur 4 cm, avec câbles internes apparents.
- Test de continuité avec multimètre : **rupture intermittente du fil de signal** (piste 3 — signal PPG) confirmée.
- Conclusion : **câble Nellcor défaillant** à remplacer.

---

## 3. Actions Correctives

### Étape 1 — Reconfiguration du seuil d'alarme SpO2 (11h30 – 11h50)

Accès au menu protégé de configuration (`Menu > Maintenance > Réglages par défaut — code technicien : XXXX`) :
- Seuil alarme SpO2 bas : réglé à **92%** (valeur standard USIC adulte conformément aux recommandations cliniques de la Clinique Saint-Louis).
- Seuil alarme SpO2 très bas : réglé à **85%** (alarme de niveau critique).
- Seuil alarme SpO2 haut : réglé à **100%** (désactivé — pas d'alarme haute cliniquement pertinente en USIC adulte).
- Délai de déclenchement alarme : **10 secondes** (évite les fausses alarmes sur artefacts de mouvement).

### Étape 2 — Reconfiguration du volume sonore des alarmes (11h50 – 12h00)

- Volume alarme SpO2 rétabli à **niveau 4/6** (niveau standard défini dans la politique d'alarme de la clinique).
- Test de déclenchement sonore immédiat après modification : alarme audible à 3 mètres ✓.
- Protection du menu de configuration par mot de passe infirmier renforcé (procédure de réinitialisation code : voir SOP-MON-CONFIG-001).

### Étape 3 — Remplacement du câble SpO2 Nellcor défaillant (12h00 – 12h30)

- Remplacement du câble d'extension SpO2 Nellcor OxiMax par un câble neuf (réf. ML-SpO2-EXT-NL-003, lot : LT-2025-02-0847, stérilisation : NA — dispositif non stérile).
- Test de continuité du nouveau câble : conforme (toutes pistes < 0,5 Ω).
- Connexion au simulateur patient : signal SpO2 stable sur 15 minutes consécutives, aucune interruption.

### Étape 4 — Test complet du système d'alarmes avec simulateur patient (12h30 – 13h30)

Protocole de test exhaustif avec Fluke ProSim 8 :

| Test                              | Valeur simulée | Résultat attendu             | Résultat obtenu | Conforme |
|-----------------------------------|----------------|------------------------------|-----------------|----------|
| SpO2 au-dessus du seuil           | 96%            | Pas d'alarme                 | Pas d'alarme    | ✓        |
| SpO2 proche du seuil bas          | 93%            | Pas d'alarme                 | Pas d'alarme    | ✓        |
| SpO2 en dessous du seuil bas      | 90%            | Alarme niveau 2 (jaune)      | Alarme déclenchée en 11s | ✓   |
| SpO2 en dessous du seuil critique | 83%            | Alarme niveau 3 (rouge+son)  | Alarme déclenchée en 10s | ✓   |
| SpO2 = 0 (perte signal)           | Déconnexion    | Alarme "Capteur déconnecté"  | Alarme déclenchée | ✓     |
| Test pause alarme (2 min)         | —              | Reprise automatique après 2' | Reprise en 2'   | ✓        |
| Alarme FC < 40 bpm simultanée     | FC=35 bpm      | Priorisation alarme FC       | Alarme FC prioritaire | ✓   |

### Étape 5 — Vérification AAMI/IEC 60601-1-8 et remise en service (13h30 – 14h15)

Vérification de la conformité du paramétrage final aux exigences de la norme IEC 60601-1-8 (gestion des alarmes en équipements médicaux) et à la politique d'alarme interne de la Clinique Saint-Louis (réf. POL-CLIN-SL-ALARM-V3-2024).

Formation rapide (20 min) réalisée auprès du cadre infirmier Fabrice Dupont sur les points suivants :
- Rappel de la politique d'interdiction de modification des paramètres d'alarme sans validation biomédicale.
- Procédure de signalement en cas d'anomalie d'alarme.
- Identification des indicateurs visuels et sonores du moniteur.

Remise en service clinique à **14h15 le 08/02/2025**.

---

## 4. Pièces Utilisées

| Référence              | Désignation                                   | Quantité | N° de lot        | Coût |
|------------------------|-----------------------------------------------|----------|------------------|------|
| ML-SpO2-EXT-NL-003     | Câble extension SpO2 Nellcor OxiMax 3m        | 1        | LT-2025-02-0847  | 42 € HT |

---

## 5. Résultat et Conclusion

Les deux anomalies identifiées (seuil d'alarme SpO2 incorrectement configuré à 75% + volume sonore à 0) résultaient d'une manipulation non maîtrisée du menu de configuration lors d'une session de formation. La défaillance du câble Nellcor était un problème indépendant lié à l'usure normale du consommable.

**Après intervention, l'ensemble du système d'alarmes SpO2 est conforme aux exigences cliniques et réglementaires. L'équipement est remis en service clinique.**

**Recommandation forte :** Mettre en place un verrouillage par mot de passe du menu de configuration des alarmes accessible en mode utilisateur normal, afin d'éviter toute modification non autorisée. Cette mesure est à déployer sur l'ensemble des BeneVision N17/N22 de la clinique.

---

## Signature

| Technicienne intervenante | Cadre infirmier validant |
|---------------------------|--------------------------|
| Sophie Vigneron           | Fabrice Dupont           |
| BMET-IDF-2020-0112        | USIC — Clinique Saint-Louis |
| _Signé électroniquement_  | _Signé électroniquement_  |
| 08/02/2025 — 14h15        | 08/02/2025 — 14h20       |

---
*Archivé dans GMAO Clinique Saint-Louis — Réf. : GMAO-SL-2025-RAP-0208-001*
