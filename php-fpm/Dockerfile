#
#--------------------------------------------------------------------------
# Final Touch
#--------------------------------------------------------------------------
#
FROM php:7.2-fpm-alpine
COPY ./laravel.ini /usr/local/etc/php/conf.d
COPY ./xlaravel.pool.conf /usr/local/etc/php-fpm.d/

USER root

WORKDIR /var/www

CMD ["php-fpm"]

EXPOSE 9000
