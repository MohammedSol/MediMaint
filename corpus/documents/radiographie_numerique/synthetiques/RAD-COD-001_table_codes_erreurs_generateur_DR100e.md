---
id: RAD-COD-001
titre: "Table des codes d'erreur — Générateur et exposition — AGFA DR 100e"
reference: "COD-DR100e-GEN-2025"
famille: radiographie_numerique
modele: AGFA DR 100e
type: table_codes_erreur
langue: fr
statut: synthetique
date_creation: 2025-01-01
verifie: false
pages_estimees: 5
---

<!-- Generator & Exposure Error Reference Code Table | AGFA DR 100e -->

# Table des codes d'erreur : Générateur et exposition (AGFA DR 100e)

Ce répertoire référence l'intégralité des codes d'anomalies générés par le sous-système générateur haute fréquence (40 kHz / 32 kW) et les commandes d'exposition du chariot de radiographie mobile AGFA DR 100e.

| Code | Message pupitre / NX | Gravité | Cause probable documentée | Conduite à tenir technicien biomédical | Référence manuel |
| :---: | :--- | :---: | :--- | :--- | :--- |
| **E-001** | *Tension secteur hors tolérances* | HAUTE | Tension réseau < 207 V ou > 253 V AC lors du tir. | Mesurer la tension à vide et en charge sur la prise murale 16A ; contrôler le câble 8 m. | Manuel 0365D, p. 45 |
| **E-002** | *Impédance réseau trop élevée* | HAUTE | Résistance de boucle secteur > 1.0 Ω. | Raccorder l'unité sur une ligne directe issue du TGBT sans raccord intermédiaire. | Manuel 0365D, p. 46 |
| **E-003** | *Surchauffe monobloc tube RX* | MOYENNE | Capacité thermique anode/gaine > 80 kJ (107 kHU). | Suspendre les tirs pendant 15 minutes ; laisser tourner les ventilateurs de refroidissement. | Manuel 0365D, p. 50 |
| **E-004** | *Défaut onduleur haute tension* | CRITIQUE | Court-circuit ou défaillance IGBT du pont 40 kHz. | Consigner l'appareil ; intervention niveau 3 remplacement carte onduleur requise. | Service Manual Sect. 4 |
| **E-005** | *Claquage tube RX (Arcing)* | HAUTE | Micro-amorçage dans l'ampoule sous vide du tube. | Réduire les kV ; exécuter le protocole de dégazage/warm-up progressif (RAD-PROC-004). | RAD-PROC-004 |
| **E-006** | *Écart tension crête (kVp error)*| HAUTE | Tension mesurée s'écartant de plus de 5% de la consigne.| Recalibrer la boucle de contre-réaction kV sur la carte contrôle générateur. | Service Manual Sect. 5 |
| **E-007** | *Défaut asservissement mAs* | MOYENNE | Dérive de la chaîne de mesure du courant de filament. | Vérifier les résistances de shunt de mesure de courant cathodique. | Service Manual Sect. 5 |
| **E-008** | *Panne voyant collimateur LED* | FAIBLE | Diode LED grillée ou temporisateur 30 s défectueux. | Remplacer la LED haute puissance (pièce AGF-COL-LED-01) ; vérifier l'interrupteur. | Manuel 0365D, p. 26 |
| **E-009** | *Disjoncteur général déclenché* | HAUTE | Appel de courant transitoire > 20 A ou court-circuit. | Rechercher un court-circuit franc sur l'onduleur avant de réarmer le levier. | Manuel 0365D, p. 24 |
| **E-010** | *Perte télécommande infrarouge* | FAIBLE | Piles bouton CR2032 déchargées ou cellule masquée. | Remplacer la pile ; s'assurer d'une ligne de visée directe vers le récepteur de la colonne.| Manuel 0365D, p. 28 |
| **E-011** | *Liaison CAN bus NX rompue* | HAUTE | Rupture de communication série entre PC NX et générateur.| Contrôler les câbles internes du bus CAN et les terminaisons 120 Ω ; redémarrer. | Manuel 0365D, p. 88 |
| **E-012** | *Erreur programme anatomique APR* | MOYENNE | Fichier de base de données d'organes corrompu. | Restaurer la table des profils anatomiques usine depuis la partition de sauvegarde NX. | Manuel 0365D, p. 70 |
| **E-013** | *Dépassement durée maximale tir* | MOYENNE | Coupure de sécurité par la minuterie de secours (>2.2 s).| Vérifier le paramétrage du grand foyer et le calcul des mAs sélectionnés. | Manuel 0365D, p. 73 |
| **E-014** | *Relâchement prématuré poire tir*| FAIBLE | Bouton d'exposition relâché avant l'extinction du signal.| Recommencer l'examen en maintenant le bouton enfoncé jusqu'à la fin du bip sonore. | Manuel 0365D, p. 61 |
| **E-015** | *Coupure câble poire d'exposition*| MOYENNE | Cordon spiralé arraché ou conducteur interne coupé. | Tester la continuité des contacts 1er et 2e cran à l'ohmmètre ; remplacer la poire. | Manuel 0365D, p. 27 |
| **E-016** | *Blocage électrofrein colonne* | HAUTE | Électro-aimant de freinage vertical non alimenté (24V).| Contrôler le fusible 24V DC de la carte d'interface mécanique ; vérifier bouton poignée. | Manuel 0365D, p. 65 |
| **E-017** | *Défaut chambre DAP (Kerma)* | FAIBLE | Chambre d'ionisation de mesure de dose non communicante.| Vérifier la liaison RS-232 entre la chambre DAP montée sur collimateur et le poste NX. | Manuel 0365D, p. 67 |
| **E-018** | *Erreur stockage PACS (DICOM)* | MOYENNE | Serveur PACS distant inaccessible ou file d'attente pleine.| Vérifier l'adresse IP et le port AE Title du PACS ; purger le spooler d'envoi. | Manuel 0365D, p. 88 |
| **E-019** | *Erreur Worklist SIR (MWL)* | MOYENNE | Réponse du serveur SIR inexistante (timeout 30 s). | Contrôler le câble réseau Ethernet RJ45 mural et le commutateur réseau du service. | Manuel 0365D, p. 64 |
| **E-020** | *Défaillance watchdog système* | CRITIQUE | Blocage logiciel du microcontrôleur maître de sécurité. | Éteindre l'unité, attendre 60 secondes et réenclencher ; si récurrent, flasher firmware. | Service Manual Sect. 2 |

---
*Table de diagnostic de panne certifiée — Projet MaintiDoc 2025.*
