
# Example with Redis server container

Run build

```
docker build .
```

build with tag

```
docker build -t nuenook/redis-server:latest .

```

then

Start it

```
docker run fc6034234
```

start with tag name
(automatically select latest tag)
```
docker run nuenook/redis-server
```

Stop it

```
ctrl + c
```

## Command in Dockerfile

### FROM
FROM, is starting point of create Image like OS
Look up local first if not found will download from docker server 

### RUN
RUN, is running on Build procress (docker build .)
start intermediate container to complete procress
if RUN is complete, this intermediate contrainer will be removed

### CMD
wokring on intermediate container too
set primary command or script for containers
and the cmd will be Startup Command

## Cache
when swap RUN commands, cache will not be used,
rerun only that line change


## Docker commit

```
docker commit -c'CMD ["redis-server"]' 0a5ebaacf79e
```

