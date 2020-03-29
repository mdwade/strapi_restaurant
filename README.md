# Projet: développement d'une application pour restaurant avec IONIC
###### # Cette API sera consommée par l'application app_restaurant

## Etudiant
```
- Nom:      Wade
- Prénom:   Mouhamed Diop
- Classe:   M2GLSI
```

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
##### Nous avons 3 types de rôle: Admin, Authenticated, Public
##### Créer ces rôles dans strapi s'ils ne sont pas déja crées.

##### Cliquez sur 'Roles & Permissions' dans le menu à gauche et autoriser les actions suivantes:

* <b>Public</b>: correspond aux utilisateurs non inscrits.  
    - Dans <b>application</b>:
        -  ```find``` dans les collections Menu et Plats
    - Dans <b>users-permissions</b>:
        -  ```connect``` et ```register``` dans la collection Auth
        - ```init``` dans la collection Userpermissions
        
* <b>Authenticated</b>: correspond aux utilisateurs disposant un compte dans l'application.
  - Dans <b>application</b>
    - ```find``` dans la collection Menu
    - ```create```, ```delete```, ```find```, ```findone``` et ```update``` dans la collection Commandes
  - Dans <b>Upload</b>
    - ```upload``` sur la collection upload
  - Dans <b>users-permissions</b>:
    - ```connect``` et ```register``` dans la collection Auth
    - ```findone```, ```me``` et ```update``` dans la collectin User
    - ```init``` dans la collection Userpermissions
    
* <b>Admin</b>:
    - Dans <b>application</b>      
        - ```create```, ```delete```, ```find```, ```findone``` et ```update``` dans les collections Menu et Plats
        - ```find``` et ```delete``` dans la collection Commandes
    - Dans <b>Upload</b>
        - ```upload``` dans la collection Upload
    - Dans <b>users-permissions</b>:
        - ```connect``` dans la collection Auth
        - ```findone```, ```me``` et ```update``` sur la collection User
        - ```init``` dans la collection Userpermissions


##### Lancer le serveur avec la commande 
```
> npx strapi start
```
