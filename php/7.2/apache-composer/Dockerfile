FROM php:7.2-apache

RUN apt-get update && apt-get install -y \
        bash \
        curl \
        git \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        libpng*-dev \
        mercurial \
        openssh-client \
        openssl \
        subversion \
        unzip \
        wget \
        zip

ENV PATH "/composer/vendor/bin:$PATH"
ENV COMPOSER_ALLOW_SUPERUSER 1
ENV COMPOSER_HOME /composer
ENV COMPOSER_VERSION 1.10.5

COPY install-composer.sh ./
RUN ./install-composer.sh

RUN composer global require hirak/prestissimo

RUN a2enmod rewrite \
    && printf 'RewriteEngine On\nRewriteCond %%{REQUEST_FILENAME} !-f\nRewriteRule ^ index.php [QSA,L]\n' > /var/www/html/.htaccess

