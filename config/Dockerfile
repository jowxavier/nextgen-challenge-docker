FROM php:8.3-fpm-alpine

WORKDIR /var/www/html

RUN apk add --update linux-headers && apk add postgresql-dev \
    && docker-php-ext-install pdo_pgsql opcache

RUN apk update \
    && apk add build-base autoconf

RUN pecl install xdebug-3.3.2 \
    && docker-php-ext-enable xdebug opcache

RUN apk del build-base autoconf \
    && apk cache clean

COPY . /var/www/html