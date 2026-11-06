---
id: MON-COD-002
titre: "Table des alarmes techniques — BeneVision N-Series"
reference: "COD-BeneVision-TECH-2025"
famille: moniteur_multiparametrique
modele: Mindray BeneVision N-Series
type: table_alarmes
sous_type: alarmes_techniques
langue: fr
statut: synthetique
date_creation: 2025-01-01
verifie: false
pages_estimees: 5
---

<!-- Technical & Hardware Alarm Guide | Mindray BeneVision N-Series -->

# Table des alarmes techniques et matérielles : BeneVision N-Series

Les alarmes techniques identifient les défaillances de capteurs, les déconnexions matérielles et les pannes internes de l'électronique de surveillance sur les moniteurs Mindray BeneVision N12 à N22.

| Code alarme | Message technique affiché | Priorité usine | Cause matérielle identifiée | Solution technique / Action biomédicale |
| :---: | :--- | :---: | :--- | :--- |
| **AL-T01** | *Électrode ECG décollée [Nom Dérivation]*| MOYENNE | Électrode desséchée ou déconnectée de la peau du patient.| Remplacer l'électrode adhésive ; nettoyer la peau ; repositionner. |
| **AL-T02** | *Câble tronc ECG non connecté* | MOYENNE | Câble principal débranché du connecteur multiproches MPM. | Enclencher fermement la fiche multibroches dans le module MPM. |
| **AL-T03** | *Capteur SpO2 débranché du moniteur* | MOYENNE | Prise du câble capteur SpO2 déverrouillée. | Réinsérer la prise capteur jusqu'au verrouillage plastique. |
| **AL-T04** | *Capteur SpO2 non positionné sur patient* | FAIBLE | Doigt retiré du capteur optique ou mauvaise perfusion. | Replacer la pince optique sur un doigt chaud et bien perfusé. |
| **AL-T05** | *Lumière ambiante excessive sur SpO2* | FAIBLE | Éclairage scialytique direct perturbant les photodiodes.| Couvrir le capteur SpO2 d'un champ opaque non stérile. |
| **AL-T06** | *Fuite pneumatique circuit PNI* | MOYENNE | Tubulure PNI débranchée, percée ou raccord rapide fuyant. | Contrôler le serrage du connecteur baïonnette ; remplacer le raccord. |
| **AL-T07** | *Brassard PNI mal positionné / trop lâche*| FAIBLE | Circonférence inadaptée ou brassard flottant sur le bras. | Choisir un brassard adapté à la corpulence ; serrer convenablement. |
| **AL-T08** | *Mouvement excessif patient pendant PNI* | FAIBLE | Artéfacts musculaires interdisant la détection des oscillations.| Demander au patient de ne pas bouger ou différer la mesure. |
| **AL-T09** | *Pression artérielle hors plage de mesure* | FAIBLE | Pression systolique > 280 mmHg ou diastolique < 20 mmHg. | Effectuer une mesure auscultatoire manuelle de contrôle. |
| **AL-T10** | *Sonde de température déconnectée* | FAIBLE | Fiche jack de température T1/T2 débranchée du moniteur. | Rebrancher la sonde ; vérifier la continuité du câble thermistance. |
| **AL-T11** | *Zéro IBP requis avant surveillance* | MOYENNE | Nouveau transducteur de pression invasive branché non taré.| Effectuer la procédure de zéro IBP à l'air libre (MON-MAN-002). |
| **AL-T12** | *Module multiparamétrique MPM non reconnu*| HAUTE | Faux contact sur le connecteur fond de panier du rack. | Éjecter le module MPM et le réinsérer fermement dans la glissière. |
| **AL-T13** | *Batterie interne faible (< 20%)* | FAIBLE | Fonctionnement prolongé sur accumulateur sans secteur. | Raccorder immédiatement le cordon secteur 230 V au moniteur. |
| **AL-T14** | *Batterie critique (< 5%) - Arrêt imminent*| HAUTE | Décharge complète de la batterie interne Li-ion sous 3 min. | Brancher sur secteur d'urgence pour éviter la coupure de surveillance. |
| **AL-T15** | *Défaillance batterie interne Li-ion* | MOYENNE | Capacité résiduelle dégradée ou défaut de charge BMS. | Remplacer l'accumulateur interne (procédure MON-PROC-004). |
| **AL-T16** | *Écran tactile non réactif / Défaut dalle* | HAUTE | Désynchronisation du contrôleur capacitif USB interne. | Recalibrer la dalle tactile ou réinitialiser le contrôleur écran. |
| **AL-T17** | *Défaillance avertisseur sonore d'alarme* | CRITIQUE | Haut-parleur principal interne en circuit ouvert. | Mise en retrait immédiate de l'appareil ; remplacement haut-parleur.|
| **AL-T18** | *Déconnexion réseau centralisé CMS / eGateway*| FAIBLE | Câble Ethernet réseau débranché ou perte de signal WiFi. | Vérifier la prise RJ45 murale et la synchronisation avec le central.|
| **AL-T19** | *Saturation mémoire interne - Purge requise*| FAIBLE | Fichiers d'historique de tendances stockés depuis > 180 jours.| Exporter les données patient archivées et purger la base locale. |
| **AL-T20** | *Erreur intégrité micrologiciel (DSP Error)*| HAUTE | Checksum DSP erroné suite à micro-coupure secteur. | Réinstaller le micrologiciel via clé USB (procédure MON-PROC-003). |

---
*Tableau de maintenance corrective Mindray MaintiDoc 2025.*
