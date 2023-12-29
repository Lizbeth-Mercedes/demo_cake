FROM php:8.2-cli

# Instalar dependencias
RUN apt-get update && apt-get install -y \
    libfreetype6-dev \
    libjpeg62-turbo-dev \
    libpng-dev \
    libonig-dev \
    libxml2-dev \
    zip \
    curl \
    unzip \
    git  
# Instalar extensiones intl para cake php
RUN docker-php-ext-install pdo_mysql mbstring exif pcntl bcmath gd intl

# Instalar composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer


# Install CakePHP via Composer
RUN composer create-project --prefer-dist cakephp/app:^4.0

# Expose port 8765 for CakePHP server
EXPOSE 8765