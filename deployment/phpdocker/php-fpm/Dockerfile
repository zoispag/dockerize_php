FROM phpdockerio/php72-fpm:latest
WORKDIR "/application"

# Install selected extensions and other stuff
RUN apt-get update \
    && apt-get -y --no-install-recommends install php7.2-mysql php7.2-sqlite3 \
    && apt-get clean; rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

# Install composer
RUN cd /tmp && \
    php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" && \
    php composer-setup.php --install-dir=/usr/bin --filename=composer

# Install nodejs & npm
RUN curl -sL https://deb.nodesource.com/setup_6.x -o nodesource_setup.sh && \
	chmod +x nodesource_setup.sh && \
	./nodesource_setup.sh && \
	apt-get -y install nodejs && \
	apt-get -y install build-essential && \
	rm ./nodesource_setup.sh