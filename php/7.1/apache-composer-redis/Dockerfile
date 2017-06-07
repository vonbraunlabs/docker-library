FROM vonbraunlabs/php:7.1-apache-composer

RUN apt-get install -y wget

RUN wget https://pecl.php.net/get/redis-3.1.2.tgz \
    && tar -zxvf redis-3.1.2.tgz

COPY redis_session.patch redis-3.1.2/

RUN cd redis-3.1.2 \
    && patch < redis_session.patch \
	&& phpize \
    && ./configure \
    && make -j$(nproc) \
    && make install

