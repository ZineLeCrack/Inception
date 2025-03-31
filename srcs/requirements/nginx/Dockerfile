FROM debian:12.10

RUN apt update && apt upgrade && apt install -y nginx curl openssl
RUN mkdir -p /etc/nginx/certs

COPY conf/default /etc/nginx/sites-available/.
COPY conf/nginx.conf /etc/nginx/.

RUN openssl req -x509 -nodes -out /etc/nginx/certs/inception.crt -keyout /etc/nginx/certs/inception.key -subj "/C=FR/ST=IDF/L=Paris/O=42/OU=42/CN=rlebaill.42.fr/UID=rlebaill"

CMD ["nginx", "-g", "daemon off;"]
