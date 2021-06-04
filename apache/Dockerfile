ARG APACHE_VERSION=""
FROM httpd:${APACHE_VERSION:+${APACHE_VERSION}-}alpine

RUN apk update; \
    apk upgrade;

# Copy apache vhost file to proxy php requests to php-fpm container
COPY localhost.apache.conf /usr/local/apache2/conf/localhost.apache.conf
RUN echo "Include /usr/local/apache2/conf/localhost.apache.conf" \
    >> /usr/local/apache2/conf/httpd.conf

RUN sed -i '/LoadModule rewrite_module/s/^#//g' /usr/local/apache2/conf/httpd.conf
RUN { \
 echo 'IncludeOptional conf.d/*.conf'; \
 } >> /usr/local/apache2/conf/httpd.conf \
 && mkdir /usr/local/apache2/conf.d