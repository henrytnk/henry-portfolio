FROM wordpress:php8.2-apache

# Install Composer and WP-CLI dependencies
RUN apt-get update && apt-get install -y \
    unzip curl git less mariadb-client less libzip-dev less \
    && docker-php-ext-install zip

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php && \
    mv composer.phar /usr/local/bin/composer

# Install WP-CLI
RUN curl -O https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar && \
    chmod +x wp-cli.phar && mv wp-cli.phar /usr/local/bin/wp

# Enable mod_rewrite
RUN a2enmod rewrite