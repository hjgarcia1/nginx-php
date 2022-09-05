FROM php:8.0-fpm

# Set working directory
WORKDIR /code

# Install dependencies
RUN apt-get update && apt-get install -y \
    build-essential \
    libpng-dev \
    libjpeg62-turbo-dev \
    libfreetype6-dev \
    locales \
    libzip-dev \
    zip \
    jpegoptim optipng pngquant gifsicle \
    vim \
    unzip \
    git \
    curl \
    libmcrypt-dev \
    openssl \
    nodejs \
    npm


# Clear cache
RUN apt-get clean && rm -rf /var/lib/apt/lists/*


RUN pecl update-channels && pecl install mcrypt-1.0.4 && docker-php-ext-enable mcrypt

# Install extensions
RUN docker-php-ext-install pdo_mysql zip exif pcntl
# RUN docker-php-ext-configure gd
# RUN docker-php-ext-install gd

# Install composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# setup npm to install all latest stuff
RUN npm install -g npm@latest

# Add user for application
RUN groupadd -g 1000 www
RUN useradd -u 1000 -ms /bin/bash -g www www

# Copy existing application directory contents
COPY . /code

# Copy existing application directory permissions
COPY --chown=www:www . /code

# Change current user to www
USER www

# Expose port 9000 and start php-fpm server
EXPOSE 9000
CMD ["php-fpm"]
