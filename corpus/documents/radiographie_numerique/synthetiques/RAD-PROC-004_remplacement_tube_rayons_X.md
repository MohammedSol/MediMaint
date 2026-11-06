---
id: RAD-PROC-004
titre: "Procédure de remplacement du tube à rayons X — DR 100e"
reference: "PROC-DR100e-TUBE-RX-2025"
famille: radiographie_numerique
modele: AGFA DR 100e
type: procedure_remplacement
duree_estimee: "4h00"
qualification_requise: "Ingénieur service agréé Agfa — OBLIGATOIRE"
langue: fr
statut: synthetique
date_creation: 2025-03-01
verifie: false
pages_estimees: 6
---

<!-- Critical Service Procedure | AGFA DR 100e Tube Assembly Replacement -->

# Procédure de remplacement du tube à rayons X et monobloc : AGFA DR 100e

> **DANGER CRITIQUE : HAUTE TENSION (125 000 VOLTS) ET RISQUE RADIOLOGIQUE**  
> Cette intervention engage la sécurité physique des intervenants. Elle doit être réalisée impérativement hors tension, par deux techniciens habilités, avec décharge manuelle complète des bancs de condensateurs de puissance du générateur haute tension.

---

### 1. Spécifications du monobloc de remplacement
- **Désignation :** Ensemble Monobloc Haute Tension avec tube radiogène à anode tournante.
- **Référence pièce constructeur :** AGF-MB32KW-MX125 (Capacité thermique monobloc : 600 kJ / 800 kHU ; Angle anodique : 15° ; Vitesse : 3 000 rpm).

---

### 2. Déroulement chronologique de l'intervention

#### Phase 1 : Consignation électrique et sécurisation mécanique (45 min)
1. Mettez le poste de travail NX hors tension, puis abaissez le disjoncteur général de l'unité mobile DR 100e.
2. Débranchez la fiche secteur 230 V murale et cadenassez la prise mâle (Procédure LOTO - Lock Out / Tag Out).
3. Verrouillez la colonne télescopique en position basse de transport à l'aide de la goupille de sécurité mécanique afin d'éviter toute détente brutale des contrepoids d'équilibrage lors du retrait de la masse du monobloc (environ 18 kg).
4. Ouvrez le capot d'accès au générateur. À l'aide d'une perche de décharge isolée 100 kV munie d'une résistance de 10 kΩ 50W, mettez à la masse les bornes positives et négatives du banc de condensateurs haute tension. Mesurez la tension résiduelle au voltmètre (< 5 V exigé avant toute manipulation).

#### Phase 2 : Dépose du monobloc défaillant (1h00)
1. Déconnectez le faisceau de câbles basse tension (commande moteur d'anode, capteurs thermiques PT100 et asservissement du collimateur).
2. Dévissez les 4 vis d'accouplement du collimateur manuel et déposez délicatement le boîtier du collimateur.
3. Déconnectez les connecteurs rapides haute tension protégés par graisse silicone diélectrique.
4. À l'aide de la sangle de levage adaptée, soutenez le monobloc pendant que le second technicien desserre les vis de bride du support de cardan.
5. Déposez l'ensemble monobloc usagé sur un chariot de transport stable.

#### Phase 3 : Pose et raccordement du monobloc neuf (1h15)
1. Présentez le monobloc neuf AGF-MB32KW-MX125 sur le berceau de rotation du bras porte-tube.
2. Engagez les vis de fixation et serrez au couple prescrit de 18 Nm à l'aide d'une clé dynamométrique étalonnée.
3. Nettoyez les embouts haute tension avec un chiffon non pelucheux sec, appliquez un film uniforme de pâte diélectrique silicone haute isolation (Dow Corning DC4), puis engagez les fiches HT jusqu'au verrouillage mécanique franc.
4. Remontez le collimateur manuel et reconnectez l'ensemble des faisceaux de commande et de retour thermique.

#### Phase 4 : Procédure obligatoire de dégazage et rodage du tube (Warm-up) (1h00)
Ne jamais appliquer immédiatement une tension élevée sur un tube neuf sous vide ! Exécutez le programme de rodage progressif suivant via la console de service :

| Palier de rodage | Tension kVp | Charge mAs | Temps de pause entre tirs | Nombre d'expositions |
| :---: | :---: | :---: | :---: | :---: |
| **Palier 1** | 50 kV | 10 mAs | 30 secondes | 3 tirs |
| **Palier 2** | 70 kV | 20 mAs | 30 secondes | 3 tirs |
| **Palier 3** | 90 kV | 32 mAs | 45 secondes | 3 tirs |
| **Palier 4** | 110 kV | 50 mAs | 60 secondes | 2 tirs |
| **Palier 5** | 125 kV | 80 mAs | 90 secondes | 2 tirs |

Si aucun amorçage ou claquage (arcing) n'est survenu, procédez au contrôle de reproductibilité de dose et au test de fuite radiologique de gaine à 125 kV conformément à la norme NFC 15-160.

---
*Intervention de service niveau 3 — Projet MaintiDoc 2025.*
