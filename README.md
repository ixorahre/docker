# Create php Docker file and image build from it

##### Create php Dockerfile

```
FROM php:7.2-cli
COPY ./src /usr/src/myapp
WORKDIR /usr/src/myapp
CMD [ "php", "./docker_index.php" ]
```

##### Create our Docker image from my php Dockerfile

`docker build -t run-php .`

##### Check that my image has been created or not

`docker images`

##### Run my docker image which should have copied a local file called docker_index.php

`docker run -it --rm --name run-app run-php`







<br><br/><br/>
-by <br/>
Habibur Rahman
