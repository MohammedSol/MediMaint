---
id: RAD-COD-002
titre: "Table des codes d'erreur — Détecteur AGFA DR 14s (WiFi, batterie, capteur)"
reference: "COD-DR14s-DET-2025"
famille: radiographie_numerique
modele: AGFA DR 100e
composant: "Détecteur AGFA DR 14s"
type: table_codes_erreur
langue: fr
statut: synthetique
date_creation: 2025-01-01
verifie: false
pages_estimees: 4
---

<!-- Detector Diagnostics Table | AGFA DR 14s / DR 17s Dura-line Panels -->

# Table des codes d'erreur : Détecteur sans fil DR 14s (WiFi, batterie, capteur)

### 1. États du témoin lumineux d'état (LED multi-couleurs du boîtier détecteur)

| Couleur LED | Comportement | Signification fonctionnelle | Action requise |
| :---: | :--- | :--- | :--- |
| **Vert** | Fixe | Connecté en WiFi, prêt pour exposition, batterie > 50%. | Aucune, appareil opérationnel. |
| **Vert** | Clignotement lent | Prêt pour exposition, batterie moyenne (20% à 50%). | Prévoir recharge au dock sous 60 min. |
| **Orange** | Fixe | En cours de synchronisation ou de transfert d'image vers NX. | Attendre la fin du transfert. |
| **Orange** | Clignotant | Batterie faible critique (< 15%), transfert prioritaire. | Insérer immédiatement dans le dock de charge. |
| **Rouge** | Clignotement rapide| Erreur de liaison sans fil ou perte de trame image. | Voir code erreur affiché sur station NX. |
| **Rouge** | Fixe | Erreur matérielle critique du capteur ou choc violent détecté. | Diagnostic biomédical requis (voir codes D-Sxx). |

---

### 2. Répertoire des codes d'erreur spécifiques du détecteur DR 14s

| Code | Sous-système | Message d'erreur NX | Cause technique documentée | Action corrective préconisée |
| :---: | :---: | :--- | :--- | :--- |
| **D-W01** | WiFi | *Détecteur hors de portée sans fil* | Distance détecteur-chariot > 10 m ou cloisons plombées intermédiaires. | Rapprocher le détecteur de l'unité mobile DR 100e. |
| **D-W02** | WiFi | *Interférence canal radiofréquence 5 GHz*| Saturation du spectre WiFi hospitalier sur le canal courant. | Configurer l'Ad-Hoc WiFi sur une fréquence DFS moins encombrée. |
| **D-W03** | WiFi | *Échec négociation clé WPA2/WPA3* | Désynchronisation de la clé cryptographique partagée. | Réinsérer le détecteur 10 secondes dans le dock d'appairage filaire. |
| **D-B01** | Batterie | *Batterie détecteur trop faible pour tir* | Tension pack batterie < 10,2 V DC. | Remplacer le pack batterie par un pack chargé ou brancher le câble d'attache. |
| **D-B02** | Batterie | *Température batterie excessive (> 45 °C)* | Échauffement anormal des cellules Li-ion lors d'une charge rapide. | Laisser refroidir ; contrôler le chargeur docking station. |
| **D-B03** | Batterie | *Défaut interne circuit BMS batterie* | Rupture de communication sur le bus I2C/SMBus du pack batterie. | Remplacer la batterie (RAD-PROC-002). |
| **D-S01** | Capteur | *Dérive d'offset thermique capteur* | Température de la matrice TFT s'écartant de la plage de calibration. | Patienter 5 min pour stabilisation thermique ou relancer un Dark Field. |
| **D-S02** | Capteur | *Saturation globale de la matrice (ADC)* | Dose de rayonnement incidente supérieure au seuil d'écrêtage (> 100 µGy).| Diminuer les mAs et kV sur le générateur. |
| **D-S03** | Capteur | *Détection d'impact mécanique violent* | Accéléromètre 3 axes interne ayant enregistré un choc > 15 g (chute sol).| Vérifier la planéité et faire un contrôle qualité d'image (RAD-PROC-003). |
| **D-S04** | Capteur | *Ligne morte détectée (Open line)* | Rupture de liaison d'un circuit intégré driver de grille flexible (TAB).| Remplacement du capteur auprès du SAV Agfa sous garantie/échange standard. |
| **D-S05** | Capteur | *Matrice NUC invalide ou périmée* | Date de validité de la calibration semestrielle dépassée (> 180 jours).| Exécuter immédiatement la procédure d'étalonnage NUC (RAD-PROC-003). |
| **D-S06** | Capteur | *Présence d'humidité interne anormale* | Déclenchement de la sonde d'hygrométrie interne suite à immersion liquide.| Arrêt immédiat ; séchage en étuve sèche ventilée à 35 °C pendant 24h. |

---
*Tableau de référence technique DR 14s MaintiDoc 2025.*
