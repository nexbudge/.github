# 💸 NexBudge

**NexBudge** est une application web pensée pour aider n'importe qui — particulier ou professionnel — à mieux gérer son argent. Elle permet de suivre ses dépenses, ses revenus, ses abonnements, ses devises, tout en conservant ses données en toute sécurité. C’est un projet pédagogique sérieux, développé dans un cadre professionnel, avec une vision claire : rendre la gestion financière plus intuitive, personnalisée, et évolutive.

---

## ❓ C’est quoi exactement NexBudge ?

C’est une **application web** qui permet de :

* Créer un ou plusieurs budgets (ex. personnel + entreprise)
* Gérer toutes les opérations (revenus, achats, abonnements)
* Suivre l’évolution de ses finances avec des graphiques
* Être alerté en cas de dépassement, renouvellement ou événement important
* Accéder à toutes ses données sur mobile ou ordinateur

Tu peux créer un compte, y associer ton entreprise ou utiliser un mode démo. Et surtout, **tes données sont chiffrées et sécurisées**.

---

## 🚀 Fonctionnalités principales

### 🔐 Comptes utilisateurs

* Inscription avec 3 rôles possibles : **particulier**, **entreprise**, ou **compte démo**
* Authentification sécurisée (chiffrage des mots de passe, sessions protégées)
* Gestion multi-budgets depuis un seul compte (ex. un budget pour toi, un autre pour ton activité freelance)

### 💰 Budgets et opérations

* Ajout, modification et suppression d'opérations (revenus, dépenses, remboursements)
* Gestion des **abonnements** avec alertes de renouvellement
* Classement des opérations par **catégories** (ex : alimentation), **types** (fixe ou variable), **moyens de paiement** (CB, PayPal, espèces…), et **devises** (EUR, USD, CHF…)
* **Multi-devises** : convertisseur intégré avec taux personnalisés

### 📊 Statistiques et rapports

* Graphiques interactifs (camemberts, courbes, histogrammes)
* Vue hebdomadaire, mensuelle, annuelle
* Export des données : CSV, PDF, impression

### 🔔 Notifications personnalisées *(fonctionnalité à venir)*

* Email
* Message privé Discord via un bot dédié
* Notifications web (PWA)
* SMS (fonction premium)
* Alertes directement visibles dans l’interface

---

## 🧱 Technologies utilisées (stack technique)

| Élément          | Technologie choisie            | Pourquoi ?                                       |
| ---------------- | ------------------------------ | ------------------------------------------------ |
| Frontend         | Angular                        | Framework moderne pour créer une PWA interactive |
| Backend          | Django + Django REST Framework | Puissant, structuré, sécurisé                    |
| Base de données  | MariaDB                        | Rapide, compatible SQL, facile à maintenir       |
| Authentification | JWT ou sessions sécurisées     | Adapté à une API REST + front Angular            |
| Déploiement      | Docker + hébergement HTTPS     | Pour une mise en ligne stable et sécurisée       |

> 🔐 Tout est pensé pour la **sécurité**, la **clarté**, et la **maintenabilité** du code.

---

## 📦 Extrait du modèle de données SQL

```sql
CREATE TABLE account_type (
   account_type_id INT AUTO_INCREMENT PRIMARY KEY,
   name VARCHAR(50) NOT NULL UNIQUE
);

CREATE TABLE user (
   user_id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
   first_name VARCHAR(100) NOT NULL,
   last_name VARCHAR(100) NOT NULL,
   email VARCHAR(255) NOT NULL UNIQUE,
   password VARCHAR(255) NOT NULL,
   account_type_id INT NOT NULL,
   company_name VARCHAR(100),
   vat_number VARCHAR(50),
   FOREIGN KEY (account_type_id) REFERENCES account_type(account_type_id)
);
```

---

## 🌍 Déploiement prévu

* **Frontend** hébergé sur [Infomaniak Managed Hosting](https://www.infomaniak.com/fr/hebergement-web) ou à défaut sur Vercel/Netlify
* **Backend API** conteneurisé via Docker, avec configuration HTTPS
* **Base de données MariaDB** sur Infomaniak DBaaS ou serveur dédié sécurisé
* **Application PWA** installable sur mobile ou PC
* **Fonctionnalité d’export PDF** intégrée dans l’interface

> 🎯 Le choix d’**Infomaniak** assure un hébergement écologique, performant, basé en Suisse et conforme RGPD.

---

## 📩 Contact et support

Tu veux poser une question, suggérer une amélioration ou juste dire bonjour ?

* 📧 [contact@nexbudge.com](mailto:contact@nexbudge.com)
* 🌐 [https://nexbudge.com](https://nexbudge.com)

---

## 🧠 À propos du projet

Ce projet a été conçu dans le cadre d’une **formation full-stack Python** au **Technofutur TIC**, en Belgique.

Il a été imaginé, structuré et développé par **Alexandre Lison** (*alias Laxe4k*) pour :

* Mettre en pratique des compétences en développement web moderne
* Créer un outil concret, utile, avec une vraie valeur
* Approfondir les notions de sécurité, structuration d’API, et gestion de données

C’est plus qu’un exercice : **c’est un vrai produit**, que l’on souhaite faire évoluer après la formation.

---

## 🚫 Code source non public

NexBudge est un projet **privé et propriétaire**. Le code source n’est **pas disponible publiquement**.

Cette décision vise à :

* Protéger la logique métier et l'effort investi
* Préserver l'intégrité de la solution
* Préparer d’éventuelles évolutions commerciales ou professionnelles

Toute reproduction ou diffusion du contenu, du design ou des fonctionnalités est interdite sans autorisation écrite préalable.

Merci de votre compréhension. 🙏
