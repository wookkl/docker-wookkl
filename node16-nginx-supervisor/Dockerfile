FROM ubuntu:20.04

MAINTAINER wookkl

RUN cd /etc/apt && \
    sed -i 's/deb.debian.org/ftp.daum.net/g' sources.list

# install nginx supervisor
RUN apt-get update && \
    apt-get install -y nginx && \
    apt-get install -y supervisor && \
    rm -rf /var/lib/apt/lists/* && \
    echo "\ndaemon off;" >> /etc/nginx/nginx.conf && \
    rm /etc/nginx/sites-enabled/default && \
    chown -R www-data:www-data /var/lib/nginx

# install nodejs
RUN apt-get update && \
    apt-get install -y curl && \
    curl -fsSL https://deb.nodesource.com/setup_16.x | bash - && \
    apt-get install -y nodejs && \
    apt-get install -y build-essential
