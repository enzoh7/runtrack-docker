// =====================================================================
// Commande : Lancement du conteneur welcome-to-docker
// =====================================================================
PS C:\wamp64\www\Welcome docker 1> docker run -it --rm -p 8080:80 docker/welcome-to-docker
/docker-entrypoint.sh: /docker-entrypoint.d/ is not empty, will attempt to perform configuration    
/docker-entrypoint.sh: Looking for shell scripts in /docker-entrypoint.d/
/docker-entrypoint.sh: Launching /docker-entrypoint.d/10-listen-on-ipv6-by-default.sh
10-listen-on-ipv6-by-default.sh: info: Getting the checksum of /etc/nginx/conf.d/default.conf       
10-listen-on-ipv6-by-default.sh: info: Enabled listen on IPv6 in /etc/nginx/conf.d/default.conf     
/docker-entrypoint.sh: Sourcing /docker-entrypoint.d/15-local-resolvers.envsh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/20-envsubst-on-templates.sh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/30-tune-worker-processes.sh
/docker-entrypoint.sh: Configuration complete; ready for start up
2026/03/17 10:56:51 [notice] 1#1: using the "epoll" event method
2026/03/17 10:56:51 [notice] 1#1: nginx/1.29.0
2026/03/17 10:56:51 [notice] 1#1: built by gcc 14.2.0 (Alpine 14.2.0)
2026/03/17 10:56:51 [notice] 1#1: OS: Linux 6.6.87.2-microsoft-standard-WSL2   
2026/03/17 10:56:51 [notice] 1#1: getrlimit(RLIMIT_NOFILE): 1048576:1048576        
2026/03/17 10:56:51 [notice] 1#1: start worker processes
2026/03/17 10:56:51 [notice] 1#1: start worker process 30
172.17.0.1 - - [17/Mar/2026:10:58:08 +0000] "GET / HTTP/1.1" 200 651 "-" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/145.0.0.0 Safari/537.36" "-"
172.17.0.1 - - [17/Mar/2026:10:58:08 +0000] "GET /static/css/main.27312bf9.css HTTP/1.1" 200 791 "http://127.0.0.1:8080/" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/145.0.0.0 Safari/537.36" "-"
172.17.0.1 - - [17/Mar/2026:10:58:08 +0000] "GET /static/js/main.c9e951e4.js HTTP/1.1" 200 382506 "http://127.0.0.1:8080/" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/145.0.0.0 Safari/537.36" "-"
172.17.0.1 - - [17/Mar/2026:10:58:08 +0000] "GET /favicon.ico HTTP/1.1" 200 15086 "http://127.0.0.1:8080/" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/145.0.0.0 Safari/537.36" "-"

// =====================================================================
// Commande : Vérification de la version de Docker
// =====================================================================
PS C:\wamp64\www\Welcome docker 1> docker --version
Docker version 29.2.1, build a5c7197

// =====================================================================
// Commande : Affichage des informations Docker
// =====================================================================
PS C:\wamp64\www\Welcome docker 1> docker info
Client:
 Version:    29.2.1
 Context:    desktop-linux
 Debug Mode: false
 Plugins:
  ai: Docker AI Agent - Ask Gordon (Docker Inc.)
  buildx: Docker Buildx (Docker Inc.)
  compose: Docker Compose (Docker Inc.)
Server:
 Containers: 8
  Running: 4
  Paused: 0
  Stopped: 4
 Images: 9
 Server Version: 29.2.1
 Storage Driver: overlayfs
 Operating System: Docker Desktop
 OSType: linux
 Architecture: x86_64
 CPUs: 16
 Total Memory: 7.61GiB

// =====================================================================
// Commande : Récupération de l'image welcome-to-docker
// =====================================================================
PS C:\wamp64\www\Welcome docker 1> docker pull docker/welcome-to-docker
Using default tag: latest
latest: Pulling from docker/welcome-to-docker
Digest: sha256:c4d56c24da4f009ecf8352146b43497fe78953edb4c679b841732beb97e588b0
Status: Image is up to date for docker/welcome-to-docker:latest
docker.io/docker/welcome-to-docker:latest

// =====================================================================
// Commande : Liste des images locales
// =====================================================================
PS C:\wamp64\www\Welcome docker 1> docker images
IMAGE                             ID             DISK USAGE   CONTENT SIZE   EXTRA
adminer:latest                    2fb88b98da9f        170MB         46.4MB    U 
docker/welcome-to-docker:latest   c4d56c24da4f       22.2MB         6.03MB    U 
mysql:8.0                         a3dff78d8762       1.08GB          247MB    U 
nginx:stable                      810ad1346ec7        240MB         65.8MB    U 
php:8.2-fpm                       2974f4c56916        698MB          178MB
phpmyadmin/phpmyadmin:latest      42a200db07b4       1.09GB          221MB    U 
redis:alpine                      fd83658b0e40        134MB         34.9MB    U 
sevenajay/mario:latest            8541a39162f3        325MB         94.8MB    U 
unit_symfony-app:latest           16aaf3a0317d        803MB          211MB    U 

// =====================================================================
// Commande : Liste des conteneurs en cours d'exécution
// =====================================================================
PS C:\wamp64\www\Welcome docker 1> docker ps
CONTAINER ID   IMAGE                      COMMAND                  CREATED              STATUS              PORTS                                         NAMES
da4a5c178e2b   docker/welcome-to-docker   "/docker-entrypoint.…"   About a minute ago   Up About a minute   0.0.0.0:8080->80/tcp, [::]:8080->80/tcp       compassionate_austin
bbf05a492535   adminer                    "entrypoint.sh docke…"   8 days ago           Up 52 minutes       0.0.0.0:8081->8080/tcp, [::]:8081->8080/tcp   Symfony_adminer
fd477aa87dcf   phpmyadmin/phpmyadmin      "/docker-entrypoint.…"   8 days ago           Up 52 minutes       0.0.0.0:8082->80/tcp, [::]:8082->80/tcp       Symfony_phpmyadmin
5c6d63d5783f   redis:alpine               "docker-entrypoint.s…"   3 weeks ago          Up 52 minutes       0.0.0.0:6379->6379/tcp, [::]:6379->6379/tcp   graphist_redis