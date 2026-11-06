---
id: MON-SEC-002
titre: "Fiche de sécurité — Électrique et protection à la défibrillation — BeneVision N-Series"
reference: "SEC-BeneVision-ELEC-DEFIB-2025"
famille: moniteur_multiparametrique
modele: Mindray BeneVision N-Series
type: fiche_securite
categorie_securite: electrique_defibrillation
langue: fr
normes: ["CEI 60601-1", "CEI 60601-2-27", "CEI 60601-1-2"]
statut: synthetique
date_creation: 2025-01-01
verifie: false
pages_estimees: 4
---

<!-- Defibrillation & Electrical Safety Guide | Mindray BeneVision N-Series -->

# Fiche de sécurité : Protection contre la défibrillation et sécurité électrique (BeneVision)

### 1. Classification de protection du patient (CEI 60601-1 / CEI 60601-2-27)
- **Degré de protection des entrées patient :** Parties appliquées de **Type CF protégées contre la défibrillation** (symbole du cœur entouré d'un carré avec les palettes de défibrillation).
- Cette classification garantit que :
  1. Le moniteur supporte l'application directe d'un choc électrique de défibrillation jusqu'à **360 Joules biphasique** (tension crête jusqu'à 5 000 V) sans subir d'endommagement de ses circuits internes.
  2. L'énergie de décharge du défibrillateur n'est pas absorbée par les câbles du moniteur (restitution de > 90% de l'énergie au myocarde du patient).
  3. Le tracé ECG réapparaît à l'écran de manière stable et exploitable en moins de **5 secondes** après la décharge.

---

### 2. Consignes vitales lors de la délivrance d'un choc électrique de défibrillation

> **DANGER : Risque d'électrisation mortelle de l'opérateur**  
> Lors de la délivrance du choc par les palettes ou les patches adhésifs du défibrillateur externe :
> - Ne toucher ni le patient, ni le lit, ni le moniteur, ni les câbles ou modules de mesure.
> - S'assurer que le liquide de perfusion ou d'irrigation ne ponte pas les électrodes avec les parties métalliques du brancard.

> **ATTENTION : Utilisation exclusive de câbles patients d'origine Mindray certifiés Defib-Proof**  
> L'utilisation de cordons ECG adaptateurs tiers non équipés de résistances de protection série intégrées (1 kΩ haute énergie) annule la protection du moniteur et expose à des brûlures cutanées au point de contact des électrodes.

> **ATTENTION : Positionnement des palettes de défibrillation**  
> Ne jamais placer les palettes ou électrodes de défibrillation directement au contact ou à moins de 5 cm des électrodes de surveillance ECG ou des capteurs de température cutanés.

---

### 3. Exigences d'essais de sécurité électrique périodiques (Norme CEI 62353)

| Test métrologique | Méthode d'essai | Valeur maximale autorisée |
| :--- | :--- | :---: |
| **Résistance du conducteur de terre (PE)** | Cordon secteur amovible en place | **≤ 0,10 Ω** |
| **Résistance d'isolement secteur / châssis** | Tension d'essai 500 V DC | **≥ 50 MΩ** |
| **Courant de fuite à la terre (Earth Leakage)**| Condition normale (NC) | **≤ 500 µA** |
| **Courant de fuite au châssis (Touch Current)**| Condition normale (NC) | **≤ 100 µA** |
| **Courant de fuite patient Type CF (ECG)** | Condition normale (NC) | **≤ 10 µA** |
| **Courant de fuite patient Type CF (ECG)** | Premier défaut (SFC) | **≤ 50 µA** |

---

### 4. Procédure post-défibrillation
Immédiatement après l'administration d'un choc de réanimation :
1. Vérifiez la reprise automatique du balayage de l'onde ECG.
2. Si le message *"Saturation ECG"* persiste plus de 10 secondes, touchez la commande logicielle **Réapprendre ECG** pour réinitialiser les amplificateurs différentiels d'entrée.
3. Contrôlez l'adhérence des électrodes qui ont pu être soufflées par la décharge ou déplacées par le massage cardiaque.

---
*Protocole de sécurité électrique et réanimation MaintiDoc 2025.*
