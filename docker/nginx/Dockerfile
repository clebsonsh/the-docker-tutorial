FROM nginx:stable-alpine

ENV NGINX_USER=1001
ENV NGINX_GROUP=1001

RUN mkdir -p /var/www/html/public

ADD default.conf /etc/nginx/conf.d/default.conf

RUN sed -i "s/user www-data/user ${NGINX_USER}/" /etc/nginx/nginx.conf

RUN adduser -g ${NGINX_GROUP} -s /bin/sh -D ${NGINX_USER}
