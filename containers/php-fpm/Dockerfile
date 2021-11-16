ARG PHP_VERSION=8.0
FROM php:${PHP_VERSION}-fpm

# Adiciona pacotes
RUN set -eux; \
    apt-get update; \
    apt-get upgrade -y; \
    apt-get install -y --no-install-recommends \
    apt-utils \
    gnupg2 \
    libzip-dev zip unzip \
    curl \
    libz-dev \
    libpq-dev \
    libjpeg-dev \
    libpng-dev \
    libfreetype6-dev \
    libssl-dev \
    libwebp-dev \
    libxpm-dev \
    libmcrypt-dev \
    libonig-dev; \
    rm -rf /var/lib/apt/lists/*

RUN docker-php-ext-configure zip; \
    docker-php-ext-install pdo_pgsql; \
    docker-php-ext-install pgsql; \
    docker-php-ext-configure gd \
    --prefix=/usr \
    --with-jpeg \
    --with-webp \
    --with-xpm \
    --with-freetype; \
    docker-php-ext-install gd;

RUN apt-get clean && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* && \
    rm /var/log/lastlog /var/log/faillog

# Define o workdir padrão
WORKDIR /var/www