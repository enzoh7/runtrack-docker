# 🐘 Projet 05 : Docker Apache/PHP

**Objectifs :** Inclure un serveur web Apache dans une image Docker pour exécuter un script PHP simple.

**Réalisations :**
* Création d'un fichier `index.php` contenant la fonction `phpinfo();` pour afficher la configuration du serveur.
* Écriture d'un `Dockerfile` pour configurer l'image officielle `php:apache` et copier le fichier source à la racine du serveur.
* Construction de l'image Docker locale nommée `mon-serveur-php` (`docker build`).
* Déploiement du conteneur en mappant le port 80 (Apache) vers le port `8080` de la machine locale.
* Test de l'application sur le navigateur pour confirmer l'interprétation du code PHP, suivi de l'arrêt propre du conteneur.

*(Toutes les captures d'écran relatives à cet exercice, montrant le code, les commandes et le rendu web, sont stockées dans le dossier `img/`)*