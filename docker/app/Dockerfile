FROM php:7.2-cli

# Install PHP modules
RUN apt-get update \
  && pecl channel-update pecl.php.net \
  && pecl install amqp

COPY . /app
WORKDIR /app