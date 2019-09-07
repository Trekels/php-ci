FROM php:7.3-cli

RUN apt-get update

RUN apt-get install -y git zip unzip

RUN docker-php-ext-install \
    bcmath \
    sockets

COPY --from=composer /usr/bin/composer /usr/bin/composer

# install xdebug
RUN pecl install xdebug

COPY php-ci.ini $PHP_INI_DIR/conf.d/

# add php csfixer
ADD https://github.com/FriendsOfPHP/PHP-CS-Fixer/releases/download/v2.15.3/php-cs-fixer.phar /usr/local/bin/php-cs-fixer
RUN chmod a+x /usr/local/bin/php-cs-fixer


ENTRYPOINT ["/bin/bash"]
