# Strapi application

A quick description of your strapi application :

Hm, a quick test of STRAPI as an API and a Backend.

# Installation

    npx create-strapi-app le-dossier-de-votre-choix --quickstart

    Si vous oubliez le drapeau --quickstart ce choix vous sera néanmoins proposé.

# Lancement

    npm start

# TIP

## Plugin Roles & Permissions

Le plugin Roles & Permissions qui permet d'accorder les droits d'accès aux requêtes distantes se situe maintenant dans _Réglages->Roles & Permissions_. Cliquer sur _Authenticated_ ou _Public_

Généralement pour _Authenticated_ : tout cocher.

Généralement pour _Public_ : cocher _findone_ et _find_

Voir TIP-roles_and_permissions.CHRIS.gif

## Passer des paramètres

On peut passer des paramètres comme ceci :

http://localhost:1337:/products?\_limit=2&sort=title

## Obtenir un JSON WEBTOKEN

Dans **Postman**, faire une requête POST (body->raw->JSON) :

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
