FROM php-fpm:latest

RUN apt-get update && apt-get install -y \
    wget \
    zlib1g-dev \
    libicu-dev \
    libjpeg-dev \
    libfreetype6-dev
RUN docker-php-ext-configure intl
RUN docker-php-ext-configure gd \
    --with-jpeg=/usr/include/ \
    --with-freetype=/usr/include/
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN curl -sS https://get.symfony.com/cli/installer | bash

RUN docker-php-ext-install pdo pdo_postgres gd intl | bash
WORKDIR /www
