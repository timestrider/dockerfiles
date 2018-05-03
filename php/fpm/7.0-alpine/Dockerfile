FROM php:7.0-fpm-alpine

MAINTAINER timestrider

ENV PHP_EXTRA_CONFIGURE_ARGS '--enable-fpm --with-fpm-user=git --with-fpm-group=www-data'

RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.ustc.edu.cn/g' /etc/apk/repositories; \
	adduser -g www-data -u 1000 -D -s /sbin/nologin git; \
	apk --no-cache add \
        freetype-dev \
        jpeg-dev \
        libmcrypt-dev \
		libxml2-dev \
		openssl-dev \
		zip \
		libedit-dev \
		postgresql-dev \
		curl-dev \
    && docker-php-ext-install iconv mcrypt mbstring \
		pdo pdo_mysql mysqli xml curl zip ftp opcache pdo_pgsql readline gd \
	&& docker-php-source delete; \