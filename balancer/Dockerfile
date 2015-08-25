# une image existe déjà pour nginx
FROM nginx

# copie des config
COPY nginx.conf /etc/nginx/nginx.conf
COPY myapp_nginx.conf /etc/nginx/conf.d/000-johntone.conf

# suppression de la conf par défaut
RUN rm /etc/nginx/conf.d/default.conf
