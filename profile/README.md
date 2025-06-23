# 💸 NexBudge

**NexBudge** est une application web moderne, sécurisée et puissante pour gérer vos finances personnelles ou professionnelles. Pensée pour être accessible, intuitive et évolutive, elle s’adresse aussi bien aux particuliers qu’aux entreprises.

---

## 🚀 Fonctionnalités

### 🔐 Comptes utilisateurs
- Inscription en tant que **particulier**, **entreprise** ou **démo**
- Gestion multi-budgets (ex. perso + pro)
- Authentification sécurisée
- Données sensibles chiffrées

### 💰 Budgets et opérations
- Suivi des **revenus**, **dépenses**, **remboursements**
- Gestion des **abonnements** (alertes, renouvellements)
- Organisation par **catégories**, **types**, **moyens de paiement**, **devises**
- Support **multi-devises** avec taux personnalisés

### 📊 Statistiques et rapports
- Graphiques dynamiques
- Statistiques hebdo / mensuelles
- Export des données (CSV, PDF…)

### 🔔 Notifications personnalisées *(en réflexion)*
- Email
- Message privé Discord (via bot)
- Web push (PWA)
- SMS (premium)
- Alertes dans l’interface

---

## 🧩 Stack technique

| Composant     | Technologie      |
|---------------|------------------|
| **Frontend**  | Angular           |
| **Backend**   | Python (Flask ou Django) |
| **Base de données** | SQL (UUIDs, relations, sécurité) |
| **PWA**       | Compatible via `manifest.json` + `service worker` |
| **Notifications** | Système modulaire prévu (Discord, Mail, Push…) |

---

## 🧱 Modèle de données (extraits)

```sql
CREATE TABLE account_type (
   account_type_id INT AUTO_INCREMENT PRIMARY KEY,
   name VARCHAR(50) NOT NULL UNIQUE
);

CREATE TABLE user (
   user_id VARCHAR(36) NOT NULL DEFAULT (UUID()),
   first_name VARCHAR(100) NOT NULL,
   last_name VARCHAR(100) NOT NULL,
   email VARCHAR(255) NOT NULL,
   password VARCHAR(255) NOT NULL,
   account_type_id INT NOT NULL,
   company_name VARCHAR(100),
   vat_number VARCHAR(50),
   FOREIGN KEY (account_type_id) REFERENCES account_type(account_type_id)
);
````

> 🔐 Données sécurisées & architecture propre

---

## 🌍 Déploiement

À venir :

* Frontend déployé sur Vercel / Netlify
* Backend API hébergée (Docker + HTTPS)
* PWA installable sur mobile / desktop
* Version print-friendly & version PDF dispo

---

## 📩 Contact

Pour toute question ou suggestion :
📧 [contact@nexbudge.com](mailto:contact@nexbudge.com)
🌐 [https://nexbudge.com](https://nexbudge.com)

---

## 🧠 À propos

Projet de fin d’études full-stack Python (Technofutur TIC)
Créé et conçu par **Alexandre Lison** (alias *Laxe4k*)
Pensé pour apprendre, progresser, et pourquoi pas... révolutionner la gestion de budget 😉