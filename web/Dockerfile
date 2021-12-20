FROM php:7.3-apache

#Install git and MySQL extensions for PHP

RUN apt-get update && apt-get install -y git
RUN docker-php-ext-install pdo pdo_mysql mysqli
RUN a2enmod rewrite

# Install software 
RUN apt-get install -y git

RUN apt-get install -y \
    libzip-dev \
    zip \
    && docker-php-ext-install zip

# Clone the conf files into the docker container
RUN git clone https://github.com/SamueleLonghin/cs-basket
RUN cd cs-basket
RUN chmod -R 777 ./
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN composer update --working-dir /var/www/html/cs-basket/

COPY vendor /var/www/html/cs-basket/vendor/


COPY src /var/www/html/
COPY etc /etc/
EXPOSE 80/tcp
EXPOSE 443/tcp