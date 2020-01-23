# DEV -> TEST -> PROD
 

 dev on local computer

 test on travis ci

 prod on elasticbeentalk aws


### Dockerfile.dev for development only
 command for custom dockerfile
 
 ```
docker build -f Dockerfile.dev .
 ```
Dockerfile for production


## Docker Volume
Docker Container refrence source code or files from local folder

command
```
docker run -v /app/node_modules -v $(pwd):/app -p 3000:3000 <image id>
```

First v is : Put a bookmark on node_modules folder if not node_modules from container will be overided from volume

TODO : 
Docker ignore some files or folders


docker-compose with customfile
build -> context: . # find location base
    -> dockerfile: Dockerfile.dev # dockerfile filename 

Run Test by override CMD

```
docker run <image id> npm run test
```

Live test

first build docker-compose

then 
```
docker exec -it <container id> npm run test
```


## React Production

try to build project to get builded file and then remove 
unused files like node_modules out for save disk