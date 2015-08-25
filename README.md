# Introduction à Docker

Le but de ce projet est de donner quelques points d'entrée à l'utilisation de Docker.

## Installation

### Debian

Pour cette distribution une "Jessie" est la manière la plus directe d'installer docker avec:

```
apt-get install docker.io
```

### MacOSX

Comme docker a besoin d'une installation linux, windows ou Macosx utilise VirtualBox comme host principal. C'est le rôle de boot2docker de gérer la machine virtuelle linux. Elle est donc créée avec cet outil
#### Avec Home Brew
```
brew install docker-machine docker docker-compose
```

#### Avec un paquet officiel

Il faut suivre les indications depuis le site principal <http://docs.docker.com/mac/step_one/>.


## Concepts

### Host
Un host docker et une machine Linux (Virtuelle ou non) qui peut exécuter des containers docker.

### Images
Une image docker est la base d'un container. Elle est passive dans le sens qu'elle n'est pas exécutée. On peut récupérer une image existante sur le site docker hub <https://hub.docker.com/> avec la commande:

```
docker pull <image_name>
```
Il est possible de créer ses propres images en écrivant un fichier ```Dockerfile```. En général une image se termine par l'exécution d'une et une seule commande, par ex. ```mysqld```.

### Container
C'est l'exécution d'une image. Il est exécuté dans l'équivalent d'un processus LXC (Linux Container). En général un et un seul processus tourne dans le container.

Toutes les données sont supprimées lors de l'arrêt d'un container.

### Data volume
Comme les données d'un container ne sont pas persistantes, il existe la possibilité de créer des volumes de données qui peuvent être montée dans les containers. Les données sont stockées dans un répertoire du __docker host__.


## En pratique

### Environnement
La commande ```docker-machine``` permet de gérer un set de __host docker__.

Créer une nouvel __host docker__:

```
docker-machine create dev
```
Le host est prêt pour exécuter des containers, mais il faut mettre à jours les variables d'enivronnement:

```
eval "$(docker-machine env dev)"
```
Note: il est possible de le mettre dans les fichiers d'init de bash (.profile, .bashr, etc.).

### Mon premier container

Cette commande permet de récupérer une image du __docker hub__ et de l'exécuter en tant que container.

Notez que le container d'arrête quand la commande se termine. La deuxième exécution sera plus rapide car l'image __hello world__ sera stockée localement.

```
docker run hello-world
```

Pour voir la liste des images disponibles localement:

```
docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             VIRTUAL SIZE
hello-world         latest              af340544ed62        2 weeks ago         960 B
```

La commande listant les containers:
```
docker ps
```
ne retourne rien. Il faut ajouter une option pour voir les containers terminés:
```
docker ps -a
```


## Références

- Site principal docker: <https://www.docker.com/>