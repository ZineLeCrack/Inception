FROM debian:12.10

RUN apt update && apt upgrade && apt install -y php-fpm php-mysqli curl

COPY conf/www.conf /etc/php/8.2/fpm/pool.d/.
COPY script_php.sh .

RUN chmod +x script_php.sh

CMD ["./script_php.sh"]
