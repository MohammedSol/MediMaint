---
id: RAD-SYN-002
titre: Fiche d'incident – Artefacts horizontaux sur images radiographiques AGFA DR 100e
famille: radiographie_numerique
modele: AGFA DR 100e
fabricant: Agfa
type: fiche_incident
langue: fr
statut: synthetique
date_creation: 2025-01-15
verifie: false
pages_estimees: 2
---

# Fiche d'Incident Technique
## Artefacts Horizontaux sur Images Radiographiques — AGFA DR 100e

---

| Champ                  | Valeur                                        |
|------------------------|-----------------------------------------------|
| **ID Incident**        | INC-2025-0234                                 |
| **Date de déclaration**| 22/04/2025                                    |
| **Heure**              | 09h47                                         |
| **Priorité**           | **HAUTE**                                     |
| **Statut**             | **CLÔTURÉ**                                   |
| **Date de clôture**    | 22/04/2025 à 15h30                            |
| **Déclarant**          | Mme. Carole Marty, Manipulatrice radio        |
| **Équipement concerné**| AGFA DR 100e — SN : FR-2024-DR100-0847        |
| **Détecteur impliqué** | AGFA DR 14s — SN : DR14S-FR-20220389          |
| **Localisation**       | CHU Bordeaux — Salle de radio portable Urgences |
| **Technicien traitant**| Jean-Marc Lefèvre                             |

---

## 1. Description du Problème

À partir de 09h30 le 22/04/2025, le service des urgences a constaté l'apparition systématique d'**artefacts sous forme de lignes horizontales périodiques** sur l'ensemble des images radiographiques produites avec l'AGFA DR 100e et son détecteur sans fil DR 14s.

Les artefacts se présentaient comme des bandes horizontales claires (hypodenses) de **2 à 4 pixels de hauteur**, réparties de façon régulière sur toute la hauteur de l'image, avec un pas d'espacement d'environ **128 lignes**. Les artefacts étaient présents sur toutes les acquisitions, indépendamment du patient, du paramétrage d'exposition (kV, mAs) ou du positionnement anatomique. Le fond de l'image (hors artefact) semblait normal en termes de densité et de contraste.

Exemple d'images affectées : radiographies thoraciques de 3 patients (réf. : RAD-BX-20250422-001 à 003), toutes présentant le même motif d'artefact en bandes horizontales parallèles. Les images ont été **rejetées cliniquement** et les examens repassés avec l'équipement de secours (AGFA DR 100e fixe, salle 4), retardant la prise en charge de 45 minutes.

La fiche de non-conformité qualité NC-RAD-2025-0067 a été ouverte en parallèle par le responsable qualité du service d'imagerie.

---

## 2. Diagnostic

### 2.1 Hypothèses initiales écartées

Après analyse visuelle des images et interrogation du manipulateur radio :
- **Hypothèse 1 — Artefacts liés au tube radiogène** : écartée (remplacement du générateur portable par un autre tube → artefacts persistants avec le même détecteur DR 14s).
- **Hypothèse 2 — Problème logiciel MUSICA** : écartée (recalcul des images avec profil de traitement alternatif → artefacts toujours présents dans les données brutes).
- **Hypothèse 3 — Contamination physique du détecteur** : écartée (nettoyage de surface effectué → aucun changement).

### 2.2 Cause identifiée — Connexion détecteur défaillante

L'inspection physique du **connecteur de docking** du détecteur DR 14s a révélé :
- **Oxydation partielle** des contacts dorés du connecteur d'interface docking (réf. AGFA : AGF-DR14-CON-002), probablement due à une exposition à un produit désinfectant corrosif non homologué (traces de gel hydroalcoolique sur les contacts).
- **Intermittence de la liaison synchronisation** entre le détecteur et la station d'acquisition en mode WiFi-N (canal 5 GHz), provoquant des micro-coupures de transfert de données toutes les 128 lignes lors de la lecture du panneau plat — d'où le motif périodique caractéristique.

Le diagnostic a été confirmé par l'analyse du fichier de log système du détecteur (`detector_log_DR14S_20250422.txt`) : 23 erreurs de type `SYNC_TIMEOUT` enregistrées entre 09h30 et 09h45, chacune correspondant exactement à un artefact en bande sur une image.

---

## 3. Actions Correctives

1. **Nettoyage des contacts du connecteur docking** avec kit de nettoyage de contacts électroniques KONTAKT WL (spray isopropanol 99,9%, sans résidu) et coton-tige antistatique. Inspection visuelle sous loupe grossissante ×10.
2. **Test de continuité électrique** des 24 pistes du connecteur avec multimètre Fluke 87V : toutes les pistes mesurées conformes (résistance de contact < 0,1 Ω).
3. **Réinitialisation du module WiFi** du détecteur via le menu de diagnostic AGFA (`Settings > Network > Reset WiFi Module`). Reconnexion au réseau WiFi dédié imagerie (SSID : CHU-RAD-5G, canal 149, 802.11ac).
4. **Vérification de la liste des produits désinfectants** utilisés en salle urgences : identification du gel hydroalcoolique non référencé (marque non homologuée pour équipements électroniques médicaux). Signalement au service hygiène.
5. **Acquisition de 5 images test** sur fantôme PMMA après correction : **aucun artefact détecté**. Images conformes à la référence de calibration.

---

## 4. Résolution et Validation

Les 5 images de validation acquises après intervention sont exemptes de tout artefact. Le fichier de log post-intervention ne présente aucune erreur `SYNC_TIMEOUT`. L'équipement a été remis en service clinique à **15h30 le 22/04/2025** après validation par le manipulateur radio référent.

Un **affichage de rappel** sur les produits de nettoyage autorisés a été apposé sur l'équipement et en salle d'examen. La liste des produits homologués pour l'AGFA DR 100e et son détecteur a été transmise au service hygiène et aux équipes soignantes.

---

## 5. Mesures Préventives

- Ajout d'une inspection trimestrielle des contacts du connecteur docking dans le plan de maintenance préventive.
- Formation des équipes soignantes à la liste des produits désinfectants autorisés (session planifiée : 15/05/2025).
- Mise à jour de la fiche de nettoyage affichée sur l'équipement.

---

**Statut final : CLÔTURÉ — 22/04/2025 à 15h30**
*Validé par : Jean-Marc Lefèvre (technicien) et Dr. Isabelle Rondeau (responsable service)*
