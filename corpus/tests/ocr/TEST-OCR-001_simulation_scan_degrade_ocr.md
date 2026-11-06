---
id: TEST-OCR-001
titre: "Document de test — Simulation de rapport biomédical dégradé (Test OCR)"
reference: "TEST-OCR-001-DEG-2025"
famille: radiographie_numerique
modele: AGFA DR 100e
type: test_ocr
objectif_test: "Tester la capacité du RAG à extraire du sens malgré du texte bruité simulant un scan papier détérioré"
langue: fr
statut: test_ocr
date_creation: 2025-01-01
verifie: true
pages_estimees: 2
---

<!-- DOCUMENT DE TEST ROBUSTESSE OCR — TEXTE BRUITÉ VOLONTAIREMENT -->

# R4PP0RT D'1NT3RV3NTI0N B10MÉD1C4L3 — CH4R10T M0B1L3 RX

**D4T3 :** 14/11/2O24  
**T3CHN1C13N :** P. DUP0NT (S3RV1C3 B10M3D)  
**APPAR31L :** AGFA DR 1OOe — S/N : FR-2O24-DR1OO-O847  
**ST4TUT :** M41NT3N4NC3 C0RR3CT1V3 D'URG3NC3  

---

### C0NST4T D3 P4NN3 (D0LÉ4NC3S S01GN4NTS) :
L'un1té m0b1le s'est c0upée brüt4lem3nt pend4nt un cl1ché de th0r4x en ch4mbr3 2O4. 
Le té-m01n d'4l1m3nt4t1on cl1gn0t41t en r0uge et un c0de d'3rr3ur **E-OO1** ét41t v1s1ble 
sur l3 pup1tre g3n3r4t3ur. 1mp0ss1bl3 de rel4nc3r le t1r.

---

### D14GN0ST1C 3T M3SUR3S :
1. C0ntr0l3 de l4 tens10n à l4 pr1s3 mur4le : m3suré **194 V0lts AC** (t0lér4nce n0rm4le : 2O7 à 253 V). 
   L4 l1gn3 3st s0us-d1m3ns10nnée d4ns l'41le n0rd du b4t1m3nt.
2. C0ntr0l3 du c4bl3 s3ct3ur 8 mèt-r3s : c0nduct3ur d3 ph4s3 lé-gèr3m3nt éc-r4sé à 1,5 m de l4 f1ch3.
3. R3s1st4nc3 de b0ucl3 d3 t3rr3 : O,18 Ohms (c0nf0rm3).

---

### TR4V4UX R34L1S3S :
- R3mpl4c3m3nt de l4 f1ch3 m4l3 16A et r4cc0urc1ss3m3nt du c4bl3 s3ct3ur à 7,5 mèt-r3s.
- Dép-l4c3m3nt du ch4r10t sur une pr1s3 mur4l3 d3 d3rv4t10n s3c0urue (t3ns10n r3v3nu3 à 228 V AC).
- R34rm3m3nt du d1sj0nct3ur g3n3r4l.
- Ré4l1s4t10n d3 5 t1rs d'3ss41 sur f4nt0m3 à 80 kV / 2.5 mAs : t0us c0nf0rm3s, 4ucun c0de E-001.

**C0NCLUS10N :** App4r31l r3m1s en s3rv1c3 cl1n1qu3 l3 14/11/2O24 à 16h45.

---
<!-- 
NOTE POUR L'ÉVALUATION DE L'AGENT :
Ce document simule une extraction OCR brute et dégradée (substitutions de caractères style leet-speak 0/O, 1/I, coupures de mots avec tirets).
TEST ATTENDU :
Le technicien pose la question : "Quel problème a provoqué l'erreur E-001 sur le DR 100e le 14 novembre 2024 et comment a-t-il été résolu ?"
L'agent doit comprendre que la panne était une tension secteur basse (194V) sur une prise murale avec câble écrasé, résolue par raccourcissement du câble et branchement sur une prise secourue 228V.
-->
