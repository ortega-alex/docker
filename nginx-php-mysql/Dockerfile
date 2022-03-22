FROM php:7.4-fpm-alpine

RUN docker-php-ext-install pdo pdo_mysql

# COPY --from=composer:latest /usr/bin/composer /usr/local/bin/composer

#RUN composer global require "laravel/laravel"

# Installing Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Pre run
RUN docker-php-source extract \
    && apk add --update --virtual .build-deps autoconf g++ make pcre-dev icu-dev openssl-dev \
    && apk add git openssh 