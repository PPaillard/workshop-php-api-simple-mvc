# Simple MVC

## Description

Ce dépôt est une structure MVC PHP simple créée à partir de zéro.

Il utilise des bibliothèques intéressantes telles que Twig et Grumphp.
Pour cet exemple, les utilisateurs peuvent choisir l'une de leurs bases de données et voir les tables qu'elle contient.

## Étapes

1. Clonez le dépôt depuis Github.
2. Exécutez `composer install`.
3. Créez _config/db.php_ à partir du fichier _config/db.php.dist_ et ajoutez vos paramètres de base de données. Ne supprimez pas le fichier _.dist_, il doit être conservé.

```php
define('APP_DB_HOST', 'votre_hôte_db');
define('APP_DB_NAME', 'votre_nom_db');
define('APP_DB_USER', 'votre_utilisateur_db_qui_n_est_pas_root');
define('APP_DB_PASSWORD', 'votre_mot_de_passe_db');
```

4. Importez _database.sql_ dans votre serveur SQL, vous pouvez le faire manuellement ou utiliser le script _migration.php_ qui importera un fichier _database.sql_.
5. Exécutez le serveur web interne PHP avec `php -S localhost:8000 -t public/`. L'option `-t` avec `public` comme paramètre signifie que votre localhost ciblera le dossier `/public`.
6. Allez sur `localhost:8000` avec votre navigateur préféré.
7. À partir de ce kit de démarrage, créez votre propre application web.

### Utilisateurs Windows

Si vous développez sur Windows, vous devez modifier votre configuration git pour changer vos règles de fin de ligne avec cette commande :

`git config --global core.autocrlf true`

## Exemple

Un exemple (une liste basique d'articles) est fourni (vous pouvez charger le fichier _simple-mvc.sql_ dans une base de données de test). Les URL accessibles sont :

-   Page d'accueil à [localhost:8000/](localhost:8000/)
-   Liste des articles à [localhost:8000/items](localhost:8000/items)
-   Détails de l'article [localhost:8000/items/show?id=:id](localhost:8000/item/show?id=2)
-   Édition de l'article [localhost:8000/items/edit?id=:id](localhost:8000/items/edit?id=2)
-   Ajout d'un article [localhost:8000/items/add](localhost:8000/items/add)
-   Suppression d'un article [localhost:8000/items/delete?id=:id](localhost:8000/items/delete?id=2)

Vous pouvez trouver toutes ces routes déclarées dans le fichier `src/routes.php`. C'est dans ce même fichier que vous ajouterez vos propres nouvelles routes à l'application.
