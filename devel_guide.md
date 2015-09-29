## Guide pour l'utilisation des containers dans un environnement de test

Vous devez au préalable définir les variables d'environnement suivantes sur votre poste de travail pour vous connecter à distance sur le __host docker__ de test.
```sh
export DOCKER_MACHINE_NAME=boulimix.rero.ch
export DOCKER_HOST=tcp://`host $DOCKER_MACHINE_NAME | rev | cut -d" " -f1 | rev`:2375
```
> :warning: Toutes les commandes docker entrées sur votre poste de travail seront exécutées sur le __host docker__

```sh
# list les containers démarrés sur le_host docker
docker ps

# list les images déjà installées
docker images
```
