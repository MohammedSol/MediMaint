---
id: RAD-COD-003
titre: "Table des messages d'état — Application NX Workstation (AGFA DR 100e)"
reference: "COD-NX-MSG-2025"
famille: radiographie_numerique
modele: AGFA DR 100e
composant: "Application NX Workstation"
type: table_messages_etat
langue: fr
statut: synthetique
date_creation: 2025-01-01
verifie: false
pages_estimees: 4
---

<!-- Application Notification Table | AGFA NX Workstation Platform -->

# Messages d'état et notifications de l'application NX Workstation

Cette table documente les bannières textuelles, fenêtres modales et alertes contextuelles générées par le logiciel d'acquisition radiologique Agfa NX Workstation installé sur la console tactile de l'AGFA DR 100e.

| Catégorie | Message affiché à l'écran | Couleur bandeau | Impact opérationnel | Action requise par l'opérateur / technicien |
| :---: | :--- | :---: | :--- | :--- |
| **INFO** | *Prêt pour l'exposition* | Vert | Nominal | Déclencher le tir via la commande à main. |
| **INFO** | *Traitement MUSICA en cours...* | Bleu | Transitoire (2 s) | Patienter pendant le filtrage fréquentiel multi-échelles. |
| **INFO** | *Transmission DICOM terminée avec succès*| Vert | Nominal | L'examen est correctement archivé sur le PACS. |
| **INFO** | *SmartRotate : Orientation automatique appliquée* | Bleu | Informatif | Vérifier visuellement l'orientation du cliché (gauche/droite). |
| **AVERT** | *Indice d'exposition (EI) élevé - Risque sur-dose* | Jaune | Qualité / ALARA | Vérifier si les paramètres mAs n'étaient pas surévalués. |
| **AVERT** | *Indice d'exposition (EI) bas - Bruit quantique* | Jaune | Risque diagnostic | Contrôler si l'image n'est pas bruitée (mouchetée). |
| **AVERT** | *Espace disque local NX inférieur à 10%* | Jaune | Stockage | Purger les examens déjà synchronisés avec le PACS. |
| **AVERT** | *Batterie du détecteur < 20%* | Jaune | Autonomie | Repositionner le détecteur sur le dock dès la fin de l'examen. |
| **AVERT** | *Calibration NUC recommandée (échéance proche)*| Jaune | Maintenance | Planifier l'étalonnage sous 15 jours avec le biomédical. |
| **ERREUR** | *Détecteur DR non détecté sur le réseau sans fil* | Rouge | Blocage tir | Contrôler l'allumage du détecteur et la liaison WiFi. |
| **ERREUR** | *Échec envoi PACS (Serveur ne répond pas)* | Rouge | Archivage différé | Les images sont stockées dans le buffer local ; relancer plus tard. |
| **ERREUR** | *Incohérence des identifiants patient (IPP)* | Rouge | Juridique / Qualité | Corriger les données d'identification via le menu Réconciliation. |
| **ERREUR** | *Défaut de synchronisation générateur-détecteur* | Rouge | Blocage tir | Redémarrer le poste NX ; vérifier le câble d'interface interne. |
| **SÉCUR** | *RAYONS X EN COURS - NE PAS OUVRIR* | Rouge clignotant | Radioprotection | Zone d'exclusion active ; attendre l'extinction complète. |
| **SÉCUR** | *Température tube critique - Tir interdit* | Rouge | Sécurité matériel | Attendre le refroidissement commandé par la sécurité thermique. |

---
*Référentiel des messages NX Workstation MaintiDoc 2025.*
