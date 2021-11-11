ARG PHP_VERSION=8.0
FROM php:${PHP_VERSION}-fpm-alpine

# Adiciona pacotes
RUN apk update \
    && apk upgrade \
    && apk add --no-cache bash

# Define o workdir padrão
WORKDIR /var/www