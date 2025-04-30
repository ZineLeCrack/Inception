FROM debian:12.10

RUN apt update && apt upgrade && apt install -y mariadb-server

COPY conf/50-server.cnf /etc/mysql/mariadb.conf.d/.
COPY init.sql /etc/mysql/init.sql
COPY script_mariadb.sh .

RUN mkdir /run/mysqld && chmod +x script_mariadb.sh

CMD ["./script_mariadb.sh"]
