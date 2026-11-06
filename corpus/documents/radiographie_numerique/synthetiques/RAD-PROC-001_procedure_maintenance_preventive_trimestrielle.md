---
id: RAD-PROC-001
titre: "Procédure de maintenance préventive trimestrielle — AGFA DR 100e"
reference: "MP-DR100e-TRIM-2025"
famille: radiographie_numerique
modele: AGFA DR 100e
fabricant: Agfa Radiology Solutions
type: procedure_maintenance
periodicite: trimestrielle
duree_estimee: "3h00"
qualification_requise: "Technicien biomédical certifié Agfa"
langue: fr
statut: synthetique
date_creation: 2025-01-01
verifie: false
pages_estimees: 6
---

<!-- Maintenance Guide | AGFA DR 100e Mobile System | P/N MP-DR100e-TRIM-2025 -->

# Procédure de maintenance préventive trimestrielle : AGFA DR 100e

### 1. Objet et domaine d'application
La présente procédure a pour objet de définir les opérations d'inspection, de test électrique, d'étalonnage radiologique et de contrôle mécanique à exécuter tous les trois mois sur les unités de radiographie mobiles AGFA DR 100e (séries 6012/003 et 6012/004) équipées d'un détecteur plan sans fil DR 14s.

---

### 2. Outillage et instruments de mesure métrologiques requis

| Instrument / Équipement de test | Modèle recommandé | Exigence métrologique |
| :--- | :--- | :--- |
| **Multimètre numérique calibré** | Fluke 87V ou équivalent | Précision tension AC/DC < 0.1%, étalonnage valide COFRAC |
| **Testeur de sécurité électrique médical** | Fluke Biomedical ESA615 | Conforme CEI 62353 et CEI 60601-1 |
| **Chambre d'ionisation / Multimètre RX** | RaySafe X2 ou Unfors Xi | Précision dose/débit ±5%, kVp ±1.5% |
| **Fantôme de contrôle qualité d'image** | Fantôme DIN 6868-150 / CDRAD | Pour contrôle résolution spatiale et contraste |
| **Pesons dynamométriques** | Peson de traction 50 kg | Contrôle de force de déplacement de colonne |
| **Kit outillage mécanique** | Clés Torx T10-T30, dynamométrique | Couple de serrage vérifié |

---

### 3. Équipements de protection individuelle (EPI) obligatoires
- Tablier de radioprotection équivalent 0,5 mm Pb.
- Lunettes de protection plombées et protège-thyroïde.
- Dosimètre opérationnel personnel à lecture directe.
- Chaussures de sécurité avec embout renforcé.

---

### 4. Grille de contrôle et protocole de maintenance pas à pas

| N° | Opération de contrôle | Valeur de référence attendue | Constat / Mesure | Résultat |
| :---: | :--- | :--- | :--- | :---: |
| **01** | Inspection visuelle du châssis, roues et freins | Aucune fissure, bande de roulement intacte | Visuel OK | ☐ OK ☐ NOK |
| **02** | Test du système de freinage de parking | Blocage complet sur plan incliné à 5° | Maintien ferme | ☐ OK ☐ NOK |
| **03** | Articulation et équilibrage de la colonne | Force de manœuvre manuelle < 40 N | Effort fluide | ☐ OK ☐ NOK |
| **04** | Disjoncteur principal et arrêt d'urgence | Coupure immédiate de l'alimentation HT | Déclenchement net | ☐ OK ☐ NOK |
| **05** | Contrôle du câble secteur 230 V (8 m) | Gaine isolante sans entaille, terre continue | R_terre < 0.1 Ω | ☐ OK ☐ NOK |
| **06** | Courant de fuite à la terre (CEI 62353) | Limite : I_fuite < 500 µA (mode normal) | Mesuré : _____ µA | ☐ OK ☐ NOK |
| **07** | Minuterie de lampe du collimateur LED | Temporisation : 30 s ± 3 s | Chrono : _____ s | ☐ OK ☐ NOK |
| **08** | Concordance champ lumineux / champ RX | Écart bord à bord < 1% de la SID (10 mm à 1 m)| Mesuré : _____ mm | ☐ OK ☐ NOK |
| **09** | Exactitude de la tension crête (kVp) | Écart mesuré < ±3% à 70, 90 et 120 kV | ΔkVp = _____ % | ☐ OK ☐ NOK |
| **10** | Répétabilité du débit de dose (mGy/s) | Coefficient de variation (CV) < 0.05 sur 5 tirs | CV = _____ | ☐ OK ☐ NOK |
| **11** | Réseau WiFi détecteur DR 14s | Puissance signal RSSI > -65 dBm à 5 m | RSSI = _____ dBm | ☐ OK ☐ NOK |
| **12** | État batterie détecteur DR 14s | Capacité résiduelle > 80% (autonomie > 3h) | Cycles charge : ___ | ☐ OK ☐ NOK |
| **13** | Exécution calibration Non-Uniformité (NUC) | Écart-type flat field < 1.5%, aucun pixel mort | Rapport NUC OK | ☐ OK ☐ NOK |
| **14** | Sauvegarde des profils NX Workstation | Export configuration système sur clé USB | Backup terminé | ☐ OK ☐ NOK |
| **15** | Décontamination externe complète | Surfaces traitées avec lingettes certifiées | Nettoyage OK | ☐ OK ☐ NOK |

---

### 5. Actions correctives en cas de non-conformité
1. **Écart de tension kVp > 3% :** Procéder à l'ajustement du bus haute tension dans le menu d'étalonnage service de l'onduleur Agfa. Si le défaut persiste, contrôler la carte de régulation du générateur.
2. **Dérive de l'alignement du collimateur :** Desserrer les vis de calage des miroirs du collimateur et réaligner la diode LED d'éclairage selon la procédure constructeur.
3. **Résistance de terre > 0.2 Ω :** Démonter la cosse de mise à la terre principale du châssis, brosser les surfaces de contact, resserrer au couple de 4 Nm et renouveler la mesure.

---
*Fiche de maintenance préventive réglementaire — MaintiDoc 2025.*
