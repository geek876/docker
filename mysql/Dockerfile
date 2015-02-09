FROM centos:centos6
MAINTAINER ckyconsulting.uk@gmail.com

RUN yum install -y mysql-server  \
 && rm -rf /var/lib/mysql/mysql 

ADD start /start
RUN chmod 755 /start

EXPOSE 3306

VOLUME ["/var/lib/mysql"]
VOLUME ["/run/mysqld"]

CMD ["/start"]
