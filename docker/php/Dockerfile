FROM php:7.4-fpm
COPY php.ini /usr/local/etc/php/

WORKDIR /var/www

RUN apt-get update \
  && apt-get install -y \
  libzip-dev \
  git \
  unzip \
  vim

# PHP extensions install
RUN docker-php-ext-install zip

# Composer install
COPY --from=composer /usr/bin/composer /usr/bin/composer

# Laravel install
RUN composer global require "laravel/installer"