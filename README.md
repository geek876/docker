1. Clone the git repo
 
2. Build containers 

   ```
   # cd docker/mysql

   # docker build -t geek876/mysql .

   # cd docker/apache

   # docker build -t geek876/apache .

   # cd docker/redis

   # docker build -t geek876/redis .

   ```
3. First Start MySQL Container 

   ```
   # docker run -P -d --name mysql geek876/mysql (this will start with an empty mysql instance)

   # docker run -P -d --name mysql  -e 'DB_NAME=dbname1' -e 'DB_USER=dbuser' -e 'DB_PASS=dbpass' geek876/mysql (this will start mysql instance and create a database dbname1 with user dbuser and pass dbpass)

   ```
4. Second, Start Redis Container

   ```
   # docker run -P -d --name redis geek876/redis 

   ```
5. Finally start Apache (Application Container)

   ```
   # docker run -P -d --name apache --link mysql:mysql --link redis:redis geek876/apache

   ```
