ARG PHP_VERSION=""
FROM php:${PHP_VERSION:+${PHP_VERSION}-}fpm-alpine

RUN apk update; \
    apk upgrade;

RUN apk add --no-cache apache2

RUN apk add --no-cache \
    php \
    php7-ctype \
    php7-fileinfo \
    php7-json \
    php7-mbstring \
    php7-openssl \
    php7-pdo \
    php7-tokenizer \
    php7-xml \
    nodejs \
    npm \
    git

RUN docker-php-ext-install \
    bcmath \
    pdo_mysql

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

WORKDIR /var/www/html/

EXPOSE 80

# Run httpd in foreground so that the container does not quit
# soon after start
# To run this container in the back ground use the -d option
#
#     $ sudo docker run -d broadtech/alpine-apache2
#
CMD ["-D","FOREGROUND"]

# Srart httpd when container runs
ENTRYPOINT ["/usr/sbin/httpd"]