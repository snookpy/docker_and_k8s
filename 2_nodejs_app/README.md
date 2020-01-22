
# try dockering with nodejs app

## STEP Building

1. create nodejs web app
2. create a dockerfile
3. build image from dockerfile
4. connect to app from browser


## PORT Mapping
docker run -p 5000:5000
first is host port and then docker container port

## WORKDIR
set starting dir
/usr/app is equal to "./" 
//save place for linux based

## minimizing cache 
when change current line, will effect to all below code inside Dockerfile