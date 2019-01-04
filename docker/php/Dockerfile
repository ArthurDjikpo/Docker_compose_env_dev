FROM php:7.2-apache

RUN apt-get update && \
    docker-php-ext-install pdo pdo_mysql &\
    useradd --create-home ipssi &\
    usermod -g groupname username
EXPOSE 30000