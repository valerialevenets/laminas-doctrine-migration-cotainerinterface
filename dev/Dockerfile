FROM php:7.4

RUN apt-get update \
 && apt-get install -y git zlib1g-dev libicu-dev libmcrypt-dev libzip-dev zip libonig-dev \
 && docker-php-ext-configure intl \
 && docker-php-ext-install -j$(nproc) zip pdo pdo_mysql mbstring iconv calendar intl sockets \
 && pecl install xdebug-3.0.4 mailparse mcrypt apcu\
 && docker-php-ext-enable xdebug mailparse apcu\
 && curl -sS https://getcomposer.org/installer \
  | php -- --install-dir=/usr/local/bin --filename=composer --version=2.1.6

WORKDIR /var/www/laminas-doctrine-migration-container