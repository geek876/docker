FROM centos:centos6
MAINTAINER CKYConsulting UK <ckyconsulting.uk@gmail.com>
RUN yum -y update && yum clean all
RUN rpm -Uvh  http://dl.fedoraproject.org/pub/epel/6/x86_64/epel-release-6-8.noarch.rpm
RUN rpm -Uvh http://rpms.famillecollet.com/enterprise/remi-release-6.rpm
RUN rpm -Uvh http://pkgs.repoforge.org/rpmforge-release/rpmforge-release-0.5.3-1.el6.rf.x86_64.rpm
RUN yum -y install httpd wget tar git gcc make gcc-c++ sqlite-devel ruby-devel rubygems which
RUN yum -y install php php-devel php-xml php-mcrypt php-gd php-mysql php-mbstring php-pecl-xdebug php-pecl-imagick
RUN cd /usr/local/src \
    wget http://downloads3.ioncube.com/loader_downloads/ioncube_loaders_lin_x86-64.tar.gz \
    tar xvfz ioncube_loaders_lin_x86-64.tar.gz \ 
    PHP_VERSION=$(php -r "echo PHP_MAJOR_VERSION.'.'.PHP_MINOR_VERSION;") \
    sudo cp "ioncube/ioncube_loader_lin_${PHP_VERSION}.so" /usr/lib64/php5/modules/
RUN gpg --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3 
RUN \curl -sSL https://get.rvm.io | bash -s stable
RUN /bin/bash -l -c "rvm install 2.2.0"
RUN /bin/bash -l -c "gem install mailcatcher --no-ri --no-rdoc"
ADD ./oracle-instantclient-basic-10.2.0.5-1.x86_64.rpm /tmp/oracle-instantclient-basic-10.2.0.5-1.x86_64.rpm
ADD ./oracle-instantclient-devel-10.2.0.5-1.x86_64.rpm /tmp/oracle-instantclient-devel-10.2.0.5-1.x86_64.rpm
RUN yum install -y /tmp/oracle-instantclient-basic-10.2.0.5-1.x86_64.rpm
RUN yum install -y /tmp/oracle-instantclient-devel-10.2.0.5-1.x86_64.rpm
RUN printf "\n" | pecl install oci8
RUN echo 'extension=oci8.so' >> /etc/php.ini
EXPOSE 80
EXPOSE 1080
EXPOSE 1025
ADD start /start
RUN chmod 755 /start
CMD ["/start"]
