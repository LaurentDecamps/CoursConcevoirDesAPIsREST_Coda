# Supports pédagogiques et corrigés - Formation API RESTful

## 📋 JOUR 1 - Session 1 : Introduction aux API

### 🔗 Support Connexion : "Trois choses + Une question"

#### **Fiche apprenant (à distribuer)**
```
NOM : ________________    BINÔME : ________________

🧠 TROIS CHOSES QUE JE SAIS SUR LES API :
1. ________________________________________________
2. ________________________________________________  
3. ________________________________________________

❓ UNE QUESTION QUE JE ME POSE :
___________________________________________________
___________________________________________________
```

#### **Réponses attendues (pour le formateur)**

**Connaissances typiques :**
- Les API permettent aux applications de communiquer
- JSON est un format d'échange courant
- Il faut une clé API pour certains services
- Les API REST utilisent HTTP
- On peut récupérer des données météo via API
- Les réseaux sociaux ont des API

**Questions fréquentes :**
- Comment sécuriser une API ?
- Quelle est la différence entre REST et SOAP ?
- Comment tester une API ?
- Que signifie RESTful exactement ?
- Comment gérer les erreurs ?

---

### 💡 Support Concepts : "Revue de code API"

#### **Cartes à distribuer (format A5, plastifiées)**

```
CARTE 1 : ✅ CORRECT
GET /api/v1/users/123
→ Récupère l'utilisateur 123

CARTE 2 : ❌ INCORRECT  
POST /api/getUser
→ Utilise un verbe dans l'URL + mauvais verbe HTTP

CARTE 3 : ❌ INCORRECT
DELETE /users/123/orders/456  
→ Supprime une commande, mais la hiérarchie peut être confuse

CARTE 4 : ✅ CORRECT
GET /api/users?page=2&limit=20
→ Pagination correcte avec query parameters

CARTE 5 : ❌ INCORRECT
POST /createNewUser
→ Verbe dans l'URL, redondant avec POST

CARTE 6 : ✅ CORRECT  
PUT /api/v2/users/123
→ Mise à jour complète d'un utilisateur
```

#### **Grille de correction**

| URL | Statut | Problème | Correction |
|-----|--------|----------|------------|
| `GET /api/v1/users/123` | ✅ Correct | - | - |
| `POST /api/getUser` | ❌ Incorrect | Verbe dans URL + mauvais verbe | `GET /api/users/{id}` |
| `DELETE /users/123/orders/456` | ⚠️ Discutable | Hiérarchie complexe | `DELETE /api/orders/456` |
| `GET /api/users?page=2&limit=20` | ✅ Correct | - | - |
| `POST /createNewUser` | ❌ Incorrect | Verbe dans URL | `POST /api/users` |
| `PUT /api/v2/users/123` | ✅ Correct | - | - |

---

### 🔨 Support Pratique : "Chasse sur le web"

#### **Fiche mission (à distribuer)**

```
🎯 MISSION : ANALYSE D'API PUBLIQUE

Binôme : ________________

1. CHOIX DE L'API
Sélectionnez une API parmi :
□ GitHub API (https://docs.github.com/en/rest)
□ OpenWeatherMap (https://openweathermap.org/api)  
□ JSONPlaceholder (https://jsonplaceholder.typicode.com/)
□ Star Wars API (https://swapi.dev/)
□ Autre : _______________________

2. ANALYSE (15 minutes)
API choisie : _________________________
URL de base : _________________________

🔍 À quoi sert cette API ?
_________________________________________

🗂️ Quelles sont les principales ressources ?
1. ________________________________
2. ________________________________  
3. ________________________________

📍 Donnez 3 exemples d'endpoints :
1. ________________________________
2. ________________________________
3. ________________________________

3. PRÉPARATION PRÉSENTATION (5 minutes)
Préparez une présentation de 2 minutes maximum.
```

#### **Exemples de réponses attendues**

**GitHub API :**
- **Rôle :** Gérer repositories, utilisateurs, issues, pull requests
- **Ressources :** users, repos, issues, pulls, commits
- **Endpoints :** 
  - `GET /users/{username}`
  - `GET /repos/{owner}/{repo}`
  - `GET /repos/{owner}/{repo}/issues`

**OpenWeatherMap :**
- **Rôle :** Fournir des données météorologiques
- **Ressources :** weather, forecast, stations
- **Endpoints :**
  - `GET /weather?q={city}`
  - `GET /forecast?lat={lat}&lon={lon}`
  - `GET /stations`

---

## 📋 JOUR 1 - Session 2 : Principes REST

### 🔗 Support Connexion : "Mythe ou Vérité"

#### **Affirmations à projeter**

```
🤔 MYTHE OU VÉRITÉ ?

1. "REST, c'est juste du JSON sur HTTP"
   □ MYTHE    □ VÉRITÉ

2. "Une API REST doit obligatoirement retourner du JSON"  
   □ MYTHE    □ VÉRITÉ

3. "GET peut modifier des données"
   □ MYTHE    □ VÉRITÉ

4. "Un seul verbe HTTP suffit pour toute une API"
   □ MYTHE    □ VÉRITÉ

5. "REST est plus rapide que GraphQL"
   □ MYTHE    □ VÉRITÉ
```

#### **Corrigé avec explications**

1. **MYTHE** - REST est un style architectural, pas limité à JSON/HTTP
2. **MYTHE** - REST peut utiliser XML, HTML, ou autres formats
3. **MYTHE** - GET doit être safe (lecture seule)
4. **MYTHE** - Les verbes HTTP ont des sémantiques différentes
5. **MYTHE** - Dépend du contexte et de l'implémentation

---

### 💡 Support Concepts : "Complète le tableau"

#### **Tableau à compléter (format A3)**

```
CONCEPTION D'API RESTful - TABLEAU À COMPLÉTER

| Action | Verbe HTTP | Code succès | Code erreur | Exemple URL |
|--------|------------|-------------|-------------|-------------|
| Lire tous les utilisateurs | ???? | ??? | ??? | ???????????????? |
| Lire un utilisateur | ???? | ??? | ??? | ???????????????? |
| Créer un utilisateur | ???? | ??? | ??? | ???????????????? |
| Modifier un utilisateur (complet) | ???? | ??? | ??? | ???????????????? |
| Modifier un utilisateur (partiel) | ???? | ??? | ??? | ???????????????? |
| Supprimer un utilisateur | ???? | ??? | ??? | ???????????????? |
| Lister les commandes d'un utilisateur | ???? | ??? | ??? | ???????????????? |
```

#### **Corrigé complet**

| Action | Verbe HTTP | Code succès | Code erreur | Exemple URL |
|--------|------------|-------------|-------------|-------------|
| Lire tous les utilisateurs | GET | 200 | 404, 500 | `/api/users` |
| Lire un utilisateur | GET | 200 | 404, 500 | `/api/users/123` |
| Créer un utilisateur | POST | 201 | 400, 409, 500 | `/api/users` |
| Modifier un utilisateur (complet) | PUT | 200, 204 | 400, 404, 500 | `/api/users/123` |
| Modifier un utilisateur (partiel) | PATCH | 200, 204 | 400, 404, 500 | `/api/users/123` |
| Supprimer un utilisateur | DELETE | 200, 204 | 404, 500 | `/api/users/123` |
| Lister les commandes d'un utilisateur | GET | 200 | 404, 500 | `/api/users/123/orders` |

---

### 🔨 Support Pratique : "Live Coding - API Bibliothèque"

#### **Canevas de conception (tableau blanc/Miro)**

```
🏛️ API BIBLIOTHÈQUE - CONCEPTION COLLABORATIVE

1. BRAINSTORM RESSOURCES (5 min)
Quelles ressources dans une bibliothèque ?
- 📚 ________________
- 👤 ________________  
- 🏷️ ________________
- 📝 ________________

2. DESIGN DES ENDPOINTS (15 min)
Base URL : https://api.bibliotheque.fr/v1

📚 LIVRES :
- Lister tous : ________________
- Livre spécifique : ________________
- Créer : ________________
- Modifier : ________________
- Supprimer : ________________

👤 AUTEURS :
- Lister tous : ________________
- Auteur spécifique : ________________
- Livres d'un auteur : ________________

🏷️ CATÉGORIES :
- Lister toutes : ________________
- Livres d'une catégorie : ________________

3. STRUCTURE JSON (15 min)
```

#### **Solution complète**

```json
{
  "api_base": "https://api.bibliotheque.fr/v1",
  
  "ressources_identifiees": [
    "livres", "auteurs", "categories", "emprunts", "utilisateurs"
  ],
  
  "endpoints": {
    "livres": {
      "GET /livres": "Liste tous les livres",
      "GET /livres/{id}": "Détails d'un livre",
      "POST /livres": "Créer un nouveau livre",
      "PUT /livres/{id}": "Modifier complètement un livre",
      "PATCH /livres/{id}": "Modifier partiellement un livre",  
      "DELETE /livres/{id}": "Supprimer un livre"
    },
    "auteurs": {
      "GET /auteurs": "Liste tous les auteurs",
      "GET /auteurs/{id}": "Détails d'un auteur",
      "GET /auteurs/{id}/livres": "Livres d'un auteur"
    },
    "categories": {
      "GET /categories": "Liste toutes les catégories",
      "GET /categories/{id}/livres": "Livres d'une catégorie"
    }
  },
  
  "structure_livre": {
    "id": 123,
    "titre": "Le Petit Prince",
    "auteur": {
      "id": 456,
      "nom": "Saint-Exupéry",
      "prenom": "Antoine de"
    },
    "isbn": "978-2-07-040618-8",
    "pages": 96,
    "categories": ["jeunesse", "classique"],
    "disponible": true,
    "date_publication": "1943-04-06",
    "created_at": "2024-01-15T10:30:00Z",
    "updated_at": "2024-01-20T14:45:00Z"
  }
}
```

---

## 📋 JOUR 1 - Session 3 : Conception pratique

### 🔗 Support Connexion : "Classe ces éléments"

#### **Cartes URLs à trier (format cartes)**

```
CARTE A: /api/users
CARTE B: /getUsers  
CARTE C: /api/v1/users/123/orders
CARTE D: /user?action=delete&id=123
CARTE E: /api/users/search?name=john
CARTE F: /users/123/orders/456/items
CARTE G: /createUser
CARTE H: /api/v2/users/{userId}/orders
```

#### **Classement du plus au moins RESTful**

```
🥇 TRÈS RESTful
- /api/users
- /api/v1/users/123/orders  
- /users/123/orders/456/items
- /api/v2/users/{userId}/orders

🥈 ACCEPTABLE  
- /api/users/search?name=john (recherche avec query param)

🥉 PEU RESTful
- /getUsers (verbe dans l'URL)
- /createUser (verbe dans l'URL)

💥 PAS RESTful DU TOUT
- /user?action=delete&id=123 (action en query param)
```

---

### 💡 Support Concepts : "Fiche conventions"

#### **Fiche de lecture (format A4)**

```
📋 CONVENTIONS DE NOMMAGE ET BONNES PRATIQUES

🎯 RÈGLES D'OR POUR LES URLs

✅ UTILISEZ DES NOMS, PAS DES VERBES
Correct : GET /users/123
Incorrect : GET /getUser/123

✅ PLURIEL POUR LES COLLECTIONS  
Correct : GET /users
Incorrect : GET /user

✅ HIÉRARCHIE LOGIQUE
Correct : GET /users/123/orders/456
Signification : Commande 456 de l'utilisateur 123

✅ MINUSCULES AVEC TIRETS
Correct : /order-items
Incorrect : /OrderItems ou /order_items

✅ COHÉRENCE DANS TOUTE L'API
Si vous utilisez "users", n'utilisez pas "user" ailleurs

🔧 GESTION DES ERREURS STANDARDISÉE

Structure de réponse d'erreur :
{
  "error": {
    "code": "VALIDATION_ERROR",
    "message": "Description lisible par l'humain",
    "details": [...],
    "timestamp": "2024-01-20T15:30:00Z",
    "path": "/api/users/123"
  }
}

Codes HTTP principaux :
- 400 : Bad Request (données invalides)
- 401 : Unauthorized (authentification manquante)
- 403 : Forbidden (pas les droits)
- 404 : Not Found (ressource introuvable)
- 409 : Conflict (conflit, ex: email déjà existant)
- 422 : Unprocessable Entity (données valides mais logiquement incorrectes)
- 500 : Internal Server Error (erreur serveur)

📄 PAGINATION

Query parameters standards :
- page : numéro de page (commence à 1)
- per_page ou limit : nombre d'éléments par page
- sort : champ de tri
- order : direction (asc/desc)

Exemple : GET /users?page=2&per_page=20&sort=name&order=asc

🔄 VERSIONING

Stratégies possibles :
1. Dans l'URL : /api/v1/users
2. Dans le header : Accept-Version: v1
3. Query parameter : /api/users?version=1

💡 FILTRAGE ET RECHERCHE

- Filtrage simple : /users?status=active
- Recherche : /users?search=john
- Filtres complexes : /users?created_at=gte:2024-01-01
```

---

### 🔨 Support Pratique : "Projets de conception"

#### **Fiche projet - Option 1 : Todo List**

```
📝 PROJET : API GESTION DE TÂCHES

🎯 CONTEXTE
Vous devez concevoir l'API d'une application de gestion de tâches (comme Todoist).

👤 UTILISATEURS CIBLES  
- Particuliers organisant leurs tâches personnelles
- Équipes collaborant sur des projets

🏗️ FONCTIONNALITÉS ATTENDUES
□ Gestion des utilisateurs (inscription, profil)
□ Création/modification/suppression de tâches
□ Organisation en projets/listes
□ Attribution de priorités et échéances
□ Statuts des tâches (à faire, en cours, terminée)
□ Partage de listes entre utilisateurs
□ Recherche et filtrage

🎯 LIVRABLES
1. Identifiez les ressources principales (15 min)
2. Concevez les endpoints avec Apicurio (25 min)
3. Définissez la structure JSON des réponses (20 min)
4. Gérez les cas d'erreur principaux (10 min)

💡 QUESTIONS À SE POSER
- Quelles sont les entités métier ?
- Comment gérer la hiérarchie tâches/projets ?
- Quels filtres proposer ?
- Comment modéliser les permissions ?
```

#### **Solution type - Todo List**

```json
{
  "ressources": ["users", "projects", "tasks", "collaborators"],
  
  "endpoints": {
    "users": {
      "POST /auth/register": "Inscription",
      "POST /auth/login": "Connexion", 
      "GET /users/me": "Profil utilisateur",
      "PATCH /users/me": "Modifier profil"
    },
    "projects": {
      "GET /projects": "Mes projets",
      "POST /projects": "Créer un projet",
      "GET /projects/{id}": "Détails d'un projet",
      "PUT /projects/{id}": "Modifier projet",
      "DELETE /projects/{id}": "Supprimer projet",
      "GET /projects/{id}/tasks": "Tâches du projet",
      "POST /projects/{id}/collaborators": "Ajouter un collaborateur"
    },
    "tasks": {
      "GET /tasks": "Mes tâches (tous projets)",
      "POST /tasks": "Créer une tâche", 
      "GET /tasks/{id}": "Détails d'une tâche",
      "PATCH /tasks/{id}": "Modifier tâche",
      "DELETE /tasks/{id}": "Supprimer tâche"
    }
  },
  
  "structure_task": {
    "id": 123,
    "title": "Finir la présentation",
    "description": "Ajouter les graphiques et relire",
    "status": "todo", 
    "priority": "high",
    "due_date": "2024-02-15T18:00:00Z",
    "project": {
      "id": 456,
      "name": "Projet Client ABC"
    },
    "assignee": {
      "id": 789, 
      "name": "Marie Dupont"
    },
    "created_at": "2024-01-15T10:30:00Z",
    "updated_at": "2024-01-20T14:45:00Z"
  },
  
  "filtres_utiles": [
    "GET /tasks?status=todo",
    "GET /tasks?priority=high", 
    "GET /tasks?due_date=lte:2024-02-01",
    "GET /tasks?assignee=me",
    "GET /tasks?project_id=456"
  ]
}
```

---

## 📋 JOUR 2 - Session 4 : Documentation OpenAPI

### 🔗 Support Connexion : "Éléments essentiels documentation"

#### **Liste à cocher (projection)**

```
🤔 PARMI CES ÉLÉMENTS, LESQUELS SONT ESSENTIELS 
   DANS UNE BONNE DOCUMENTATION D'API ?

□ Exemples de requêtes
□ Couleurs de l'interface  
□ Codes d'erreur possibles
□ CV du développeur
□ Format des données d'entrée
□ Historique des versions
□ Tutoriel "Hello World"
□ Liste des endpoints disponibles
□ Schémas de données de réponse
□ Logo de l'entreprise
□ Exemples de réponses
□ Informations d'authentification
□ Limites de taux (rate limiting)
□ Numéro de téléphone du support
```

#### **Réponses correctes**

```
✅ ESSENTIELS :
□ Exemples de requêtes
□ Codes d'erreur possibles  
□ Format des données d'entrée
□ Tutoriel "Hello World"
□ Liste des endpoints disponibles
□ Schémas de données de réponse
□ Exemples de réponses
□ Informations d'authentification
□ Limites de taux (rate limiting)

❌ PAS ESSENTIELS :
□ Couleurs de l'interface
□ CV du développeur  
□ Historique des versions (nice to have)
□ Logo de l'entreprise
□ Numéro de téléphone du support
```

---

### 🔨 Support Pratique : "Template OpenAPI"

#### **Template de base OpenAPI (à fournir)**

```yaml
openapi: 3.0.3
info:
  title: Mon API
  description: Description de mon API
  version: 1.0.0
  contact:
    name: Équipe API
    email: api@monapp.com
    
servers:
  - url: https://api.monapp.com/v1
    description: Serveur de production
  - url: https://staging-api.monapp.com/v1  
    description: Serveur de test

paths:
  # À COMPLÉTER PAR LES APPRENANTS
  
components:
  schemas:
    # À COMPLÉTER PAR LES APPRENANTS
    
  securitySchemes:
    BearerAuth:
      type: http
      scheme: bearer
      bearerFormat: JWT
      
security:
  - BearerAuth: []
```

#### **Exemple complet pour référence formateur**

```yaml
openapi: 3.0.3
info:
  title: API Gestion de Tâches
  description: |
    API pour gérer des tâches et projets dans une application de productivité.
    
    ## Authentification
    Cette API utilise JWT Bearer tokens pour l'authentification.
    
    ## Limitation du taux
    - 1000 requêtes par heure par utilisateur authentifié
    - 100 requêtes par heure pour les utilisateurs non authentifiés
    
  version: 1.0.0
  contact:
    name: Équipe API TodoApp
    email: api@todoapp.com
    url: https://todoapp.com/support
    
servers:
  - url: https://api.todoapp.com/v1
    description: Serveur de production
  - url: https://staging-api.todoapp.com/v1
    description: Serveur de test

paths:
  /tasks:
    get:
      summary: Lister les tâches
      description: Récupère la liste des tâches de l'utilisateur connecté
      parameters:
        - name: status
          in: query
          description: Filtrer par statut
          required: false
          schema:
            type: string
            enum: [todo, in_progress, done]
        - name: project_id
          in: query
          description: Filtrer par projet
          required: false
          schema:
            type: integer
        - name: page
          in: query
          description: Numéro de page
          required: false
          schema:
            type: integer
            default: 1
            minimum: 1
      responses:
        '200':
          description: Liste des tâches récupérée avec succès
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/TasksResponse'
        '401':
          description: Non authentifié
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/Error'
                
    post:
      summary: Créer une tâche
      description: Crée une nouvelle tâche
      requestBody:
        required: true
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/CreateTask'
            examples:
              simple_task:
                summary: Tâche simple
                value:
                  title: "Réviser le cours d'API"
                  project_id: 123
              detailed_task:
                summary: Tâche détaillée
                value:
                  title: "Préparer la présentation client"
                  description: "Inclure les métriques de performance"
                  project_id: 123
                  priority: "high"
                  due_date: "2024-02-15T18:00:00Z"
      responses:
        '201':
          description: Tâche créée avec succès
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/Task'
        '400':
          description: Données invalides
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/Error'

  /tasks/{taskId}:
    get:
      summary: Récupérer une tâche
      parameters:
        - name: taskId
          in: path
          required: true
          description: ID de la tâche
          schema:
            type: integer
      responses:
        '200':
          description: Tâche récupérée avec succès
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/Task'
        '404':
          description: Tâche non trouvée

components:
  schemas:
    Task:
      type: object
      properties:
        id:
          type: integer
          example: 123
        title:
          type: string
          example: "Terminer le rapport mensuel"
        description:
          type: string
          example: "Ajouter les graphiques de performance"
          nullable: true
        status:
          type: string
          enum: [todo, in_progress, done]
          example: "todo"
        priority:
          type: string
          enum: [low, medium, high]
          example: "medium"
        due_date:
          type: string
          format: date-time
          example: "2024-02-15T18:00:00Z"
          nullable: true
        project:
          $ref: '#/components/schemas/ProjectSummary'
        created_at:
          type: string
          format: date-time
        updated_at:
          type: string
          format: date-time
          
    CreateTask:
      type: object
      required:
        - title
        - project_id
      properties:
        title:
          type: string
          minLength: 1
          maxLength: 200
          example: "Nouvelle tâche"
        description:
          type: string
          maxLength: 1000
          example: "Description détaillée de la tâche"
        project_id:
          type: integer
          example: 123
        priority:
          type: string
          enum: [low, medium, high]
          default: "medium"
        due_date:
          type: string
          format: date-time
          example: "2024-02-15T18:00:00Z"
          
    ProjectSummary:
      type: object
      properties:
        id:
          type: integer
        name:
          type: string
        
    TasksResponse:
      type: object
      properties:
        data:
          type: array
          items:
            $ref: '#/components/schemas/Task'
        meta:
          type: object
          properties:
            total:
              type: integer
            page:
              type: integer
            per_page:
              type: integer
            total_pages:
              type: integer
              
    Error:
      type: object
      properties:
        error:
          type: object
          properties:
            code:
              type: string
              example: "VALIDATION_ERROR"
            message:
              type: string
              example: "Les données fournies ne sont pas valides"
            details:
              type: array
              items:
                type: object
                properties:
                  field:
                    type: string
                  message:
                    type: string

  securitySchemes:
    BearerAuth:
      type: http
      scheme: bearer
      bearerFormat: JWT
      description: |
        Utilisez un token JWT Bearer obtenu via l'endpoint /auth/login
        
        Exemple: `Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...`

security:
  - BearerAuth: []
```

---

## 📋 JOUR 2 - Session 5 : Bonnes pratiques

### 🔗 Support Connexion : "Cartes bonnes pratiques"

#### **Jeu de cartes à classer (format cartes)**

```
CARTE SÉCURITÉ 1: Utiliser HTTPS uniquement
CARTE SÉCURITÉ 2: Authentification JWT
CARTE SÉCURITÉ 3: Validation des données d'entrée
CARTE SÉCURITÉ 4: Pas de données sensibles dans les URLs
CARTE SÉCURITÉ 5: Rate limiting par utilisateur

CARTE PERFORMANCE 1: Pagination des collections
CARTE PERFORMANCE 2: Compression GZIP
CARTE PERFORMANCE 3: Cache HTTP avec ETag
CARTE PERFORMANCE 4: Requêtes asynchrones
CARTE PERFORMANCE 5: CDN pour les ressources statiques

CARTE MAINTENABILITÉ 1: Versioning de l'API (/v1, /v2)
CARTE MAINTENABILITÉ 2: Codes d'erreur standardisés
CARTE MAINTENABILITÉ 3: Documentation OpenAPI à jour
CARTE MAINTENABILITÉ 4: Tests automatisés
CARTE MAINTENABILITÉ 5: Logs structurés
```

#### **Classification attendue**

```
🔒 SÉCURITÉ
- Utiliser HTTPS uniquement
- Authentification JWT
- Validation des données d'entrée  
- Pas de données sensibles dans les URLs
- Rate limiting par utilisateur

⚡ PERFORMANCE  
- Pagination des collections
- Compression GZIP
- Cache HTTP avec ETag
- Requêtes asynchrones
- CDN pour les ressources statiques

🔧 MAINTENABILITÉ
- Versioning de l'API (/v1, /v2)
- Codes d'erreur standardisés
- Documentation OpenAPI à jour
- Tests automatisés  
- Logs structurés
```

---

### 🔨 Support Pratique : "Missions d'amélioration"

#### **Fiche mission sécurité (15 min)**

```
🔒 MISSION SÉCURITÉ

Objectif : Ajouter l'authentification à votre API

✅ TÂCHES À RÉALISER :

1. SCHÉMA DE SÉCURITÉ (5 min)
   □ Ajoutez un securitySchemes dans components
   □ Choisissez : JWT Bearer, API Key, ou OAuth2
   □ Documentez comment obtenir le token

2. APPLICATION AUX ENDPOINTS (5 min)
   □ Appliquez la sécurité aux endpoints sensibles
   □ Laissez publics : documentation, health check
   □ Sécurisez : création, modification, suppression

3. GESTION DES ERREURS AUTH (5 min)
   □ Ajoutez les réponses 401 (non authentifié)
   □ Ajoutez les réponses 403 (accès refusé)
   □ Documentez le format des erreurs d'auth

💡 EXEMPLE DE SÉCURITÉ JWT :
```yaml
components:
  securitySchemes:
    BearerAuth:
      type: http
      scheme: bearer
      bearerFormat: JWT
      description: Token JWT obtenu via POST /auth/login

security:
  - BearerAuth: []
```
```

#### **Fiche mission performance (15 min)**

```
⚡ MISSION PERFORMANCE

Objectif : Optimiser votre API pour de gros volumes

✅ TÂCHES À RÉALISER :

1. PAGINATION (7 min)
   □ Ajoutez les paramètres : page, per_page, sort, order
   □ Définissez les limites (max 100 items/page)
   □ Enrichissez la réponse avec les métadonnées

2. FILTRAGE ET RECHERCHE (8 min)
   □ Ajoutez des query parameters de filtrage
   □ Implémentez une recherche textuelle (search=)
   □ Ajoutez des filtres par date/statut

💡 EXEMPLE DE PAGINATION :
```yaml
parameters:
  - name: page
    in: query
    schema:
      type: integer
      default: 1
      minimum: 1
  - name: per_page
    in: query
    schema:
      type: integer
      default: 20
      minimum: 1
      maximum: 100

# Dans la réponse :
meta:
  type: object
  properties:
    total: { type: integer }
    page: { type: integer }
    per_page: { type: integer }
    total_pages: { type: integer }
```
```

#### **Fiche mission versioning (10 min)**

```
🔄 MISSION VERSIONING

Objectif : Préparer l'évolution de votre API

✅ TÂCHES À RÉALISER :

1. STRATÉGIE DE VERSIONING (5 min)
   □ Choisissez : URL (/v1/), Header, ou Query param
   □ Mettez à jour la base URL dans servers
   □ Documentez la stratégie dans la description

2. GESTION DES CHANGEMENTS (5 min)
   □ Identifiez 2-3 évolutions possibles de votre API
   □ Classez-les : compatible vs breaking change
   □ Planifiez les versions futures

💡 EXEMPLES D'ÉVOLUTIONS :
- Ajout d'un champ optionnel → Compatible
- Suppression d'un champ → Breaking change  
- Nouveau format de date → Breaking change
- Nouvel endpoint → Compatible
```

#### **Fiche mission tests (15 min)**

```
🧪 MISSION TESTS

Objectif : Définir une stratégie de test pour votre API

✅ TÂCHES À RÉALISER :

1. CAS DE TEST CRITIQUES (8 min)
   □ Identifiez vos 5 endpoints les plus critiques
   □ Listez les cas de test pour chacun (succès + erreurs)
   □ Définissez les données de test nécessaires

2. SCÉNARIOS D'INTÉGRATION (7 min)  
   □ Créez 2-3 scénarios utilisateur complets
   □ Exemple : "Utilisateur crée un projet puis y ajoute des tâches"
   □ Identifiez les assertions importantes

💡 TEMPLATE CAS DE TEST :
Endpoint : GET /users/{id}
- ✅ Cas nominal : utilisateur existant → 200 + données
- ❌ Utilisateur inexistant → 404 + erreur
- ❌ ID invalide → 400 + erreur de validation  
- ❌ Non authentifié → 401 + erreur auth
```

---

## 📋 JOUR 2 - Session 6 : Alternatives (GraphQL, gRPC)

### 🔗 Support Connexion : "Connaissances alternatives"

#### **Fiche de réflexion individuelle**

```
🤔 QUE SAVEZ-VOUS SUR CES TECHNOLOGIES ?

📊 GRAPHQL
3 choses que je sais (ou que j'ai entendu dire) :
1. _____________________________________________
2. _____________________________________________  
3. _____________________________________________

1 question que je me pose :
_____________________________________________

⚡ gRPC  
3 choses que je sais (ou que j'ai entendu dire) :
1. _____________________________________________
2. _____________________________________________
3. _____________________________________________

1 question que je me pose :
_____________________________________________

🔄 AUTRES STYLES D'API
Connaissez-vous d'autres styles ? (SOAP, WebSocket, etc.)
_____________________________________________
```

---

### 💡 Support Concepts : "Challenge recherche express"

#### **Fiche mission recherche (10 min)**

```
🔍 CHALLENGE MINUTE : RECHERCHE EXPRESS

Binôme : ___________________
Technologie choisie : □ GraphQL  □ gRPC

🎯 MISSION (10 minutes chrono !)
Préparez une présentation de 2 minutes avec :

1. QU'EST-CE QUE C'EST ? (1 phrase simple)
   _________________________________________

2. 1 AVANTAGE PRINCIPAL
   _________________________________________

3. 1 INCONVÉNIENT  
   _________________________________________

4. 1 CAS D'USAGE TYPIQUE (exemple concret)
   _________________________________________

5. BONUS : 1 GRANDE ENTREPRISE QUI L'UTILISE
   _________________________________________

💡 RESSOURCES SUGGÉRÉES :
- Site officiel de la technologie
- Articles dev.to ou blog tech  
- Documentation GitHub
- Comparaisons REST vs X
```

#### **Réponses de référence pour le formateur**

**GraphQL :**
- **Définition :** Langage de requête qui permet au client de demander exactement les données dont il a besoin
- **Avantage :** Une seule requête pour récupérer des données complexes depuis plusieurs sources
- **Inconvénient :** Complexité du cache, courbe d'apprentissage
- **Cas d'usage :** Applications mobiles avec besoins de données variables, dashboards complexes
- **Entreprises :** Facebook (créateur), GitHub, Shopify, Netflix

**gRPC :**
- **Définition :** Framework RPC haute performance utilisant HTTP/2 et Protocol Buffers
- **Avantage :** Très performant, typage fort, support multi-langage
- **Inconvénient :** Moins accessible depuis le navigateur, complexité de mise en œuvre
- **Cas d'usage :** Communication entre microservices, systèmes distribués haute performance
- **Entreprises :** Google (créateur), Netflix, Uber, Square

---

### 🔨 Support Pratique : "Étude de cas comparative"

#### **Cahier des charges - 3 projets**

```
📋 ÉTUDE DE CAS : CHOISIR LE BON STYLE D'API

🎯 VOTRE MISSION
Analysez ces 3 projets et recommandez le meilleur style d'API pour chacun.
Justifiez vos choix avec des arguments techniques et métier.

---

📱 PROJET A : API PUBLIQUE MÉTÉO
CONTEXTE :
- Service météo public pour développeurs tiers
- 10 000+ développeurs utilisateurs  
- Données simples : température, humidité, prévisions
- Besoin de simplicité d'intégration
- Budget limité pour la maintenance
- Trafic : 1M requêtes/jour

CONTRAINTES :
- Documentation facile à comprendre
- Intégration rapide (5 min pour un Hello World)
- Compatible avec tous langages/plateformes
- Cache HTTP important (données changent peu)

VOTRE RECOMMANDATION : ________________
JUSTIFICATION :
_________________________________________
_________________________________________

---

📱 PROJET B : APP MOBILE SOCIALE  
CONTEXTE :
- Application mobile type Instagram/Facebook
- Interface complexe avec timeline, profils, messages
- Besoins de données très variables selon les écrans
- Optimisation réseau critique (4G/5G variable)
- Équipe de 20 développeurs front/back

CONTRAINTES :
- Minimiser le nombre d'appels réseau
- Récupérer seulement les données affichées
- Interface riche et interactive
- Évolutions fréquentes de l'UI

VOTRE RECOMMANDATION : ________________
JUSTIFICATION :
_________________________________________
_________________________________________

---

🏗️ PROJET C : MICROSERVICES BANCAIRES
CONTEXTE :
- Architecture microservices (50+ services)
- Communications internes haute fréquence
- Données sensibles (transactions financières)
- Performance critique (< 10ms de latence)
- Équipe experte en distributed systems

CONTRAINTES :
- Sécurité maximale
- Performance très élevée
- Typage strict des données
- Monitoring et observabilité avancés
- Tolérance de panne

VOTRE RECOMMANDATION : ________________  
JUSTIFICATION :
_________________________________________
_________________________________________
```

#### **Grille d'analyse (à fournir aux groupes)**

```
📊 GRILLE D'ANALYSE COMPARATIVE

| Critère | REST | GraphQL | gRPC | Poids |
|---------|------|---------|------|-------|
| Simplicité d'implémentation | 🟢 Très simple | 🟡 Moyen | 🔴 Complexe | /5 |
| Performance | 🟡 Correcte | 🟡 Variable | 🟢 Excellente | /5 |
| Flexibilité côté client | 🟡 Limitée | 🟢 Très flexible | 🔴 Rigide | /5 |
| Cache HTTP | 🟢 Excellent | 🔴 Difficile | 🔴 Non applicable | /5 |
| Écosystème et outils | 🟢 Mature | 🟡 En croissance | 🟡 Spécialisé | /5 |
| Courbe d'apprentissage | 🟢 Facile | 🟡 Moyenne | 🔴 Difficile | /5 |
| Support multi-plateforme | 🟢 Universel | 🟢 Très bon | 🟡 Bon | /5 |

🟢 Excellent  🟡 Correct  🔴 Faible

CALCULEZ LE SCORE POUR CHAQUE PROJET :
Projet A (API Météo) : REST _/35, GraphQL _/35, gRPC _/35
Projet B (App Mobile) : REST _/35, GraphQL _/35, gRPC _/35  
Projet C (Microservices) : REST _/35, GraphQL _/35, gRPC _/35
```

#### **Solutions recommandées**

```
✅ SOLUTIONS RECOMMANDÉES

📱 PROJET A (API MÉTÉO) → REST
JUSTIFICATION :
- Simplicité d'intégration cruciale pour adoption massive
- Données simples ne nécessitent pas la flexibilité GraphQL
- Cache HTTP très efficace pour données météo
- Écosystème mature, documentation universelle
- Coût de développement et maintenance minimal

📱 PROJET B (APP MOBILE) → GraphQL  
JUSTIFICATION :
- Une requête pour récupérer timeline + profil + notifications
- Client peut demander uniquement les champs affichés
- Économie de bande passante sur mobile
- Évolution UI sans modifier l'API
- Équipe assez grande pour gérer la complexité

🏗️ PROJET C (MICROSERVICES) → gRPC
JUSTIFICATION :
- Performance maximale pour communications internes fréquentes
- Typage strict réduit les erreurs en production
- HTTP/2 multiplexing optimal pour microservices
- Sérialisation binaire plus efficace
- Équipe experte peut gérer la complexité
```

---

## 📋 CONCLUSION GÉNÉRALE

### 🎯 Support Consolidation : "Mind Map collective"

#### **Canevas Mind Map (tableau blanc/Miro)**

```
                    🌐 API RESTful
                         |
        ┌────────────────┼────────────────┐
        │                │                │
    PRINCIPES        CONCEPTION      DOCUMENTATION
        │                │                │
   ┌────┼────┐      ┌────┼────┐      ┌────┼────┐
   │    │    │      │    │    │      │    │    │
  6      │  Codes   │  Naming │    OpenAPI │  Exemples
Contraintes │ HTTP  │ Conventions │        │
   │    Verbes      │         │         │
Sans état  HTTP   Ressources Endpoints  Schémas
   │                │         │         │
Client/   GET      Pluriel   URLs      Swagger UI
Serveur   POST     │       RESTful     │
   │      PUT      Hiérarchie         Auto-génération
Cache   DELETE    │                   │
   │    PATCH     /users/123/orders   Tests
Interface         │                   
uniforme         Bonnes pratiques     
   │              │                   
HATEOAS      ┌────┼────┐              
             │    │    │              
         Sécurité Perf Maintenance    
             │    │    │              
           HTTPS Pagination Versioning
           JWT   Cache    Erreurs     
           Validation    Logs         
```

### 🎯 Support final : "Thermomètre d'apprentissage"

#### **Fiche d'auto-évaluation finale**

```
📊 THERMOMÈTRE D'APPRENTISSAGE

NOM : _________________________   DATE : _____________

🎯 À QUEL POINT VOUS SENTEZ-VOUS CAPABLE DE :

1. CONCEVOIR UNE API RESTful SIMPLE
   1 -------- 2 -------- 3 -------- 4 -------- 5
   Pas du tout                             Très confiant

2. LA DOCUMENTER AVEC OpenAPI
   1 -------- 2 -------- 3 -------- 4 -------- 5
   Pas du tout                             Très confiant

3. CHOISIR ENTRE REST/GraphQL/gRPC
   1 -------- 2 -------- 3 -------- 4 -------- 5
   Pas du tout                             Très confiant

4. APPLIQUER LES BONNES PRATIQUES DE SÉCURITÉ
   1 -------- 2 -------- 3 -------- 4 -------- 5
   Pas du tout                             Très confiant

5. GÉRER LES ERREURS ET LA PERFORMANCE
   1 -------- 2 -------- 3 -------- 4 -------- 5
   Pas du tout                             Très confiant

💡 MA PLUS GRANDE DÉCOUVERTE :
_________________________________________________

🎯 CE QUE JE VEUX APPROFONDIR D'ICI 1 MOIS :
_________________________________________________

👥 BINÔME POUR ÉCHANGER SUR CE SUJET :
_________________________________________________
```

### 🎯 Support : "Question bonus et engagement"

#### **Fiche de projection (derniers 5 min)**

```
🚀 QUESTIONS BONUS À CREUSER

Choisissez UN sujet à approfondir et trouvez-vous un binôme de formation :

□ SÉCURITÉ API AVANCÉE
  - OAuth 2.0 vs JWT : quand utiliser quoi ?
  - Comment sécuriser une API publique à grande échelle ?
  - Rate limiting avancé et protection DDoS

□ TESTS D'API AUTOMATISÉS  
  - Tests de contrat avec Pact
  - Tests de charge avec K6 ou Artillery  
  - Stratégie de tests en pyramide pour API

□ PERFORMANCE ET MONITORING
  - Métriques critiques à surveiller
  - Optimisation des requêtes N+1
  - CDN et stratégies de cache avancées

□ MIGRATION REST VERS GraphQL
  - Stratégie de migration progressive
  - Cohabitation REST/GraphQL  
  - Retour d'expérience d'entreprises

□ AUTRE SUJET :
  _________________________________

MON CHOIX : _________________________

MON BINÔME : _______________________
EMAIL/CONTACT : ___________________

📅 NOUS PRÉVOYONS D'ÉCHANGER :
□ Dans 2 semaines  □ Dans 1 mois  □ Autre : ________
```

---

## 📁 RÉCAPITULATIF DES SUPPORTS PHYSIQUES À PRÉPARER

### 🖨️ À imprimer/plastifier

1. **Cartes révision de code** (Session 1) - Format A6, plastifiées
2. **Cartes URLs à classer** (Session 3) - Format cartes, plastifiées  
3. **Cartes bonnes pratiques** (Session 5) - Format A6, plastifiées
4. **Fiches projet de conception** (Session 3) - Format A4
5. **Tableau REST à compléter** (Session 2) - Format A3
6. **Grille comparative REST/GraphQL/gRPC** - Format A4
7. **Fiches auto-évaluation finale** - Format A4

### 💻 À préparer numériquement

1. **Template OpenAPI de base** - Fichier YAML
2. **Exemples d'API publiques** - Liste avec URLs
3. **Slides visuelles** (peu de texte, beaucoup d'images)
4. **Collection Postman/Insomnia** - Pour les démos
5. **Accès aux outils** (Apicurio, Stoplight)

### 🎨 Matériel général

- Post-its de couleurs
- Marqueurs pour tableaux  
- Tableau blanc/paperboard
- Ordinateurs avec accès internet
- Projecteur/écran
- Chronomètre visible

Cette approche garantit des sessions interactives où les apprenants manipulent constamment, questionnent, et produisent, conformément aux principes de pédagogie active de Sharon Bowman.