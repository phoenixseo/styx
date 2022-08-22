FROM docker.io/library/php:7-apache

# https://hub.docker.com/_/php?tab=tags&page=1&name=apache

### setup modules for mass-dynamic vhosts
RUN a2enmod \
  vhost_alias \
  alias

### php extensions helper
ADD https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions /usr/local/bin/
RUN chmod +x /usr/local/bin/install-php-extensions

### install some php extensions
RUN install-php-extensions bz2 exif gd imap mysqli pdo_mysql gettext xdebug

### add git (needed for composer)
RUN apt-get update
RUN apt-get install -y git

### install composer 2
RUN install-php-extensions @composer-2
