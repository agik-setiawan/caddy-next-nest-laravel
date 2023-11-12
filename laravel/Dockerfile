FROM php:8.2-fpm

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --2 --filename=composer

RUN apt-get update && apt-get install -y \
    apt-utils \
    libfreetype6-dev \
    libjpeg62-turbo-dev \
    libpng-dev \
    libzip-dev \
    zip \
    wget

RUN docker-php-ext-configure gd --with-freetype --with-jpeg

RUN docker-php-ext-install gd \
    pdo_mysql \
    zip

RUN groupmod -o -g 1000 www-data && \
    usermod -o -u 1000 -g www-data www-data

EXPOSE 9000