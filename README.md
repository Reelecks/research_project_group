# API de Gestion des Projets de Recherche

Cette API Django REST permet la gestion des projets de recherche, des chercheurs et des publications avec des fonctionnalités CRUD complètes et une authentification par token JWT.

## Prérequis

- Python 3.x
- pip
- Virtualenv

## Installation

1. **Cloner le dépôt :**

   ```bash
   git clone https://your_repository_url.git
   cd your_repository_directory
```

Créer et activer un environnement virtuel :

```bash

python -m venv env
source env/bin/activate   # Sur Windows, utilisez `env\Scripts\activate`
```
Installer les dépendances :

```bash

pip install -r requirements.txt
```
Configurer les variables d'environnement :

Créez un fichier .env à la racine du projet et ajoutez les lignes suivantes :

```bash

SECRET_KEY=your_secret_key
DEBUG=True
```
Appliquer les migrations de la base de données :

```bash

python manage.py makemigrations
python manage.py migrate
```
Créer un superutilisateur :

```bash

python manage.py createsuperuser
```
Lancer le serveur de développement :

```bash

python manage.py runserver
```
Utilisation
Authentification
Obtenir un token JWT :

Envoyer une requête POST à http://127.0.0.1:8000/api/token/ avec les informations de votre superutilisateur (username et password).

```bash

http POST http://127.0.0.1:8000/api/token/ 
username=your_username password=your_password
```
Utiliser le token pour accéder aux endpoints protégés :

Ajoutez le token obtenu aux en-têtes de vos requêtes en utilisant le format : Authorization: Bearer your_token.

## Endpoints
### Chercheurs

GET /api/chercheurs/
POST /api/chercheurs/
GET /api/chercheurs/{id}/
PUT /api/chercheurs/{id}/
PATCH /api/chercheurs/{id}/
DELETE /api/chercheurs/{id}/

### Projets de Recherche

GET /api/projets/
POST /api/projets/
GET /api/projets/{id}/
PUT /api/projets/{id}/
PATCH /api/projets/{id}/
DELETE /api/projets/{id}/

### Publications

GET /api/publications/
POST /api/publications/
GET /api/publications/{id}/
PUT /api/publications/{id}/
PATCH /api/publications/{id}/
DELETE /api/publications/{id}/