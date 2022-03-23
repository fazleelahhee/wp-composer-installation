FROM php:7.4.2-apache
RUN apt-get update -y && apt-get install -y libonig-dev libwebp-dev libjpeg62-turbo-dev libpng-dev libxpm-dev \
    libfreetype6-dev
RUN apt-get -y install git
RUN docker-php-ext-install pdo pdo_mysql mysqli

RUN docker-php-ext-configure gd --with-webp --with-jpeg \
     --with-xpm --with-freetype

RUN docker-php-ext-install gd
# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN a2enmod rewrite
RUN a2enmod ssl
RUN service apache2 restart