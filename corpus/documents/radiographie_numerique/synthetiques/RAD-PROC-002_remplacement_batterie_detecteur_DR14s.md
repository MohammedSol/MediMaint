---
id: RAD-PROC-002
titre: "Procédure de remplacement de la batterie — Détecteur AGFA DR 14s"
reference: "PROC-DR14s-BAT-2025"
famille: radiographie_numerique
modele: AGFA DR 100e
composant: "Détecteur AGFA DR 14s"
fabricant: Agfa Radiology Solutions
type: procedure_remplacement
duree_estimee: "30 min"
qualification_requise: "Technicien biomédical"
langue: fr
statut: synthetique
date_creation: 2025-02-01
verifie: false
pages_estimees: 3
---

<!-- Technical Service Procedure | AGFA DR 14s Detector Battery Replacement -->

# Procédure de remplacement de la batterie : Détecteur AGFA DR 14s

### 1. Critères de remplacement
Le pack batterie Lithium-ion du capteur plan DR 14s doit être remplacé dès lors que l'une des conditions suivantes est observée :
- Autonomie en service inférieure à 120 minutes (ou moins de 50 clichés consécutifs).
- Nombre de cycles de décharge complète supérieur à 500 cycles (historique consultable via l'outil de diagnostic NX).
- Message d'alerte permanent *« Batterie détecteur dégradée - Remplacement requis »*.
- Gonflement physique visible de l'enveloppe de la cellule de batterie.

---

### 2. Référence de pièce d'origine
- **Désignation :** Pack batterie rechargeable Li-ion pour détecteur Agfa Dura-line DR 14s/17s.
- **Référence constructeur :** AGF-DR14S-BAT-LI42 (Tension nominale : 11,1 V DC ; Capacité : 4 200 mAh / 46,6 Wh).

---

### 3. Matériel requis et précautions ESD
- Tournevis Torx de précision T8.
- Bracelet antistatique relié à la terre pour éviter toute décharge électrostatique sur les cartes TFT.
- Lingette imbibée d'alcool isopropylique à 70%.

---

### 4. Procédure étape par étape

```
[1. ÉTEINDRE DÉTECTEUR] ──> [2. OUVRIR TRAPPE] ──> [3. EXTRAIRE BATTERIE] ──> [4. INSÉRER NEUVE] ──> [5. TEST CHARGE]
```

1. **Mise hors tension :** Pressez la touche d'alimentation du détecteur pendant 4 secondes jusqu'à extinction totale de la LED d'état bleue/verte.
2. **Déverrouillage :** Retournez le panneau sur une surface capitonnée douce. Repérez le verrou mécanique de la trappe batterie au dos du boîtier en magnésium.
3. **Extraction :** Faites glisser le loquet de sécurité en position déverrouillée et retirez le couvercle étanche (vérifiez l'état du joint torique périphérique noir).
4. **Retrait du pack usagé :** Tirez délicatement sur la languette textile d'extraction pour dégager le connecteur multibroches.
5. **Nettoyage préventif :** Nettoyez les broches du connecteur interne à l'aide d'un coton-tige imbibé d'alcool isopropylique. Laissez sécher 60 secondes.
6. **Insertion du pack neuf :** Insérez la batterie neuve AGF-DR14S-BAT-LI42 en alignant les détrompeurs mécaniques. Appuyez fermement jusqu'à entendre le clic franc d'encliquetage.
7. **Fermeture de la trappe :** Repositionnez le couvercle de la trappe et verrouillez le loquet. Assurez-vous de la continuité de l'étanchéité IP54.
8. **Initialisation et charge complète :** Insérez le détecteur dans la baie de recharge (dock) de l'unité mobile DR 100e. Laissez charger jusqu'à allumage de la LED verte fixe (environ 3 heures).
9. **Mise à jour compteur :** Sur la console NX, connectez-vous avec le profil Administrateur Biomédical, ouvrez `Outils -> Maintenance Détecteur -> Réinitialiser cycle batterie`.

---
*Procédure de service technique MaintiDoc 2025.*
