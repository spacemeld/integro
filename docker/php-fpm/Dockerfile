# Pulls an minimal image from Docker Hub, maintained by PHP.
# This uses alpine, which is a distribution of choice to keep the docker images size small.
# The environment uses slightly different set of commands to manage packages.
# Tag is specific as much as possible to reduce unexpected changes.
# We will be using MySQL as our choice of data store for this version.

FROM php:7.4-fpm-alpine3.12

# Author of this image.
LABEL maintainer="andy@spacemeld.com"

# Composer is needed for Laravel
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# Satisfy requirements for Laravel as listed in their documentation:
# * PHP >= 7.2.5
# * BCMath PHP Extension
# * Ctype PHP Extension
# * Fileinfo PHP extension
# * JSON PHP Extension
# * Mbstring PHP Extension
# * OpenSSL PHP Extension
# * PDO PHP Extension
# * Tokenizer PHP Extension
# * XML PHP Extension

# The official PHP-FPM Alpine image already has the following:
# * PHP 7.4.7
# * Ctype PHP Support
# * Fileinfo PHP Support
# * JSON PHP Support
# * Mbstring PHP Support
# * OpenSSL PHP Support
# * PDO PHP Support
# * Tokenizer PHP Support
# * XML PHP Support
# * MySQL Native Driver for PHP

# Given the above, we need to add support for:
# * BCMath
# * PDO MySQL PHP Extension

RUN docker-php-ext-install bcmath \
    pdo_mysql

ENTRYPOINT [ "php-fpm" ]
