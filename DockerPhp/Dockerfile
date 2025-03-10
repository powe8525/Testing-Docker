# Use the official PHP image from the Docker Hub
FROM php:8.0-apache

# Set root password (for demo purposes, use a strong password in production)
RUN echo 'root:yourpassword' | chpasswd

# Install nano and other dependencies
RUN apt update && apt install -y nano

# Copy the source code into the container
COPY src/ /var/www/html/

# Set the working directory
WORKDIR /var/www/html/

# Install any necessary dependencies
RUN docker-php-ext-install mysqli pdo pdo_mysql

# Set correct permissions during build
RUN chown -R www-data:www-data /var/www/html \
    && chmod -R 755 /var/www/html

# Set Apache userapachectl -k restart

USER www-data

# Expose port 80 to the outside world
EXPOSE 80

# Start Apache in the foreground
CMD ["apache2-foreground"]