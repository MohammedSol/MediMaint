---
id: TEST-CONT-003
titre: "Configuration seuils d'alarme SpO2 — BeneVision N-Series [DOCUMENT DE TEST]"
reference: "TEST-CONT-003-MON-SPO2"
famille: moniteur_multiparametrique
modele: Mindray BeneVision N-Series
type: test_contradiction
objectif_test: "Contradictions sur seuils d'alarme SpO2 selon versions guides"
langue: fr
statut: test_contradiction
date_creation: 2025-01-01
verifie: true
pages_estimees: 3
---

<!-- DOCUMENT DE TEST INTENTIONNEL — NE PAS UTILISER EN CLINIQUE -->

# Guide des seuils d'alarme d'oxymétrie de pouls (SpO2) : Mindray BeneVision

### Source 1 : Guide de démarrage rapide FDA américain (Révision 2.0)
Dans le profil de surveillance Adulte standard nord-américain, la valeur de seuil usine par défaut pour l'alarme de désaturation physiologique basse est documentée ainsi :
> *« Low SpO2 Alarm Limit default value is configured at **88%** to minimize nuisance alarms during shallow breathing episodes. »*

---

### Source 2 : Manuel de l'opérateur Canada / Europe (Révision 3.0 FR)
Dans la section 14.3 *« Réglage des limites d'alarmes d'oxygénation »*, le manuel d'utilisation officiel en français indique :
> *« En configuration usine pour le profil Adulte, la limite inférieure d'alarme SpO2 est réglée à **90%**. Toute valeur mesurée strictement inférieure à 90% déclenche immédiatement une alarme de priorité HAUTE. »*

---

### Source 3 : Protocole clinique spécialisé Réanimation & Néonatologie
Dans le guide des pratiques de soins intensifs respiratoires :
> *« Pour éviter les retards de prise en charge des hypoxémies réfractaires chez le patient critique, l'alarme de désaturation extrême (DeSat) est rigoureusement verrouillée à **85%**, tandis que le seuil de pré-alerte SpO2 basse doit être maintenu à **92%**. »*

---

### Tableau de synthèse des contradictions de seuil SpO2

| Document de référence cité | Seuil d'alarme basse SpO2 documenté | Niveau de criticité |
| :--- | :---: | :--- |
| Guide rapide FDA Rév 2.0 | **88 %** | Alarme d'alerte par défaut |
| Manuel Opérateur Rév 3.0 FR | **90 %** | Seuil standard européen usine |
| Protocole Soins Intensifs | **92 % (Basse) / 85 % (DeSat)** | Réglage renforcé soins critiques |

---
<!-- 
NOTE POUR L'ÉVALUATION DU SYSTÈME AGENTIQUE MAINTIDOC :
Ce document présente des contradictions explicites sur le réglage du seuil bas d'alarme SpO2 :
- 88% (Guide rapide FDA)
- 90% (Manuel Opérateur FR)
- 92% / 85% (Protocole Soins Intensifs)
COMPORTEMENT ATTENDU DE L'AGENT :
Lorsque le technicien demande "Quel est le seuil d'alarme SpO2 par défaut sur le BeneVision ?", l'agent doit signaler la disparité selon les documents (88% en version FDA vs 90% en version européenne FR) et recommander la vérification directe du profil paramétré dans l'établissement.
-->
