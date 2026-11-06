---
id: RAD-MAN-002
titre: "Guide de démarrage rapide — DR 100e + Détecteur DR 14s"
reference: "QSG-DR100e-FR-2025"
famille: radiographie_numerique
modele: AGFA DR 100e
fabricant: Agfa Radiology Solutions
type: guide_demarrage
langue: fr
statut: synthetique
date_creation: 2025-01-20
verifie: false
pages_estimees: 4
inspire_de: "DR 100e Quick Reference & Operating Guide"
---

<!-- Quick Reference Guide | AGFA DR 100e Mobile Digital System -->

# Guide de démarrage rapide : AGFA DR 100e & DR 14s

Ce guide synthétique récapitule les étapes essentielles pour mettre en œuvre rapidement l'unité mobile de radiographie AGFA DR 100e lors d'une intervention au lit du patient.

---

### Checklist de mise en service immédiate (10 points de contrôle)
- [ ] Câble d'alimentation secteur 230 V branché ou chariot sous réserve batterie.
- [ ] Disjoncteur général sur position **I (ON)**.
- [ ] Écran tactile NX allumé et session technicien ouverte.
- [ ] Détecteur DR 14s extrait de son dock de charge, batterie > 80% (3 barres vertes).
- [ ] Liaison sans fil WiFi détecteur/poste NX confirmée (icône antenne active).
- [ ] Colonne télescopique déverrouillée et rotation libre sans contrainte.
- [ ] Voyant collimateur fonctionnel (minuterie 30 s vérifiée).
- [ ] Déclencheur à main à double course opérationnel.
- [ ] Housse de protection hygiénique neuve appliquée sur le panneau DR 14s.
- [ ] Équipements de radioprotection disponibles (tablier plombé 0,5 mm Pb pour le manipulateur).

---

### Procédure opérationnelle en 5 étapes clés

```
[1. MISE SOUS TENSION] ──> [2. SÉLECTION EXAMEN] ──> [3. POSITIONNEMENT] ──> [4. EXPOSITION] ──> [5. TRANSMISSION]
   Disjoncteur ON             Worklist SIR / Urgence     Centrage collimateur       Double course       MUSICA & PACS
```

#### Étape 1 : Mise sous tension et initialisation
1. Enclenchez le disjoncteur général situé en bas à droite du châssis.
2. Allumez la station NX. Le système réalise un auto-test matériel (POST) en 45 secondes.
3. Le détecteur DR 14s se synchronise automatiquement par liaison radiofréquence 5 GHz.

#### Étape 2 : Sélection du patient et de la procédure
1. Sur l'interface NX, appuyez sur **Worklist** pour afficher les demandes du SIR.
2. Touchez le nom du patient puis sélectionnez le programme anatomique (ex: *Thorax AP*).
3. En cas d'urgence vitale sans identification préalable, appuyez sur **Examen d'urgence** ; les paramètres standards par défaut (80 kV, 2.5 mAs) sont immédiatement appliqués.

#### Étape 3 : Positionnement du chariot et du tube
1. Déverrouillez la pédale de frein, poussez l'unité au chevet du patient.
2. Alignez le tube à rayons X avec la région à radiographier. Ajustez la hauteur à l'aide de la poignée de commande du bras.
3. Allumez la lumière du collimateur via la touche latérale et ajustez les volets. Contrôlez la distance foyer-détecteur (SID) avec le ruban métrique (distance nominale : 100 cm).

#### Étape 4 : Déclenchement de l'exposition
1. Reculez d'au moins 2 mètres de la source de rayonnement.
2. Pressez le bouton du câble d'exposition au 1er cran (préparation anode) : attendez l'allumage du voyant vert "PRÊT".
3. Pressez à fond au 2e cran : le voyant orange s'allume avec émission d'un bip sonore continu. Maintenez enfoncé jusqu'à la fin de la tonalité.

#### Étape 5 : Revue de l'image et archivage
1. L'image radiologique apparaît sous 3 secondes sur l'écran tactile NX.
2. Vérifiez la qualité diagnostique et l'absence d'artéfacts de mouvement.
3. Touchez **Envoyer vers PACS** pour archiver l'examen au format DICOM 3.0.

---

### Résolution rapide des incidents d'exploitation

| Code / Symptôme | Cause probable | Action immédiate |
| :--- | :--- | :--- |
| **Icône WiFi clignotante rouge** | Perte de liaison détecteur DR 14s | Rapprocher le détecteur du chariot ou le replacer 10 s dans son docking. |
| **Voyant PRÊT éteint au 1er cran** | Température tube trop haute ou mauvais contact | Vérifier si alarme surchauffe active. Relâcher et réappuyer franchement. |
| **Touche collimateur sans effet** | Minuterie 30 s expirée ou connecteur débranché | Réappuyer une seconde fois sur la touche d'allumage collimateur. |
| **Code erreur E-001** | Tension d'alimentation secteur basse (< 207 V) | Changer de prise murale 16A ; vérifier le raccordement du câble de 8 m. |
| **Code erreur E-011** | Déconnexion communication interne NX-Générateur | Redémarrer le poste NX en coupant le disjoncteur général pendant 30 s. |

---
*Support de formation interne MaintiDoc 2025. Référence produit AGFA DR 100e.*
