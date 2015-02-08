PHP/Apache with Magento Dependencies
To start a new vhost
docker run -d -P --name vhost -v /path/to/vhost.conf:/etc/httpd/conf.d/vhost.conf -v /path/to/docroot:/var/www/html docker/image:tag 
