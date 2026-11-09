# 📄 Product Requirements Document (PRD)

**Nom du Projet :** Plateforme Éditoriale "Spirituelle"  
**Statut :** En production (V1.0)  
**Hébergement :** Vercel  
**Dépôt Source :** GitHub  
**Auteur :** Équipe de Développement Web  

---

## 1. Vue d'ensemble & Objectif du Produit

### 1.1 Contexte
La plateforme éditoriale **Spirituelle** a été conçue pour offrir un espace moderne, réactif et fluide dédié à la diffusion et à la consultation d'articles éditoriaux et spirituels. 

### 1.2 Objectifs Principaux
* **Diffusion de contenu :** Présenter les articles de manière claire et lisible sur tous les types d'écrans (Mobile, Tablette, Desktop).
* **Modération & Gestion dynamique :** Filtrer et afficher dynamiquement les articles en fonction de leur statut de validation (approuvé, en attente, archivé) via Supabase.
* **Intégration & Déploiement Continus (CI/CD) :** Maintenir le code source sur **GitHub** et assurer une mise en ligne automatique et sans coupure via la connexion GitHub-Vercel.

---

## 2. Architecture & Stack Technique

Le projet repose sur une chaîne technique moderne allant de la gestion de version jusqu'à la distribution globale :

| Composant | Technologie Utilisée | Rôle dans le Projet |
| :--- | :--- | :--- |
| **Gestion de Code / Versioning** | **GitHub** | Stockage du dépôt principal, gestion des branches et déclenchement des builds. |
| **Structure Web** | **HTML5** | Balisage sémantique pour la structure des pages et l'accessibilité. |
| **Stylisation** | **CSS3 & Tailwind CSS** | Framework CSS utility-first pour un design moderne, responsive et optimisé. |
| **Dynamisme** | **JavaScript (ES6+)** | Interactions client, requêtes asynchrones API/Fetch et manipulation du DOM. |
| **Base de données / Backend** | **Supabase** | Stockage des articles et règles de sécurité d'accès (**RLS - Row Level Security**). |
| **Hébergement & CI/CD** | **Vercel** | Déploiement automatique depuis le dépôt GitHub, certificat SSL/TLS et CDN global. |

---

## 3. Flux de Déploiement (Workflow GitHub ➔ Vercel)

1. **Développement & Validation Locale :** Modification des fichiers (`.html`, `.js`, fichiers Tailwind/CSS).
2. **Gestion de Version sur GitHub :** Commit et `push` du code sur la branche principale (`main` / `master`) du dépôt GitHub.
3. **Trigger Automatique Vercel :** Vercel détecte le nouveau commit sur GitHub, lance la compilation des assets (Tailwind CSS) et déploie la nouvelle version en quelques secondes.
4. **Mise en Production :** Le site est automatiquement mis à jour sans interruption de service.

---

## 4. Spécifications Fonctionnelles (Features)

### 4.1 Interface Utilisateur (Front-End)
* **Design Responsive :** Adaptation aux formats d'écran via Tailwind CSS.
* **Navigation Éditoriale :** Structure épurée valorisant la lecture des articles.

### 4.2 Gestion & Filtrage des Contenus (JavaScript + Supabase)
* **Requêtes API Supabase :** Chargement dynamique des articles enregistrés en base de données.
* **Filtre par Statut :** Affichage sélectif des articles validés par l'administration.
* **Sécurisation des Entrées :** Assainissement du code en JavaScript pour parer les failles XSS.

---

## 5. Exigences Non-Fonctionnelles (Sécurité & Maintien du Code)

* **Traçabilité du Code (GitHub) :** Historique complet des commits, gestion de versions et réversion rapide en cas de bug.
* **Sécurité des Données (Supabase) :** Politiques **RLS** actives pour verrouiller l'accès direct aux tables SQL.
* **Sécurité du Transport (Vercel) :** HTTPS natif, HSTS et en-têtes HTTP sécurisés.

---

## 6. Feuille de Route & Évolutions Futures (Roadmap V2)

1. **GitHub Actions / Tests Automatisés :** Mise en place d'un workflow GitHub Actions pour valider la qualité du code (linter HTML/JS) avant chaque fusion de branche.
2. **Espace Rédacteur :** Formulaire de soumission d'articles directement relié à Supabase.
3. **Tableau de Bord Administrateur :** Validation des articles en attente.