# Create docker-compose file

##### Create php Dockerfile
```
FROM php:7.2-apache
```

##### Create my docker-compose file

```
version: "3"
services:
    www:
        build: .
        ports:
            - "8080:80"
        volumes:
            - ./src:/var/www/html/
        networks:
            - default
```

##### Stop and remove my docker container

```
docker-compose down
```

##### Start my docker container from docker-compose file

```
docker-compose up
```








<br><br/><br/>
-by <br/>
Habibur Rahman
