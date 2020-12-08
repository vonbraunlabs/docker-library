FROM php:7.2

RUN apt-get update && apt-get install -y \
        git \
        libzip-dev \
        unzip \
        wget \
        zip

RUN docker-php-ext-install -j$(nproc) \
        zip

ENV PATH "/composer/vendor/bin:$PATH"
ENV COMPOSER_ALLOW_SUPERUSER 1
ENV COMPOSER_HOME /composer
ENV COMPOSER_VERSION 1.10.5
COPY install-composer.sh ./
RUN ./install-composer.sh



