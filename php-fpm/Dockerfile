FROM php:5.6-fpm


RUN apt-get update \
    && apt-get install libpng12-dev libfreetype6-dev libjpeg62-turbo-dev -qy 

RUN pecl install memcached-2.2.0 \
    && docker-php-ext-enable memcached