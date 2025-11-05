# Il nous faut une base (version de linux) pour faire marcher notre mini-site (on prend alpine)
FROM alpine:latest 

# On va lui dire d'installer un petit serveur web (busybox)
RUN apk update && apk add --no-cache busybox-extras

# Créatoin du dossier pour le mini-site
RUN mkdir -p /var/www/html

# Copie les fichiers du site dans l'image
COPY site/* /var/www/html/

RUN chmod -R 777 /var/www/html

# Exposition du port(réquisition d'un port pour notre conteneur)
EXPOSE 8083

# Configuration de notre image et commandes par défaut (pour que le serveur tourn en permanence)
CMD ["httpd", "-f", "-v", "-p", "0.0.0.0:8083", "-h", "/var/www/html"]
