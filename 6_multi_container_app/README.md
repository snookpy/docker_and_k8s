

example app calculate Fibonacci

![](./example-app.png)



Flow
![](./flow.png)



CI Section will use this repo https://github.com/nuenook/multi_docker


## Deployed multi container on Elasticbeentalk 

config on Dockerrun.aws.json

amazon will use  => Amazon Elastic Container Service (ECS) 

that config with Task Definition

*Note

## Dockerrun.aws.json

### Hostname 
is like services name on docker-compose

### essential
if true when container is broken other containers will shutdown too


### links
 make container can able to connect to other container host
