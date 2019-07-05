FROM nginx:latest

MAINTAINER Mahmoud Zalt <mahmoud@zalt.me>

COPY ./sources.list.stretch /etc/apt/sources.list


ADD nginx.conf /etc/nginx/

# If you're in China, or you need to change sources, will be set CHANGE_SOURCE to true in .env.


RUN apt-get -y update \
    && apt-get -y upgrade \
    && usermod -u 1000  www-data

ARG PHP_UPSTREAM_CONTAINER=php-fpm
ARG PHP_UPSTREAM_PORT=9000

# Set upstream conf and remove the default conf
RUN echo "upstream php-upstream { server ${PHP_UPSTREAM_CONTAINER}:${PHP_UPSTREAM_PORT}; }" > /etc/nginx/conf.d/upstream.conf \
    && rm /etc/nginx/conf.d/default.conf

CMD ["nginx"]

EXPOSE 80 443
