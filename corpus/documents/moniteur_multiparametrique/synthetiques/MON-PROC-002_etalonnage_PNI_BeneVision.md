---
id: MON-PROC-002
titre: "Procédure d'étalonnage de la pression non-invasive (PNI) — BeneVision N-Series"
reference: "PROC-BeneVision-PNI-ETALON-2025"
famille: moniteur_multiparametrique
modele: Mindray BeneVision N-Series
type: procedure_etalonnage
periodicite: annuelle
duree_estimee: "1h00"
qualification_requise: "Technicien biomédical (accréditation COFRAC recommandée)"
langue: fr
statut: synthetique
date_creation: 2025-01-15
verifie: false
pages_estimees: 4
---

<!-- Technical Calibration Protocol | Mindray BeneVision NIBP Subsystem -->

# Procédure d'étalonnage et vérification métrologique PNI : BeneVision N-Series

### 1. Objet et conformité normative
Vérifier et ajuster l'étalonnage des transducteurs de pression piézorésistifs du circuit pneumatique de pression artérielle non invasive (PNI) des moniteurs Mindray BeneVision, conformément aux exigences de la norme internationale **CEI 80601-2-30** relative à la sécurité et aux performances essentielles des sphygmomanomètres automatisés.

---

### 2. Dispositif de banc d'essai
- Chambre rigide d'expansion volumique métallique (volume étalon : 500 mL ± 25 mL).
- Pompe à main pneumatique de génération de pression avec vernier de réglage fin.
- Manomètre numérique de référence de haute précision (incertitude de mesure maximale tolérée : ± 0,2 mmHg).
- Raccord en T à tubulures semi-rigides et connecteurs rapides métalliques Mindray.

```
┌──────────────────┐         ┌─────────────────────┐
│  Moniteur N-Series│         │   Chambre 500 mL    │
│    (Port PNI)    ├────┐    ┌┤    (Rigide)         │
└──────────────────┘    │    │└─────────────────────┘
                        ├──T─┤
┌──────────────────┐    │    │┌─────────────────────┐
│ Manomètre Étalon ├────┘    └┤   Poire / Pompe     │
│  (± 0.2 mmHg)    │          │  de mise en pression│
└──────────────────┘          └─────────────────────┘
```

---

### 3. Protocole opératoire détaillé

#### Étape 1 : Accès au mode Service Technique
1. Allumez le moniteur BeneVision.
2. Touchez `Menu Principal -> Maintenance -> Maintenance Usine/Service`.
3. Saisissez le code d'accès technicien biomédical habilité (`MindrayPass`).
4. Sélectionnez le module `PNI (NIBP) -> Test de Pression Statique / Étalonnage`.

#### Étape 2 : Test d'étanchéité pneumatique préliminaire (Leak Test)
1. Montez la pression à **250 mmHg** à l'aide de la pompe pneumatique.
2. Patientez 20 secondes pour la stabilisation thermique du volume d'air comprimé.
3. Déclenchez le chronomètre de test de fuite automatique de 60 secondes.
4. **Critère de conformité :** La chute de pression mesurée sur 60 secondes doit être strictement inférieure à **6 mmHg**. Si la fuite est supérieure, vérifier les joints toriques du connecteur rapide et le clapet anti-retour de l'électrovanne avant de poursuivre.

#### Étape 3 : Contrôle de linéarité sur 5 points de mesure

| Palier de consigne étalon | Pression étalon mesurée | Pression affichée sur écran moniteur | Écart constaté (Δ) | Tolérance limite admissible |
| :---: | :---: | :---: | :---: | :---: |
| **Palier 1 : 50 mmHg** | 50.0 mmHg | _____ mmHg | _____ mmHg | ± 3.0 mmHg |
| **Palier 2 : 100 mmHg** | 100.0 mmHg | _____ mmHg | _____ mmHg | ± 3.0 mmHg |
| **Palier 3 : 150 mmHg** | 150.0 mmHg | _____ mmHg | _____ mmHg | ± 3.0 mmHg |
| **Palier 4 : 200 mmHg** | 200.0 mmHg | _____ mmHg | _____ mmHg | ± 3.0 mmHg |
| **Palier 5 : 250 mmHg** | 250.0 mmHg | _____ mmHg | _____ mmHg | ± 3.0 mmHg |

#### Étape 4 : Procédure de recalibration en cas d'écart > 3 mmHg
Si un écart supérieur à ±3 mmHg est relevé :
1. Sélectionnez la fonction **Ajuster calibration PNI**.
2. Appliquez une pression stabilisée exactement égale à **200.0 mmHg** lue sur le manomètre étalon certifié.
3. Appuyez sur la touche logicielle **Valider le point 200 mmHg**.
4. Le microcontrôleur recalcule automatiquement la pente de conversion analogique/numérique et l'enregistre en mémoire non volatile EEPROM.
5. Répétez le cycle complet des 5 paliers pour valider formellement la linéarité post-ajustement.

---
*Fiche métrologique d'étalonnage PNI — Projet MaintiDoc 2025.*
