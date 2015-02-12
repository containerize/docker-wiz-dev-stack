FROM tutum/nginx:latest

VOLUME ["/var/www", "/etc/nginx/sites-enabled"]

RUN apt-get update
RUN apt-get install -y supervisor curl wget php5-fpm php5-mysql php5-mcrypt php5-gd php5-memcached php5-curl php5-xdebug

RUN mkdir -p /var/log/supervisor
RUN mkdir -p /etc/nginx
RUN mkdir -p /var/run/php5-fpm

ADD supervisord.conf /etc/supervisor/conf.d/supervisord.conf

EXPOSE 80

CMD ["/usr/bin/supervisord"]