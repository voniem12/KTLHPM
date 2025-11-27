FROM php:8.2-apache

# Cài các package hữu ích (apt tools, ping, nano, vim, curl)
RUN apt-get update && apt-get install -y --no-install-recommends \
    iputils-ping curl vim nano net-tools \
    git unzip libpng-dev libjpeg-dev libfreetype6-dev libxml2-dev libzip-dev libicu-dev libonig-dev \
  && docker-php-ext-configure gd --with-freetype --with-jpeg \
  && docker-php-ext-install -j$(nproc) gd mysqli intl mbstring zip opcache xml \
  && apt-get clean && rm -rf /var/lib/apt/lists/*

RUN a2enmod rewrite

RUN mkdir -p /var/moodledata && chown -R www-data:www-data /var/moodledata

WORKDIR /var/www/html

EXPOSE 80
