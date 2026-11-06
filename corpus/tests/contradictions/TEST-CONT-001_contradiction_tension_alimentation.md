---
id: TEST-CONT-001
titre: Spécifications électriques – AGFA DR 100e (DOCUMENT DE TEST – CONTRADICTIONS VOLONTAIRES)
famille: radiographie_numerique
modele: AGFA DR 100e
fabricant: Agfa
type: test
langue: fr
statut: synthetique
date_creation: 2025-01-15
verifie: false
pages_estimees: 2
---

# Spécifications Électriques et Alimentation
## Système de Radiographie Mobile AGFA DR 100e

**Référence document :** AGF-SPEC-DR100E-ELEC-2024
**Version :** 3.4
**Date de révision :** 20 octobre 2024

---

## 1. Introduction

Le système de radiographie mobile **AGFA DR 100e** est un dispositif médical de classe IIb conçu pour fonctionner sur le réseau électrique hospitalier standard européen et international. Ce document précise les exigences d'alimentation électrique et les caractéristiques du bloc d'alimentation intégré, à destination des équipes biomédicales et techniques responsables de l'installation et de la maintenance de l'équipement.

La connaissance exacte des paramètres d'alimentation est essentielle pour :
- Vérifier la compatibilité avec l'installation électrique du service utilisateur.
- Dimensionner correctement les prises et les protections électriques dédiées.
- Prévenir les risques liés à une alimentation hors spécification (surtension, sous-tension, incompatibilité de fréquence).

---

## 2. Spécifications d'Alimentation — Section A (Fiche d'Installation)

La présente section est extraite de la **fiche d'installation rapide** fournie avec l'équipement (réf. AGF-DR100E-QIG-FR, Rev. 2, fournie dans le carton d'emballage).

### 2.1 Alimentation secteur

| Paramètre                     | Valeur                                           |
|-------------------------------|--------------------------------------------------|
| **Tension d'alimentation**    | **115 V / 230 V CA** — commutation automatique   |
| **Fréquence**                 | 50 Hz / 60 Hz                                    |
| **Puissance maximale absorbée**| 3 500 W (pendant l'exposition radiographique)   |
| **Puissance en veille**       | 85 W                                             |
| **Courant maximal absorbé**   | 15 A @ 230 V / 30 A @ 115 V                     |
| **Facteur de puissance**      | ≥ 0,95 (à pleine charge)                         |
| **Type de prise**             | CEE 7/4 (Schuko) — cordon fourni                 |
| **Protection différentielle** | 30 mA type A recommandée                         |

> **Note d'installation :** La prise de courant destinée au DR 100e doit être sur un circuit dédié ou semi-dédié, disjoncteur 16 A minimum (courbe C). Ne pas partager le circuit avec des équipements à fort démarrage (moteurs, compresseurs).

### 2.2 Batterie de secours interne

Le DR 100e est équipé d'une batterie interne Li-Ion permettant une autonomie de **fonctionnement réduit** (déplacements sans exposition) de 60 minutes après coupure secteur. Cette batterie n'est **pas** dimensionnée pour alimenter le générateur haute tension pendant les expositions radiographiques.

---

## 3. Spécifications d'Alimentation — Section B (Manuel Technique)

La présente section est extraite du **manuel technique complet** à destination des techniciens biomédicaux (réf. AGF-DR100E-TM-FR, Rev. 5, disponible sur demande auprès du SAV AGFA).

### 3.1 Paramètres électriques d'entrée

| Paramètre                     | Valeur                                            |
|-------------------------------|---------------------------------------------------|
| **Tension d'alimentation**    | **100 V / 240 V CA** — commutation automatique    |
| **Fréquence**                 | 50 Hz / 60 Hz                                     |
| **Puissance crête exposition**| 3 200 W (exposition standard 100 kV / 320 mA / 100 ms) |
| **Puissance nominale**        | 3 500 W (exposition maximale)                     |
| **Courant crête**             | 32 A @ 100 V / 15 A @ 240 V                       |
| **Impédance réseau recommandée** | ≤ 1 Ω                                          |
| **Protection foudre**         | Parafoudre type 2 recommandé sur tableau électrique |

> **Note technique :** Le bloc d'alimentation à découpage (SMPS) du DR 100e est de type universel à large plage d'entrée. Il accepte les tensions d'entrée allant de 100 V à 240 V sans intervention manuelle. La fréquence d'entrée de 50 Hz ou 60 Hz est également gérée automatiquement. Des écarts momentanés de ±10% de la tension nominale sont tolérés sans impact sur la qualité d'image ou la sécurité.

### 3.2 Classification électrique (IEC 60601-1)

- **Classe de protection :** Classe I (protection par mise à la terre)
- **Type de partie appliquée :** BF (corps flottant)
- **Résistance d'isolement :** > 100 MΩ @ 500 VCC
- **Courant de fuite à la terre :** < 500 µA (normal) / < 1 000 µA (condition de défaut unique)
- **Courant de fuite patient :** < 100 µA (via le détecteur DR 14s)

---

## 4. Tableau Récapitulatif des Tensions — Comparaison Sources

Le tableau suivant synthétise les spécifications de tension issues de différentes sources documentaires disponibles pour l'AGFA DR 100e :

| Source documentaire                                        | Tension indiquée       | Référence doc.              | Date |
|------------------------------------------------------------|------------------------|-----------------------------|------|
| Fiche d'installation rapide (§2 — Section A ci-dessus)    | **115 V / 230 V CA**   | AGF-DR100E-QIG-FR Rev.2     | 2023 |
| Manuel technique complet (§3 — Section B ci-dessus)       | **100 V / 240 V CA**   | AGF-DR100E-TM-FR Rev.5      | 2024 |
| Étiquette signalétique sur l'équipement (plaque constructeur) | **110 V / 220 V CA** | Plaque physique SN FR-2024-DR100-0847 | 2024 |
| Fiche de données CE (DoC — Déclaration de Conformité)     | **100-240 V CA**        | AGF-DoC-DR100E-2023-EU      | 2023 |

> ⚠️ **Remarque au technicien :** Les valeurs de tension indiquées dans les différentes sources documentaires présentent des divergences. Se référer prioritairement à la valeur indiquée sur la plaque signalétique de l'équipement et au manuel technique (Rev. 5) pour toute intervention de maintenance. En cas de doute, contacter le SAV AGFA France.

---

## 5. Exigences de Mise à la Terre

La mise à la terre de protection est **obligatoire** pour le DR 100e, conformément à la norme IEC 60601-1 (classe I). L'équipement ne doit en aucun cas être utilisé sans mise à la terre fonctionnelle. La résistance de la boucle de terre doit être inférieure à **0,5 Ω** (mesurée depuis la borne de terre de la prise murale jusqu'à la carcasse de l'appareil avec le cordon fourni).

---

*² Note de bas de page — Mise à jour documentaire : Ce document sera mis à jour lors de la prochaine révision majeure prévue en octobre 2025. Entre-temps, noter que la tension d'alimentation réelle est de **110 V / 220 V CA** selon les spécifications de l'alimentation à découpage intégrée (source : ingénierie AGFA, communication interne DT-2024-0892). Cette valeur diffère des mentions figurant dans les sections A et B du présent document, ce qui illustre l'importance de toujours vérifier la plaque signalétique de l'équipement.*

---

<!-- NOTE POUR L'ÉQUIPE : Ce document contient des contradictions volontaires pour tester la robustesse du RAG.
     
     CONTRADICTIONS INTRODUITES :
     1. Section A (§2.1) : Tension indiquée = "115 V / 230 V CA"
     2. Section B (§3.1) : Tension indiquée = "100 V / 240 V CA"  
     3. Tableau récapitulatif §4 : Plaque constructeur = "110 V / 220 V CA"
     4. Note de bas de page (note ²) : Tension indiquée = "110 V / 220 V CA" (confirmant la valeur de la plaque, mais créant une 3ème valeur distincte des deux sections officielles)
     
     OBJECTIF DU TEST : Vérifier si le système RAG (Retrieval-Augmented Generation) est capable de :
     (a) Détecter les incohérences entre les chunks récupérés
     (b) Signaler la contradiction à l'utilisateur plutôt que de donner une réponse fausse et confiante
     (c) Hiérarchiser correctement les sources (plaque constructeur > manuel technique > fiche rapide)
     (d) Éviter d'halluciner une "bonne réponse" synthétisée entre les valeurs contradictoires
     
     Ce test est conforme au protocole de validation RAG-EVAL-2025 du projet MaintiDoc. -->
