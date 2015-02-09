MySQL Docker
To start the DB 
```
docker run -d -P --name mysql docker/image:tag 
```

To start the DB and create a new DB and user
```
docker run -d -P --name mysql -e 'DB_NAME=dbname1,dbname2' -e 'DB_USER=dbuser' -e 'DB_PASS=dbpass' docker/image:tag
```
To connect to DB
```
docker -it --rm --volumes-from mysql docker/image:tag mysql -uroot
```
