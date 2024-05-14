# Utiliser une image PHP Apache comme base
FROM php:7.4-apache

# Installer git
RUN apt-get update && apt-get install -y git

# Créer un répertoire pour le site web
WORKDIR /var/www/html

# Cloner les fichiers du dépôt GitHub
RUN git clone https://github.com/Tidjene/myrepo.git .

# Exposer le port 80 pour le trafic web
EXPOSE 80

# Commande par défaut pour démarrer le serveur Apache
CMD ["apache2-foreground"]
