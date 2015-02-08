FROM centos:centos6
MAINTAINER CKYConsulting UK <ckyconsulting.uk@gmail.com>
RUN yum -y update && yum clean all
RUN rpm -Uvh  http://dl.fedoraproject.org/pub/epel/6/x86_64/epel-release-6-8.noarch.rpm
RUN rpm -Uvh http://rpms.famillecollet.com/enterprise/remi-release-6.rpm
RUN rpm -Uvh http://pkgs.repoforge.org/rpmforge-release/rpmforge-release-0.5.3-1.el6.rf.x86_64.rpm
RUN yum -y install httpd 
RUN yum -y install php php-devel php-xml php-mcrypt php-gd php-mysql php-mbstring
EXPOSE 80
ADD start /start
RUN chmod 755 /start
CMD ["/start"]
