# Projet: développement d'une application pour restaurant avec IONIC
###### # Cette API sera consommée par l'application app_restaurant

#### Télécharger le projet et installer les dépendances avec la commande suivante
```
> npm install
```

#### Les collections:
```
- Menu: c'est le menu du jour, contient un composant (collection de plats).

- Plats
    Les attributs sont: nom, prix, description.

- Users : les utilisateurs.
    Les attributs de cette collection sont: nom, prenom, adresse, telephone, username, email, password.

- Commandes
    Cette collection contient deux collections que sont: Users, Plats
```

#### Les roles
###### Nous avons 3 types de rôle: Admin, Authenticated, Public
###### Créer ces rôles dans strapi s'ils ne sont pas déja créés.

##### Cliquez sur 'Roles & Permissions' dans le menu à gauche et autoriser les actions suivantes:

* Rôle <b>Public</b>: correspond aux utilisateurs non inscrits.
    - Dans <b>application</b>:
        - autoriser ```find``` dans les collections Menu et Plats
    - Dans <b>users-permissions</b>:
        - autoriser ```connect``` et ```register``` dans la collection Auth
        - autoriser ```init``` dans la collection Userpermissions
        
* Rôle <b>Authenticated</b>: correspond aux utilisateurs disposant un compte dans l'application.
  - Dans <b>application</b>:
    - autoriser ```find``` dans la collection Menu
    - autoriser ```create```, ```delete```, ```find```, ```findone``` et ```update``` dans la collection Commandes
  - Dans <b>Upload</b>:
    - autoriser ```upload``` sur la collection upload
  - Dans <b>users-permissions</b>:
    - autoriser ```connect``` et ```register``` dans la collection Auth
    - autoriser ```findone```, ```me``` et ```update``` dans la collectin User
    - autoriser ```init``` dans la collection Userpermissions
    
* Rôle <b>Admin</b>:
    - Dans <b>application</b>:
        - autoriser ```create```, ```delete```, ```find```, ```findone``` et ```update``` dans les collections Menu et Plats
        - autoriser ```find``` et ```delete``` dans la collection Commandes
    - Dans <b>Upload</b>:
        - autoriser ```upload``` dans la collection Upload
    - Dans <b>users-permissions</b>:
        - autoriser ```connect``` dans la collection Auth
        - autoriser ```findone```, ```me``` et ```update``` sur la collection User
        - autoriser ```init``` dans la collection Userpermissions


##### Lancer le serveur avec la commande 
```
> npx strapi start
```
