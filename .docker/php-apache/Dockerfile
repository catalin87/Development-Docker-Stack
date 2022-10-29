FROM php:8.1-apache

RUN apt-get update && apt-get upgrade -y

RUN apt-get install -y \
        librabbitmq-dev \
        libssh-dev \
    && docker-php-ext-install \
        bcmath \
        sockets \
        mysqli \
    && pecl install amqp \
    && pecl install redis \
    && docker-php-ext-enable \
        amqp \
        redis \
        mysqli \

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
