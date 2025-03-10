# Use the official PHP image from the Docker Hub
FROM php:8.0-apache

# Copy the source code into the container
COPY src/ /var/www/html/

# Set the working directory
WORKDIR /var/www/html/

# Install any necessary dependencies
RUN docker-php-ext-install mysqli pdo pdo_mysql

# Expose port 80 to the outside world
EXPOSE 80

# Start Apache in the foreground
CMD ["apache2-foreground"]