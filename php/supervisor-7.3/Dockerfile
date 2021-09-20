FROM alitectec/php-fpm:7.3

USER root

RUN apt-get update && apt-get install supervisor -y

RUN ln -s  /etc/supervisor/supervisord.conf /etc/supervisord.conf

ADD . /var/www/

ADD laravel-worker.conf /etc/supervisor/conf.d/

CMD service supervisor start && tail -f storage/worker.log