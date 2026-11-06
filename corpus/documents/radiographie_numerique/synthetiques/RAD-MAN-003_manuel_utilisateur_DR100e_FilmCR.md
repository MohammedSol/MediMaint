---
id: RAD-MAN-003
titre: "Manuel de l'utilisateur — DR 100e (Film/CR)"
reference: "0360B-FR-SYN-2025"
famille: radiographie_numerique
modele: AGFA DR 100e
fabricant: Agfa Radiology Solutions
references_produit: ["6012/001", "6012/002"]
type: manuel_utilisateur
langue: fr
statut: synthetique
date_creation: 2025-01-15
verifie: false
pages_estimees: 10
revision: B
inspire_de: "DR_100e_(Film_CR)_User_Manual_0360_B_(French).pdf"
---

<!-- Page 1 | DR 100e (Film/CR) | Manuel de l'utilisateur | 0360B FR 20181015 0853 -->

# DR 100e (Film/CR)
## Manuel de l'utilisateur — Révision B
**Références produit : 6012/001, 6012/002**

---

### 1. Présentation du système DR 100e en version Film/CR

La version Film/CR de l'Agfa DR 100e est une configuration autonome de radiographie mobile conçue pour fonctionner avec des cassettes radiologiques traditionnelles à films argentiques ou des cassettes à plaques photostimulables (écrans ERLM / CR). Contrairement à la version numérique directe (digital), cette déclinaison ne comporte pas de poste NX tout-en-un ni de détecteur DR sans fil intégré, mais offre un générateur haute puissance piloté par une console intégrée dédiée.

#### Spécifications fondamentales du générateur :
- Puissance maximale : 32 kW à 100 kV.
- Tension de tube réglable : 40 à 125 kV par pas de 1 kV.
- Plage de mAs : 0.1 à 110 mAs (extensible à 220 mAs en option).
- Courant de tube maximal : 400 mA.

---

### 2. Commandes de fonctionnement et console du générateur

Le panneau frontal du générateur intègre les commandes suivantes :
1. **Interrupteur général à clé / disjoncteur :** Contrôle l'arrivée secteur 230 V.
2. **Afficheurs digitaux à LED rouges à haute visibilité :**
   - Afficheur 3 chiffres pour les kilovolts (kV).
   - Afficheur 4 chiffres pour les milliampères-secondes (mAs).
   - Indicateur thermique d'échauffement du tube (% HU).
3. **Touches de réglage :**
   - Touches `[kV ▲]` et `[kV ▼]` pour modifier la tension de crête.
   - Touches `[mAs ▲]` et `[mAs ▼]` pour modifier la charge.
4. **Sélecteur de foyer :** Sélection petit foyer (pour haute résolution membres) ou grand foyer (pour examens thoraciques et abdominaux à forte charge).
5. **Indicateurs d'état lumineux et sonores :**

| Signal lumineux | Couleur | État du dispositif | Signification technique |
| :--- | :--- | :--- | :--- |
| **ALIMENTATION** | Vert | Fixe | Appareil sous tension, veille active. |
| **ATTENTE (STANDBY)** | Jaune | Fixe | Préchauffage du filament en cours. |
| **PRÊT (READY)** | Vert | Fixe | Vitesse d'anode atteinte (3 000 rpm), prêt au tir. |
| **RAYONS X (X-RAY)**| Jaune/Orange | Clignotant / Fixe | Tube en émission (présence haute tension). |
| **DEFAUT (ERROR)** | Rouge | Fixe / Clignotant | Blocage de sécurité activé (voir code affiché). |

#### Signaux sonores d'avertissement :
- **1 bip court (0,2 s) :** Prise en compte d'une touche sur le pupitre.
- **Tonalité continue (durant le tir) :** Émission de rayons X en cours.
- **2 bips successifs :** Fin normale de l'exposition.
- **3 bips intermittents rapides :** Refus d'exposition (anode non prête, surchauffe ou incident).

---

### 3. Procédure d'exposition sur cassette argentique ou CR

1. **Insertion de la cassette :** Positionnez la cassette 35x43 ou 24x30 sous le patient ou dans un porte-cassette mobile.
2. **Réglage géométrique :** Positionnez le monobloc radiogène à la distance focale requise (ex : 100 cm). Activez le réticule lumineux du collimateur pour aligner le centre de l'examen avec le centre de la cassette.
3. **Sélection des paramètres :**
   - Ajustez la valeur kV en fonction de la corpulence du patient et de la région anatomique.
   - Ajustez la valeur mAs conformément aux chartes d'exposition étalonnées pour la combinaison film-écran ou l'écran CR utilisé.
4. **Déclenchement :**
   - Enfoncez la poire d'exposition à mi-course. Attendez la fin de la phase de montée en vitesse de l'anode (environ 1.5 seconde) jusqu'à ce que le voyant vert "PRÊT" soit stable.
   - Enfoncez la poire à fond. Maintenez jusqu'à l'arrêt complet de la tonalité continue.
5. **Développement :** Transportez la cassette exposée vers la développeuse argentique ou le numériseur CR de service (ex: Agfa CR 30-X / CR 15-X).

---

### 4. Précautions et maintenance périodique

> **ATTENTION : Respect de la courbe de charge thermique du tube**  
> En mode argentique, le manipulateur doit surveiller l'indicateur d'accumulation thermique. Si l'affichage atteint 80% HU, marquez un temps d'arrêt de 10 à 15 minutes afin de préserver l'intégrité de l'anode tournante.

- **Vérification trimestrielle :** Répétabilité de dose, contrôle de l'alignement champ lumineux / champ de rayons X (tolérance < 1% de la distance foyer-détecteur).
- **Contrôle électrique annuel :** Mesure des courants de fuite à la terre conformément à la norme CEI 60601-1.

---
*Document de référence technique synthétique — Projet MaintiDoc 2025.*
