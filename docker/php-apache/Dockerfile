FROM php:7.4.15-apache

ARG APACHE_DOCUMENT_ROOT
ENV APACHE_DOCUMENT_ROOT $APACHE_DOCUMENT_ROOT

RUN sed -ri -e 's!/var/www/html!${APACHE_DOCUMENT_ROOT}!g' /etc/apache2/sites-available/*.conf
RUN sed -ri -e 's!/var/www/!${APACHE_DOCUMENT_ROOT}!g' /etc/apache2/apache2.conf /etc/apache2/conf-available/*.conf

RUN apt-get -y update \
&& apt-get install -y libicu-dev \
&& docker-php-ext-configure intl \
&& docker-php-ext-install intl \
&& docker-php-ext-install pdo pdo_mysql mysqli

RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y git

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN apt-get update && apt-get install -y mariadb-client
