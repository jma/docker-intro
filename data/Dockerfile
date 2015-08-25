# n'importe quelle image fait l'affaire, mais de préférence une qui est déjà en cache
FROM python:2.7-slim

ENV USER myuser
# création de l'utilisateur avec un uid réutilisé dans les autres containers
RUN useradd --shell /bin/bash --uid 1000 $USER

# création du répertoire
RUN mkdir -p /data && chown $USER:$USER -R /data

# définition du volume
VOLUME ["/data"]
