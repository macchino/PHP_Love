FROM php:7.2-apache

RUN apt-get -y update && apt-get install -y \
    sudo \
    wget
RUN apt-get update \
    && apt-get install -y zlib1g-dev \
    && apt-get install -y git \
    && apt-get install -y unzip \
    && docker-php-ext-install zip \
    && apt-get install -y libmcrypt-dev 

RUN docker-php-ext-install pdo_mysql mysqli mbstring



COPY --from=composer:latest /usr/bin/composer /usr/bin/composer 
COPY php.ini /usr/local/etc/php/
WORKDIR /var/www/html

EXPOSE 80