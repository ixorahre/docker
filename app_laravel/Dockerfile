FROM php:7.2-apache 
#FROM php:7.2-fpm-alpine3.7

RUN docker-php-ext-install mysqli
RUN docker-php-ext-install pdo_mysql
RUN pecl install xdebug
RUN docker-php-ext-enable xdebug

RUN apt-get update && apt-get install -y \
  wget \
  vim \
  libssl-dev \
  openssl \
  ssl-cert \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/* \
  && a2enmod ssl \
  && a2ensite default-ssl


RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
RUN php -r "if (hash_file('sha384', 'composer-setup.php') === 'a5c698ffe4b8e849a443b120cd5ba38043260d5c4023dbf93e1558871f1f07f58274fc6f4c93bcfd858c6bd0775cd8d1') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
RUN php composer-setup.php
RUN php -r "unlink('composer-setup.php');"
RUN cp ./composer.phar /usr/bin/composer
RUN a2enmod rewrite

COPY ./php.ini /usr/local/etc/php/php.ini
COPY ./000-default.conf /etc/apache2/sites-available/000-default.conf
COPY ./apache2.conf /etc/apache2/apache2.conf

