FROM php:7.4-fpm

RUN apt-get update \
	&& apt-get install -y \
		libzip-dev \
		zip \
		unzip \
		vim \
		nano \
		wget \
		apache2 \
		curl \
		git \
		moreutils \
		dnsutils \
		zlib1g-dev \
		libicu-dev \
		libmemcached-dev \
		g++ \
    && rm -rf /var/lib/apt/lists/*

# Install Composer
COPY --from=composer /usr/bin/composer /usr/bin/composer

# Run docker-php-ext-install for available extensions
RUN docker-php-ext-configure intl \
    && docker-php-ext-install pdo pdo_mysql opcache intl pcntl

RUN apt-get update -y \
  && apt-get install -y \
    libxml2-dev \
  && apt-get clean -y \
  && docker-php-ext-install soap

RUN usermod -u 1000 www-data

# Remove PHP-FPM pool configuration files
RUN rm -rf /usr/local/etc/php-fpm.d/*.conf

# Copy custom configuration files
COPY conf/php-fpm.conf /usr/local/etc/php-fpm.conf
COPY conf/www.conf     /usr/local/etc/php-fpm.d/www.conf

CMD php-fpm -F