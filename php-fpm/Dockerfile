#
#--------------------------------------------------------------------------
# Final Touch
#--------------------------------------------------------------------------
#
FROM php:7.2-fpm-alpine

RUN apk add --update --no-cache openssh bash vim nodejs npm
RUN docker-php-ext-install pdo pdo_mysql

RUN npm i -g npm

COPY ./laravel.ini /usr/local/etc/php/conf.d
COPY ./xlaravel.pool.conf /usr/local/etc/php-fpm.d/

USER root

WORKDIR /var/www
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

CMD ["php-fpm"]

EXPOSE 9000
