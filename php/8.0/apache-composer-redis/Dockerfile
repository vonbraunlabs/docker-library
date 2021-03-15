FROM vonbraunlabs/php:8.0-apache-composer

RUN echo '' | pecl install redis && echo "extension=redis.so" > /usr/local/etc/php/conf.d/redis.ini
