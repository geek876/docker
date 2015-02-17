PHP/Apache with Magento Dependencies
To start a new vhost
```
docker run -d -P --name vhost --link mysql:db --link redis:redis -v /path/to/vhost.conf:/etc/httpd/conf.d/vhost.conf -v /path/to/docroot:/var/www/html docker/image:tag 
```
ex:
```
docker run -d -P --name testvhost --lisk mysql:db --link redis:redis -v testvhost.conf:/etc/httpd/conf.d/testvhost.conf -v testvhost_docroot:/var/www/html geek876/apache
```
Now check which local port does the testvhost container's port 80 map to (it is 49165 here )
```
docker ps -a
ONTAINER ID        IMAGE                   COMMAND             CREATED             STATUS              PORTS                                                                     NAMES
e8559b875853        geek876/apache:latest   "/start"            7 minutes ago       Up 7 minutes        0.0.0.0:49163->1025/tcp, 0.0.0.0:49164->1080/tcp, 0.0.0.0:49165->80/
```
From the host, now access
```
http://localhost:49165
```
OR
```
http://www.testvhost.conf:49165
```

