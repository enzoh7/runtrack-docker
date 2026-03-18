# 🏗️ Projet 03 : Welcome to Docker - Part 2 (Build & React)

**Objectifs :** Construire une image personnalisée à partir d'un code source et comprendre le processus de mise à jour.

**Réalisations :**
* Clonage du dépôt GitHub officiel `welcome-to-docker` et analyse de son `Dockerfile` (basé sur `node:22-alpine`).
* Construction de l'image locale avec `docker build -t welcome-image .`.
* Déploiement du conteneur sur le port local `8080`.
* Compréhension du cycle de mise à jour : modification du code source en local, nécessité d'arrêter le conteneur, de reconstruire l'image (`build`) et de relancer un conteneur pour appliquer les changements.

> **📌 Note sur le rendu :** Les copier-coller intégraux des commandes de code et des logs de build se trouvent dans le fichier `readme.md` de ce dossier.