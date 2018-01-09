FROM vonbraunlabs/php:7.2-apache-composer-redis

RUN docker-php-ext-install -j$(nproc) \
        iconv \
        pdo \
        pdo_mysql \
        zip

RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini" \
 && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini" \
 && echo "extension = redis.so" > "$PHP_INI_DIR/conf.d/redis.ini" \
 && echo "session.save_handler = rediscluster" >> "$PHP_INI_DIR/conf.d/redis.ini" \
 && echo "session.save_path = \"seed[]=tasks.redis:6379\"" >> "$PHP_INI_DIR/conf.d/redis.ini"

RUN apt-get install -y \
    time \
    wget

WORKDIR /var/www/html/
