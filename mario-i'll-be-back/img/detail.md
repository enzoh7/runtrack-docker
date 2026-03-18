# 🍄 Projet 04 : I'll be back (Super Mario)

**Objectifs :** Déployer une application existante en mappant les ports et comparer l'utilisation de l'interface en ligne de commande (CLI) avec l'interface graphique (GUI) de Docker Desktop.

**Réalisations :**
* Recherche et rapatriement de l'image `sevenajay/mario:latest` depuis le Docker Hub.
* Double déploiement : Lancement d'un conteneur isolé via le terminal (`docker run -p 8600:80...`) et d'un second via l'interface de Docker Desktop (sur le port `8601`).
* Gestion du cycle de vie des conteneurs via les deux méthodes (CLI & GUI) : identification (`docker ps`), arrêt (`docker stop`) et suppression.
* Résolution d'un conflit de suppression d'image en utilisant la suppression forcée de conteneur (`docker rm -f`).

*(Les captures d'écran du gameplay sur le navigateur et des commandes d'exécution/GUI sont disponibles dans le dossier `img/`)*