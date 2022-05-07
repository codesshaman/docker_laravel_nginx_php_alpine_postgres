FROM php:8.0.5-fpm-alpine

WORKDIR /var/www

RUN apk update add wget curl zip unzip nano mc 

RUN set -ex \
  && apk --no-cache add \
    postgresql-dev

RUN docker-php-ext-install pdo pdo_pgsql

RUN rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* var/cache/apk* && set -x

COPY ./php/php.ini /usr/local/etc/php/conf.d/php.ini