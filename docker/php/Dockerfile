FROM php:7.2-apache

RUN docker-php-ext-install pdo pdo_mysql &&\
    docker-php-ext-enable pdo_mysql && \
    rm -rf ~/tmp/$var/cache/apk/* &&\
    sed -i -r -e "s/DocumentRoot.*/DocumentRoot \/home\//"  /etc/apache2/sites-available/000-default.conf &&\
    sed -i -r -e "s/Order allow,deny.*/Require all granted/g"  /etc/apache2/*.conf &&\
    sed -i -r -e "s/Allow from all.*/ /g"  /etc/apache2/*.conf &&\
    sed -i -r -e "s/Require all denied.*/Require all granted/g"  /etc/apache2/*.conf &&\
    chown www-data:www-data /var/www/html/ &&\
    # useradd --create-home --gid www-data ipssi &&\
    useradd --create-home ipssi &&\
    usermod --gid www-data ipssi
    # impossible de changer de groupe le user 
 
EXPOSE 30000