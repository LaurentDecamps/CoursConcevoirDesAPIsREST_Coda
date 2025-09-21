# Formation API RESTful - 2 jours en pédagogie active

## 📋 Objectifs pédagogiques
* Définir ce qu'est une API distante et identifier son rôle dans la communication entre services
* Expliquer les principes d'une API RESTful (verbes HTTP, statuts, ressources)
* Concevoir une API RESTful simple avec les bonnes pratiques
* Documenter une API RESTful à l'aide d'OpenAPI
* Appliquer les bonnes pratiques de sécurité et performance
* Identifier les différents styles d'API (REST, GraphQL, gRPC) et leurs cas d'usage

---

# 🗓️ JOUR 1 : Comprendre et concevoir

## Session 1 - Introduction aux API (90 min)

### 🔗 CONNEXION (15 min)

#### **Activité : "Trois choses que je sais + Une question"**
*En binômes (5 min + 5 min de partage + 5 min de synthèse)*

**Consigne :** 
- Notez **3 choses que vous savez déjà** sur les API
- Formulez **1 question** que vous vous posez sur les API

**Partage :** Chaque binôme partage une chose intéressante et une question au groupe.

*Le formateur note les questions au tableau pour y revenir dans la formation.*

### 💡 CONCEPTS (30 min)

#### **Activité : "Revue de code API"** (15 min)
*En groupes de 3-4 personnes*

**Support :** Plusieurs extraits de requêtes HTTP mélangés (bonnes et mauvaises pratiques)

```http
GET /api/v1/users/123
POST /api/getUser
DELETE /users/123/orders/456
GET /api/users?page=2&limit=20
POST /createNewUser
PUT /api/v2/users/123
```

**Consigne :** Identifiez ce qui vous semble correct ou incorrect dans ces exemples.

#### **Mini-conférence interactive** (15 min)
*Support visuel avec pauses questions*

**Contenu :**
- Définition API distante
- Rôle dans l'architecture moderne
- Exemples concrets d'usage

**Interaction :** Toutes les 5 minutes → "Donnez-moi un exemple d'API que vous utilisez au quotidien"

### 🔨 PRATIQUE CONCRÈTE (35 min)

#### **Activité : "Chasse sur le web + Analyse"** (20 min)
*En binômes*

**Mission :** 
1. Trouvez une API publique intéressante (GitHub, OpenWeather, etc.)
2. Analysez sa documentation
3. Identifiez : le rôle, les ressources, les endpoints principaux

#### **Partage et feedback croisé** (15 min)
Chaque binôme présente son API en 2 minutes : "Voici l'API X, elle sert à Y, ses principales ressources sont Z"

### 🎯 CONCLUSION/CONSOLIDATION (10 min)

#### **Activité : "Une phrase + Une idée à creuser"**
**Consigne :** 
- Complétez : "Une API distante, c'est..."
- Notez une chose que vous voulez approfondir

---

## Session 2 - Principes REST (90 min)

### 🔗 CONNEXION (10 min)

#### **Activité : "Mythe ou Vérité - REST Edition"**
*Vote à main levée*

**Affirmations à évaluer :**
- "REST, c'est juste du JSON sur HTTP" 
- "Une API REST doit obligatoirement retourner du JSON"
- "GET peut modifier des données"
- "Un seul verbe HTTP suffit pour toute une API"

### 💡 CONCEPTS (35 min)

#### **Slides interactives avec participation** (20 min)
*Support visuel + interactions*

**Séquence :**
1. Les 6 contraintes REST (5 min) → **Pause :** "Selon vous, pourquoi 'sans état' ?"
2. Les verbes HTTP (5 min) → **Activité :** "Associez verbe et action" (cartes à distribuer)
3. Les codes de statut (5 min) → **Quiz rapide :** "Quel code pour chaque situation ?"
4. Structure en ressources (5 min) → **Challenge :** "Nommez ces endpoints correctement"

#### **Complète le tableau** (15 min)
*En groupes de 3*

**Support :** Tableau à compléter avec verbes HTTP, codes de statut et exemples

| Action | Verbe | Code succès | Code erreur | Exemple URL |
|--------|-------|-------------|-------------|-------------|
| Lire tous les utilisateurs | ? | ? | ? | ? |
| Créer un utilisateur | ? | ? | ? | ? |
| Modifier un utilisateur | ? | ? | ? | ? |

### 🔨 PRATIQUE CONCRÈTE (35 min)

#### **Live Coding participatif** (35 min)
*Le formateur code, les apprenants dirigent*

**Objectif :** Concevoir ensemble l'API d'une bibliothèque simple

**Process :**
1. **Brainstorm ressources** (5 min) : "Quelles ressources dans une bibliothèque ?"
2. **Design des endpoints** (15 min) : Les apprenants proposent, on débat, on corrige ensemble
3. **Structure JSON** (15 min) : Conception collaborative des réponses

**Outils :** Tableau blanc ou outil collaboratif (Miro/Figma)

### 🎯 CONCLUSION/CONSOLIDATION (10 min)

#### **Mind Map collective**
Création collaborative d'une carte mentale "Principes REST" au tableau

---

## Session 3 - Conception pratique (2h00)

### 🔗 CONNEXION (10 min)

#### **Activité : "Classe ces éléments"**
*En binômes*

**Matériel :** Cartes avec différents styles d'URLs à trier du "plus RESTful" au "moins RESTful"

```
/api/users
/getUsers
/api/v1/users/123/orders
/user?action=delete&id=123
/api/users/search?name=john
```

### 💡 CONCEPTS (30 min)

#### **Lecture avec mission** (15 min)
*Travail individuel puis partage*

**Support :** Fiche "Conventions de nommage et bonnes pratiques"

**Mission :** Surlignez 3 règles que vous ne connaissiez pas, et préparez 1 question.

#### **Quiz interactif argumenté** (15 min)
*Kahoot ou vote simple*

**Questions sur :**
- Conventions de nommage
- Gestion des erreurs
- Versioning
- Pagination

*Après chaque réponse : 2-3 apprenants justifient leur choix*

### 🔨 PRATIQUE CONCRÈTE (70 min)

#### **Développement d'un mini-projet** (70 min)
*Groupes de 2-3 personnes*

**Projet :** Conception complète d'une API pour un système au choix :
- Gestion de tâches (todo-list)
- Catalogue de produits e-commerce  
- Système de réservation
- Blog avec commentaires

**Outils :** **Apicurio Studio** ou **Stoplight** pour la conception

**Livrables (à répartir sur 70 min) :**
1. **Identification des ressources** (15 min)
2. **Design des endpoints** avec Apicurio (25 min)
3. **Structure des réponses JSON** (20 min)
4. **Gestion d'erreurs** (10 min)

**Process :**
- **15 min :** Brainstorm et choix du domaine
- **40 min :** Conception dans l'outil
- **15 min :** Préparation de la présentation

### 🎯 CONCLUSION/CONSOLIDATION (10 min)

#### **Présentation express** (10 min)
Chaque groupe présente son API en 2 minutes maximum avec l'outil de conception.

---

# 🗓️ JOUR 2 : Documenter et approfondir

## Session 4 - Documentation OpenAPI (2h00)

### 🔗 CONNEXION (15 min)

#### **Activité : "Choisissez seulement les bonnes réponses"**
*Travail individuel puis débat*

**Question :** "Parmi ces éléments, lesquels sont essentiels dans une bonne documentation d'API ?"

- [ ] Exemples de requêtes
- [ ] Couleurs de l'interface
- [ ] Codes d'erreur possibles
- [ ] CV du développeur
- [ ] Format des données d'entrée
- [ ] Historique des versions
- [ ] Tutoriel "Hello World"

### 💡 CONCEPTS (25 min)

#### **Vidéo courte + réflexion guidée** (15 min)

**Support :** Vidéo 5 min sur l'importance de la documentation API

**Activité post-vidéo :** En binômes, notez :
- 2 raisons pour lesquelles une bonne doc est cruciale
- 1 exemple de mauvaise expérience avec une doc d'API

#### **Live demo** (10 min)
*Exploration interactive*

**Démonstration :** Navigation dans une spec OpenAPI (Swagger UI)
**Interaction :** "Que remarquez-vous ? Que trouvez-vous utile ?"

### 🔨 PRATIQUE CONCRÈTE (70 min)

#### **Atelier de documentation** (70 min)
*Mêmes groupes que la veille*

**Mission :** Documenter votre API d'hier avec OpenAPI

**Outils au choix :**
- **Stoplight Studio** (recommandé pour débutants)
- **Apicurio** (si familier avec YAML)
- **Swagger Editor** online

**Programme :**
1. **Prise en main de l'outil** (15 min)
2. **Documentation de base** (info, servers, paths) (25 min)
3. **Schémas et modèles de données** (20 min)
4. **Enrichissement** (exemples, descriptions) (10 min)

**Coaching :** Le formateur circule, aide, débloquer les groupes

### 🎯 CONCLUSION/CONSOLIDATION (10 min)

#### **Showcase** (10 min)
Chaque groupe montre sa documentation générée (Swagger UI), 2 min par groupe.

---

## Session 5 - Bonnes pratiques avancées (90 min)

### 🔗 CONNEXION (10 min)

#### **Activité : "Explique un concept vu précédemment"**
*En binômes changeants*

**Consigne :** Expliquez à votre partenaire (qui n'était pas dans votre groupe) :
- Ce que vous avez conçu hier
- Un principe REST qui vous a marqué

### 💡 CONCEPTS (30 min)

#### **Cartes à trier** (15 min)
*Groupes de 3-4*

**Matériel :** Cartes avec bonnes pratiques à classer par catégorie :
- Sécurité (authentification JWT, HTTPS, validation...)
- Performance (pagination, cache, compression...)
- Maintenabilité (versioning, codes d'erreur, logs...)

#### **Slides interactives** (15 min)
*Apport théorique avec pauses*

**Séquences courtes :**
- Sécurité (5 min) → **Question :** "Que risque-t-on sans HTTPS ?"
- Performance (5 min) → **Activité :** "Quand utiliseriez-vous la pagination ?"
- Versioning (5 min) → **Débat express :** "URL vs Header pour la version ?"

### 🔨 PRATIQUE CONCRÈTE (40 min)

#### **Atelier d'amélioration** (40 min)
*Mêmes groupes, travail sur leur API*

**Missions au choix (chaque groupe choisit 2-3 sujets) :**

1. **Sécurité** (15 min) : Ajoutez l'authentification à votre spec OpenAPI
2. **Gestion d'erreurs** (15 min) : Enrichissez avec tous les codes d'erreur possibles
3. **Performance** (15 min) : Implémentez la pagination sur une collection
4. **Versioning** (10 min) : Ajoutez une stratégie de versioning
5. **Tests** (15 min) : Écrivez des cas de test pour vos endpoints critiques

**Outil :** Continue avec Stoplight/Apicurio + documentation collaborative

### 🎯 CONCLUSION/CONSOLIDATION (10 min)

#### **1 chose apprise + 1 chose à approfondir**
- Chacun note individuellement puis partage avec son voisin
- Tour de table express : "Ma plus grande découverte aujourd'hui..."

---

## Session 6 - Écosystème et alternatives (90 min)

### 🔗 CONNEXION (15 min)

#### **Activité : "Trois faits et une question"**
*Réflexion individuelle puis partage*

**Consigne :** Notez 3 faits que vous connaissez sur GraphQL ou gRPC, et 1 question que vous vous posez.

*Si peu de connaissances préalables → adapter en "Qu'avez-vous entendu dire sur ces technologies ?"*

### 💡 CONCEPTS (30 min)

#### **Challenge minute** (10 min)
*En binômes*

**Défi :** "Vous avez 10 minutes pour faire une recherche express et présenter GraphQL OU gRPC en 2 minutes"
- Qu'est-ce que c'est ?
- 1 avantage principal
- 1 inconvénient
- 1 cas d'usage typique

#### **Présentation croisée** (20 min)
- 4 binômes présentent GraphQL (2 min chacun)
- 4 binômes présentent gRPC (2 min chacun)
- Questions et compléments du formateur (10 min)

### 🔨 PRATIQUE CONCRÈTE (35 min)

#### **Étude de cas comparative** (35 min)
*Groupes de 4-5 personnes*

**Cas :** "Vous devez choisir le style d'API pour ces 3 projets"

**Projets :**
1. **API publique** pour développeurs tiers (météo, cartes...)
2. **App mobile** avec besoins de données complexes et variables
3. **Communication entre microservices** haute performance

**Matériel :** Tableau comparatif à compléter + critères de décision

**Process :**
- **15 min :** Analyse et discussions en groupe
- **20 min :** Préparation d'une recommandation argumentée par projet

#### **Débat mouvant** (optionnel si le temps le permet)
**Affirmation :** "REST est dépassé, GraphQL est l'avenir"
Les participants se positionnent physiquement et débattent.

### 🎯 CONCLUSION/CONSOLIDATION (10 min)

#### **Présentation des recommandations** (10 min)
Chaque groupe présente ses choix technologiques en 1-2 minutes par projet.

---

## 🎯 CONCLUSION GÉNÉRALE (30 min)

### **Mind Map collective finale** (15 min)
*Collaboration de tout le groupe*

Création d'une grande carte mentale récapitulative de la formation avec tous les concepts abordés.

### **Retour d'expérience** (10 min)

#### **Thermomètre d'apprentissage**
"Sur une échelle de 1 à 5, à quel point vous sentez-vous capable de :"
- Concevoir une API RESTful simple (/5)
- La documenter avec OpenAPI (/5)  
- Choisir entre REST/GraphQL/gRPC (/5)

### **Engagement et suites** (5 min)

#### **Question bonus à creuser**
"Choisissez un sujet à approfondir d'ici 1 mois et trouvez-vous un binôme de la formation pour en discuter"

**Sujets proposés :**
- Sécurité API avancée
- Tests d'API automatisés
- Performance et monitoring
- Migration REST vers GraphQL

---

## 📚 Ressources et supports

### Outils utilisés
- **Apicurio Studio** : https://www.apicur.io/studio/
- **Stoplight Studio** : https://stoplight.io/studio/
- **Swagger Editor** : https://editor.swagger.io/

### Matériel pédagogique
- Cartes bonnes pratiques plastifiées
- Tableaux comparatifs à compléter
- Post-its et marqueurs pour mind maps
- Accès wifi et ordinateurs

### Supports numériques
- Slides visuelles avec peu de texte
- Spécifications OpenAPI d'exemple
- Collection Postman/Insomnia prête
- Liens vers API publiques pour exploration

---

## ⏱️ Récapitulatif temporel

| Jour | Session | Durée | Focus principal |
|------|---------|--------|-----------------|
| **Jour 1** | Session 1 | 90 min | Introduction API |
| | Session 2 | 90 min | Principes REST |
| | Session 3 | 120 min | Conception pratique |
| **Jour 2** | Session 4 | 120 min | Documentation OpenAPI |
| | Session 5 | 90 min | Bonnes pratiques |
| | Session 6 | 90 min | Alternatives (GraphQL, gRPC) |
| | Conclusion | 30 min | Synthèse et suites |

**Total :** 2 jours (12h de formation)

---

## 🎯 Points clés de la pédagogie active appliquée

✅ **Alternance constante** : Jamais plus de 15 min sans activité
✅ **Apprendre en faisant** : Conception réelle avec outils pro
✅ **Collaboration** : Travail en binômes et petits groupes
✅ **Réflexivité** : Moments de synthèse et auto-évaluation
✅ **Mouvement** : Vote physique, présentations, circulation
✅ **Parole active** : Explications entre pairs, présentations
✅ **Variété** : Quiz, débats, conception, recherche, analyse
✅ **Productions concrètes** : API documentée réutilisable