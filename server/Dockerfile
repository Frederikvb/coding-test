FROM php:7.2-fpm-stretch

RUN apt-get -y update --fix-missing
RUN apt-get upgrade -y

# important libraries
RUN apt-get -y install --fix-missing apt-utils build-essential libcurl3 libcurl3-dev  

# useful tools
RUN apt-get -y install vim iputils-ping git curl zip 

# Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Imagick 
RUN apt-get install -y \
    libmagickwand-dev --no-install-recommends \
    && pecl install imagick \
	&& docker-php-ext-enable imagick

# Xdebug
RUN pecl install xdebug-2.6.0
RUN docker-php-ext-enable xdebug

# Other PHP7 Extensions
RUN apt-get -y install libsqlite3-dev libsqlite3-0 mysql-client
RUN docker-php-ext-install pdo_mysql 
RUN docker-php-ext-install pdo_sqlite
RUN docker-php-ext-install mysqli

# Composer install
WORKDIR /var/www/html/server
COPY composer.* ./
RUN composer install --prefer-source --no-interaction

COPY . /var/www/html/server



