FROM php:7.4-apache

RUN apt-get update && apt-get install -y libpq-dev zip unzip git libpng-dev libzip-dev libxml2-dev libgmp-dev

RUN docker-php-ext-install pdo pdo_pgsql pgsql bcmath gd zip soap gmp intl

RUN a2enmod rewrite

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

WORKDIR /var/www/html

RUN mkdir -p -m 775 templates_c backups cache /storage/rt storage/voipcalls storage/customercalls storage/promotions storage/promotionschemas documents js/xajax_js/deferred



EXPOSE 80
