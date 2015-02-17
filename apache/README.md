PHP/Apache with Magento Dependencies
To start a new vhost
```
docker run -d -P --name vhost -v /path/to/vhost.conf:/etc/httpd/conf.d/vhost.conf -v /path/to/docroot:/var/www/html docker/image:tag 
```
ex:
```
docker run -d -P --name testvhost -v testvhost.conf:/etc/httpd/conf.d/testvhost.conf -v testvhost_docroot:/var/www/html geek876/apache
