FROM php:7.4-apache

# Cài các dependency cần thiết
RUN apt-get update && apt-get install -y \
    libpng-dev libjpeg-dev libfreetype6-dev libzip-dev unzip git vim \
    libicu-dev libxml2-dev libxslt-dev \
    && docker-php-ext-configure gd --with-freetype --with-jpeg \
    && docker-php-ext-install gd mysqli zip intl \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

# Bật rewrite module của Apache
RUN a2enmod rewrite

# Thiết lập timezone mặc định (tùy chọn)
RUN echo "date.timezone=UTC" > /usr/local/etc/php/conf.d/timezone.ini

# Copy source Moodle vào container
COPY . /var/www/html/

# Cấp quyền đúng cho Apache
RUN chown -R www-data:www-data /var/www/html

# Expose cổng 80
EXPOSE 80
