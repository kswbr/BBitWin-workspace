#
#--------------------------------------------------------------------------
# Final Touch
#--------------------------------------------------------------------------
#
FROM php:7.2-fpm-alpine3.7

RUN apk --no-cache update
RUN apk --no-cache upgrade
RUN apk --no-cache add \
    curl-dev \
    freetype-dev \
    libjpeg-turbo-dev \
    libpng-dev \
    libxml2-dev \
    zlib-dev \
    pcre-dev \
    g++ \
    make \
    bash \
    autoconf \
    vim \
    openssl \
    nodejs-npm

RUN docker-php-ext-install pdo pdo_mysql

# RUN npm i -g npm

COPY ./laravel.ini /usr/local/etc/php/conf.d
COPY ./xlaravel.pool.conf /usr/local/etc/php-fpm.d/

USER root

WORKDIR /var/www
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

CMD ["php-fpm"]

EXPOSE 9000
