FROM docker.pkg.github.com/uniandesdsit/docker-plantilla-drupal/uniandes_plantilla:v1.0.0

# Se instala mysql-client para el correcto funcionamiento de Drush
RUN apt-get update

# Configuracion de Argumentos para GitHub y Version de Plantilla
ARG GITHUB_TOKEN 

# Copia archivos necesarios con personalización de medicina
COPY .htaccess profiles/andes/backup/
COPY composer.json /var/www/html

# Configurar e instalar Composer
RUN composer config -g github-oauth.github.com  ${GITHUB_TOKEN} && \
	composer install

# CMD
CMD ["apache2-foreground"]