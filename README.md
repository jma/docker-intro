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
brew install boot2docker docker docker-compose
```

#### Avec un paquet dédier

Il faut suivre les indications depuis le site principal <http://docs.docker.com/mac/step_one/>.

#### Initialiser la machine virtuelle
```
boot2docker init #crée la machine virtuelle
boot2docker start #démarre la machine virtuelle
boot2docker ssh #se connecte en ssh à la machine virtuelle
```


## Références

- Site principal docker: <https://www.docker.com/>