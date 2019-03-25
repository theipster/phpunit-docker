FROM php:7.3-alpine
MAINTAINER Alan Ip <theipster@users.noreply.github.com>
ENV PHPUNIT_VERSION=8.0.5

# Install wget
RUN apk add --no-cache --virtual .fetch-deps wget && \
# Pull in PHPUnit PHAR
    wget -O /tmp/phpunit.phar https://phar.phpunit.de/phpunit-$PHPUNIT_VERSION.phar && \
# Remove wget
    apk del --no-network .fetch-deps

# Set up app
VOLUME ["/app"]
WORKDIR /app

# Set up command
ENTRYPOINT ["php", "/tmp/phpunit.phar"]
CMD ["--help"]
