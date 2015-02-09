FROM centos:centos6
RUN rpm -Uvh  http://dl.fedoraproject.org/pub/epel/6/x86_64/epel-release-6-8.noarch.rpm
RUN yum install -y redis
EXPOSE      6379
ENTRYPOINT  ["redis-server"]
