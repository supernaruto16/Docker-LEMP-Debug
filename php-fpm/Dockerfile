FROM php:fpm-alpine

RUN rm -f /usr/local/etc/php-fpm.d/zz-docker.conf /usr/local/etc/php-fpm.d/www.conf
COPY conf.d/custom-php-fpm.conf /usr/local/etc/php-fpm.d/www.conf

RUN mv /usr/local/etc/php/php.ini-production /usr/local/etc/php/php.ini

COPY conf.d/custom-php.ini /usr/local/etc/php/conf.d/custom-php.ini

RUN apk add --no-cache tzdata
ENV TZ Asia/Ho_Chi_Minh
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

WORKDIR /var/www/html
CMD ["php-fpm", "--nodaemonize"]