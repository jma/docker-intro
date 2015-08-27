FROM python:2.7-slim

# information sur le créateur
MAINTAINER Johnny Mariéthoz <chezjohnny@gmail.com>

# installation des paquets Debian nécessaire à gunicorn
RUN apt-get update -y && apt-get install -y gcc

# les variables d'environnement pour l'utilisateur
ENV USER myuser
ENV HOME /home/myuser

# ajustement des paths pour pip --user
ENV PATH /usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:${HOME}/.local/bin

# création de l'utilisateur
RUN useradd --home-dir $HOME --create-home --shell /bin/bash --uid 1000 $USER

# création du répertoire de travail
RUN mkdir $HOME/www

# changement du répertoire de travail
WORKDIR ${HOME}/www

# copier le fichier d'application
COPY myapp.py  $HOME/www/

# ajustement des permissions
RUN chown $USER:$USER -R ${HOME}

# changement d'utilisateur
USER $USER

# intallation des modules python
RUN pip install --user gunicorn eventlet Flask

# commande par defaut: exécuter le serveur web
CMD gunicorn --log-file=- --bind 0.0.0.0:5000   -w 3 --worker-connections=2000 --backlog=1000  -k eventlet myapp:app
