FROM php:7.3-cli

RUN apt-get update

RUN apt-get install -y git zip unzip

RUN docker-php-ext-install \
    bcmath \
    sockets

COPY --from=composer /usr/bin/composer /usr/bin/composer

ENTRYPOINT ["/bin/bash"]
