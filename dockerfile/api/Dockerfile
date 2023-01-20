FROM php:7.1-apache

RUN apt-get update && apt-get install --no-install-recommends -yq ${BUILD_PACKAGES} \
        build-essential \
        wget \
        ssh \
        git \
        libmcrypt-dev \
        libicu-dev \
        libzip-dev \
        librabbitmq-dev

ENV PHP_EXTENSIONS opcache pdo_mysql pcntl intl zip
RUN docker-php-ext-install ${PHP_EXTENSIONS}

ENV COMPOSER_ALLOW_SUPERUSER=1
RUN curl -sS https://getcomposer.org/installer | php -- --filename=composer --install-dir=/usr/local/bin

RUN a2enmod rewrite

COPY vhost.conf /etc/apache2/sites-enabled/000-default.conf