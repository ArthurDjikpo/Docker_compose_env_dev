FROM php:7.2-apache

RUN docker-php-ext-install pdo pdo_mysql &&\
    docker-php-ext-enable pdo_mysql && \
    rm -rf ~/tmp/$var/cache/apk/* &&\
    sed -i -r -e "s/DocumentRoot.*/DocumentRoot \/home\//"  /etc/apache2/sites-available/000-default.conf &&\
    chown www-data:www-data /var/www/html/ &&\
    useradd --create-home ipssi &&\
    usermod --gid www-data ipssi &&\
    adduser ipssi www-data
 
EXPOSE 30000