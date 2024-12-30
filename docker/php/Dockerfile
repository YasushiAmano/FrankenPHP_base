FROM dunglas/frankenphp:1


RUN install-php-extensions \
    pcntl \
    pdo_mysql \
    gd \
    intl \
    zip \
    opcache

# cwebp導入
RUN apt-get update && \
    apt-get -y install --no-install-recommends webp=1.2.4* && \
    rm -rf /var/lib/apt/lists/*

# Composer
SHELL ["/bin/bash", "-o", "pipefail", "-c"]
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Install xdebug
RUN pecl install xdebug && docker-php-ext-enable xdebug

# .bashrcの設定を追加
COPY bashrc /root/.bashrc

ENTRYPOINT ["php", "artisan", "octane:frankenphp"]
