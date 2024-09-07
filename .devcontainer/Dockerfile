FROM php:8.3-fpm

# Install system dependencies
RUN apt-get update && apt-get install -y git curl libpng-dev libjpeg-dev libfreetype6-dev

# Install PHP extensions
RUN docker-php-ext-install pdo pdo_mysql gd

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Set working directory
WORKDIR /var/www

# Copy current directory to working directory
COPY . /var/www

# Install PHP dependencies
RUN composer install
