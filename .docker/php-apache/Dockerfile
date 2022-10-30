FROM php:8.1-apache

RUN apt-get update && apt-get upgrade -y

RUN apt-get install -y \
        librabbitmq-dev \
        libssh-dev \
        apt-transport-https \
        gnupg \
        bash \
        curl \
        ca-certificates \
        libzip-dev \
        zip \
        libtidy-dev \
    && docker-php-ext-install \
        bcmath \
        sockets \
        mysqli \
        zip \
    && pecl install amqp \
    && pecl install redis \
    && docker-php-ext-enable \
        amqp \
        bcmath \
        sockets \
        redis \
        mysqli \
        zip

RUN sed -ri -e 's!/var/www/html!/var/www/html${APACHE_DOCUMENT_ROOT}!g' /etc/apache2/sites-available/*.conf
RUN sed -ri -e 's!/var/www/html!/var/www/html${APACHE_DOCUMENT_ROOT}!g' /etc/apache2/apache2.conf /etc/apache2/conf-available/*.conf


RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN curl -1sLf 'https://dl.cloudsmith.io/public/symfony/stable/setup.deb.sh' | bash
RUN apt install -y symfony-cli

RUN a2enmod rewrite
RUN service apache2 restart