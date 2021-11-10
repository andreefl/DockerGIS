# Versão 7.4 como default
ARG PHP_VERSION=7.4
# Para usar outra versão, basta mudar o valor de PHP_VERSION no docker-compose
FROM php:${PHP_VERSION}-fpm-alpine

# Adiciona pacotes
RUN apk update \
    && apk upgrade \
    && apk add --no-cache bash