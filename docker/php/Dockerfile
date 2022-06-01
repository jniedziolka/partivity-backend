FROM php:8.1-fpm

WORKDIR /var/www/html

RUN curl -sS https://getcomposer.org/installer |php \
    && mv composer.phar /usr/local/bin/composer

RUN docker-php-ext-install pdo_mysql bcmath

RUN groupadd -g 1000 www
RUN useradd -u 1000 -ms /bin/bash -g www www

COPY . .

COPY --chown=www:www . .

USER www
