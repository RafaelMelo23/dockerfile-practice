
FROM php:8.2-apache

WORKDIR /app

RUN docker-php-exit-install mysqli && a2enmod rewrite

COPY src/ /var/www/html/

