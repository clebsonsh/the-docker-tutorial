FROM php:8.3-fpm-alpine

ENV PHP_GROUP=laravel
ENV PHP_USER=laravel

RUN adduser -g ${PHP_GROUP} -s /bin/sh -D ${PHP_USER}

RUN sed -i "s/user = www-data/user = ${PHP_USER}/" /usr/local/etc/php-fpm.d/www.conf
RUN sed -i "s/group = www-data/user = ${PHP_GROUP}/" /usr/local/etc/php-fpm.d/www.conf

RUN mkdir -p /var/www/html/public

RUN docker-php-ext-install pdo pdo_mysql

CMD ["php-fpm", "-y", "/usr/local/etc/php-fpm.conf", "-R"]
