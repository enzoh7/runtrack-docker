// =====================================================================
// Commande : Clonage du dépôt GitHub officiel
// =====================================================================
PS C:\wamp64\www\Welcome docker 2> git clone git@github.com:docker/welcome-to-docker.git
Cloning into 'welcome-to-docker'...
remote: Enumerating objects: 185, done.
remote: Counting objects: 100% (105/105), done.
remote: Compressing objects: 100% (75/75), done.
remote: Total 185 (delta 78), reused 30 (delta 30), pack-reused 80 (from 3)
Receiving objects: 100% (185/185), 483.70 KiB | 1.27 MiB/s, done.
Resolving deltas: 100% (92/92), done.

// =====================================================================
// Commande : Navigation dans le dossier cloné
// =====================================================================
PS C:\wamp64\www\Welcome docker 2> cd welcome-to-docker

// =====================================================================
// Commande : Construction de l'image personnalisée (Build)
// =====================================================================
PS C:\wamp64\www\Welcome docker 2\welcome-to-docker> docker build -t welcome-image .
[+] Building 96.4s (12/12) FINISHED                                                               docker:desktop-linux
 => [internal] load build definition from Dockerfile                                                              0.2s
 => => transferring dockerfile: 676B                                                                              0.2s 
 => [internal] load metadata for docker.io/library/node:22-alpine                                                 1.9s
 => [auth] library/node:pull token for registry-1.docker.io                                                       0.0s
 => [internal] load .dockerignore                                                                                 0.1s
 => => transferring context: 52B                                                                                  0.0s 
 => [1/6] FROM docker.io/library/node:22-alpine@sha256:8094c002d08262dba12645a3b4a15cd6cd627d30bc782f53229a2ec... 16.4s
 => => resolve docker.io/library/node:22-alpine@sha256:8094c002d08262dba12645a3b4a15cd6cd627d30bc782f53229a2ec... 0.0s 
 => => sha256:c699e235cde407e9ab634f43f63d20708c76c61d2817bd98708fc1aa50c09397 1.26MB / 1.26MB                   0.8s 
 => => sha256:ed87be4595e508c0f2a1ff7a1810938267171d1018a91c41b6dc191f15ca818c 52.07MB / 52.07MB                 12.8s 
 => => sha256:7c9e1e1c637a965a5768a81fd902f4df05debe64963fcf7c7ed4c5401cc6bcd3 447B / 447B                       0.6s
 => => extracting sha256:ed87be4595e508c0f2a1ff7a1810938267171d1018a91c41b6dc191f15ca818c                        3.3s 
 => => extracting sha256:c699e235cde407e9ab634f43f63d20708c76c61d2817bd98708fc1aa50c09397                        0.1s 
 => => extracting sha256:7c9e1e1c637a965a5768a81fd902f4df05debe64963fcf7c7ed4c5401cc6bcd3                        0.0s
 => [internal] load build context                                                                                 0.4s
 => => transferring context: 708.73kB                                                                             0.4s 
 => [2/6] WORKDIR /app                                                                                            0.2s 
 => [3/6] COPY package*.json ./                                                                                   0.1s 
 => [4/6] COPY ./src ./src                                                                                        0.1s 
 => [5/6] COPY ./public ./public                                                                                  0.1s
 => [6/6] RUN npm install     && npm install -g serve@latest     && npm run build     && rm -fr node_modules      69.9s 
 => exporting to image                                                                                            7.1s
 => => exporting layers                                                                                           4.3s
 => => exporting manifest sha256:763f89315f2986d70143726480bab8fb86ace6bd2dbdcc2acbbeecb034852515                 0.0s
 => => exporting config sha256:e634fc1c6ca115c583b6553b62cb793cba005a89029d5264c4105197b0358b09                   0.0s
 => => naming to docker.io/library/welcome-image:latest                                                           0.0s
 => => unpacking to docker.io/library/welcome-image:latest                                                        2.6s 

// =====================================================================
// Commande : Lancement du conteneur à partir de l'image buildée
// =====================================================================
PS C:\wamp64\www\Welcome docker 2\welcome-to-docker> docker run -d -p 8080:80 welcome-image
b411489a6242e5d4479139fba1ee9d3f499b539ad7b156268dd7617b5e3b2edc

// =====================================================================
// Commande : Vérification du conteneur en cours d'exécution
// =====================================================================
PS C:\wamp64\www\Welcome docker 2\welcome-to-docker> docker ps
CONTAINER ID   IMAGE                   COMMAND                  CREATED          STATUS          PORTS                                         NAMES
b411489a6242   welcome-image           "docker-entrypoint.s…"   19 minutes ago   Up 19 minutes   0.0.0.0:8080->80/tcp, [::]:8080->80/tcp       adoring_mayer
bbf05a492535   adminer                 "entrypoint.sh docke…"   8 days ago       Up 5 hours      0.0.0.0:8081->8080/tcp, [::]:8081->8080/tcp   Symfony_adminer
fd477aa87dcf   phpmyadmin/phpmyadmin   "/docker-entrypoint.…"   8 days ago       Up 5 hours      0.0.0.0:8082->80/tcp, [::]:8082->80/tcp       Symfony_phpmyadmin
5c6d63d5783f   redis:alpine            "docker-entrypoint.s…"   3 weeks ago      Up 5 hours      0.0.0.0:6379->6379/tcp, [::]:6379->6379/tcp   graphist_redis