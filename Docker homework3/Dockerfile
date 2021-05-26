FROM php:7.0-apache
RUN apt-get update && a2enmod rewrite
RUN apt-get install apt-utils -y && apt-get install wget -y && apt-get install tar -y
RUN cd ~ && wget https://wordpress.org/latest.tar.gz && tar zxvf latest.tar.gz && mv wordpress/* /var/www/html
RUN chown -R www-data:www-data /var/www/html && chmod -R 755 /var/www/html
RUN rm -rf latest.tar.gz && rm -rf wordpress
EXPOSE 80

# Install xdebug
#RUN pecl install xdebug && docker-php-ext-enable xdebug

# Install Less for WP-CLI
#RUN apt-get update && apt-get -y install less

# Install WP-CLI
#RUN curl -s -o /usr/local/bin/wp \
 #   https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar \
 #   && chmod +x /usr/local/bin/wp
#CMD -e WORDPRESS_DB_USER=wpuser \
#    -e WORDPRESS_DB_PASSWORD=password \
#    -e WORDPRESS_DB_NAME=wpdb -p 8080:80 -v /root/wordpress/html:/var/www/html --link wordpressdb:mysql --name wpcontainer -d

