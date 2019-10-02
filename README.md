# Create Docker file
```
FROM nginx
COPY html /usr/share/nginx/html
```

# Create our Docker image from our Dockerfile

`docker build --tag my_http_server .`

##### Check that our image has been created
`docker images`

##### Run our docker image on port 8080

`docker run -d -p 8080:80 --name my_http_server`  

##### Check my docker is running?
`http://localhost:8080`

##### Stop the running container

`docker stop CONTAINER_ID`

##### Find the running image ID

`docker images`

##### Remove the running image

`docker rmi my_http`

##### If removal fails force the removal

`docker rmi my_http --force`


<br><br/><br/>
-by <br/>
Habibur Rahman
