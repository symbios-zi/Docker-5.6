FROM php:5.6-fpm


RUN apt-get update && \
    apt-get install -y --no-install-recommends \
        curl \
        libmemcached-dev \
        libz-dev \
        libpq-dev \
        libjpeg-dev \
        libpng12-dev \
        libfreetype6-dev \
        libssl-dev \
        libmcrypt-dev \
        libgearman-dev \
        libmagickwand-dev

# Install the PHP mcrypt extention
RUN docker-php-ext-install mcrypt


#####################################
# mysql
#####################################
RUN docker-php-ext-install mysqli \
    && docker-php-ext-install pdo_mysql


#####################################
# gd:
#####################################

# Install the PHP gd library
RUN docker-php-ext-install gd && \
    docker-php-ext-configure gd \
        --enable-gd-native-ttf \
        --with-jpeg-dir=/usr/lib \
        --with-freetype-dir=/usr/include/freetype2 && \
docker-php-ext-install gd


####################################
# memcached
####################################
RUN pecl install memcached-2.2.0 \
    && docker-php-ext-enable memcached


####################################
# stats
####################################
RUN pecl install stats-1.0.5 \
    && docker-php-ext-enable stats

####################################
# gearman client
####################################
RUN pecl install gearman-1.0.3 \
    && docker-php-ext-enable gearman


####################################
# Zip 
####################################
RUN docker-php-ext-install zip

####################################
# Opcache 
#################################### 
RUN docker-php-ext-install opcache \
    && docker-php-ext-enable opcache

####################################
# Imagick 
#################################### 
RUN pecl install imagick \
    && docker-php-ext-enable imagick


####################################
# Redis 
####################################
RUN pecl install redis \
&&  docker-php-ext-enable redis