# Strapi application

A quick description of your strapi application :

Hm, a quick test of STRAPI as an API and a Backend.

# Installation

    npx create-strapi-app le-dossier-de-votre-choix --quickstart

    Si vous oubliez le drapeau --quickstart ce choix vous sera néanmoins proposé.

# Lancement

    npm start

# Problème

Avec npm start, il est impossible d'ajouter un "Collection Type" (Le bouton n'apparaît pas).

Il faut faire

    npm start strapi develop

# TIP

## Plugin Roles & Permissions

Le plugin Roles & Permissions qui permet d'accorder les droits d'accès aux requêtes distantes se situe maintenant dans _Réglages->Roles & Permissions_. Cliquer sur _Authenticated_ ou _Public_

Généralement pour _Authenticated_ : tout cocher.

Généralement pour _Public_ : cocher _findone_ et _find_

Voir TIP-roles_and_permissions.CHRIS.gif

# Ajouter des Collection Types

En plus de devoir démarrer le serveur avec **npm start strapi develop**, il est possible qu'il faille accorder les permissions concernant le Content-Type-Builder.

À chaque fois qu'on va ajouter une Collection, il sera nécessaire d'accorder les permissions aux deux roles (AUTHENTICATED et PUBLIC).

## Passer des paramètres

On peut passer des paramètres comme ceci :

http://localhost:1337:/products?\_limit=2&sort=title

## Obtenir un JSON WEBTOKEN

Dans **Postman**, faire une requête POST (body->raw->JSON) :

http://localhost:1337/auth/local

    {
        "identifier":"monlogin"
        "password":"monmdp"
    }

Faire **SEND**

La requête devrait renvoyer un **JSON WEBTOKEN** comme ceci :

    "jwt":"1mach1c0mm3c4trestrestreslong"

Lors d'une **seconde requête**, insérer ce **JSON WEBTOKEN**

Dans Authorization->TYPE choisir "Bearer Token" et insérer dans le champ token... le token.

Et faire par exemple une requête d'ajout de produit :

    {
        "title":"Test product"
        "description":"This is a test"
        "price":"99.88"
        "quantity:"100"
    }

Et là le produit devrait être ajouté.

# Référence (Traversy Media)

    https://www.youtube.com/watch?v=6FnwAbd2SDY

# Voir aussi

Ce tutoriel avec STRIPE API (paiement en ligne)

    https://youtu.be/QT3_zT97_1g

# Faire une requête FETCH depuis une application FRONT-END

    fetch("http://localhost:1337/todos")
      .then(res => res.json())
      .then(data => console.log(data));

# API ENDPOINTS

https://strapi.io/documentation/v3.x/content-api/api-endpoints.html#endpoints

# Se servir de jQuery dans un Composant React

    import $ from 'jquery'

Et dans une fonction :

    $("#exampleModal").modal();

On peut utiliser \$
