FROM php:5.6-apache
RUN apt-get update && apt-get install -y libmcrypt-dev\
	libxslt-dev\
	libicu-dev\
	zlib1g-dev\
	libpng-dev\
	libjpeg-dev\
	git\
&& docker-php-ext-install bcmath\
	mcrypt \
	xsl \
	intl \
	pdo_mysql \
	soap \
	zip \
&& a2enmod rewrite \
&& docker-php-ext-configure gd --with-jpeg-dir=/usr/local/images/\
&& docker-php-ext-install gd\
&& echo "max_input_vars=5273" >> /usr/local/etc/php/php.ini\
&& service apache2 restart 
RUN cd .. && rm -r html \
&& git clone https://github.com/arturkult/ksiegarnia.git html && chmod 777 -R /var/www/html 
EXPOSE 80