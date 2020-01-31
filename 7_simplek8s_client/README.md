# Kubernetes
    Will get the `multi-client` to run this developments

## Diffrent of docker-compose 
1. Only image builded maybe on Docker.hub

2. Config file per Object

3. Manually set up networking


## Descript in .yaml
Each .yaml config file will create each Objects:
  - StatefulSet
  - ReplicaController
  - Pod, is for run Container
  - Deployment Clostly Pods but good for development and production
  - Service, for Networking

### apiVersion
each api version defiens a different set of Objects
1. `v1` have configs: 
    - componentStatus
    - configMap
    - Endpoints
    - Event
    - Namespace
    - Pod
2. `apps/v1`
    - ControllerRevision
    - StatefulSet

### Kind
    Represent type of Object
### metadata
- name is name of pod will created
- labels is will link to network on Selector (key: value)
### name of containers
    name for connecting to other Pod
### ports of containerPort
    port's containers to outside world

### spec
- selector: component: web, sent to labels on Pod Objects (key is component, value is web)
## Pod
    Grouping containers one or more inside it
    maybe have closely related containers

## Services
    sets up networking in a K8s Cluster, subtype:
    define in spec:
- `ClusterIP`
- `NodePort` exposes a container to the outside world (dev purposes)
    `ports` is an array
    - port: is for `other Pod` needs connect to this Pod
    - targetPort: target to container's port
    - nodePort: is typing out on Browser (mapping Host port)
- `LoadBalancer`: lagacy thing, getting network traffic into a cluster
- `Ingress`: exposes set of services to the outside world


## kubectl

### Feed a config file to Kubectl
```
kubectl apply -f <filename>
```

### Print the status of all running pods, services
```
kubectl get pods

kubectl get services

kubectl logs client-pod -p 
```

### get detail
```
kubectl describe <pbject_type> <object name>
```

### delete pod
```
kubectl delete -f <config file>
```

### update image in pod
```
kubectl set image <object_type>/<object_name> <container_name>=<new_mage to use>
```
## Imperative Deployments
    Do exactly these steps to arrive at this container setup

## Declartive Deployments
    Out container setup should look like this, make it happen

    Limit config update:
        only can change image, 
        cannot change port, containers number, name


## Pods and Deployment Object types:
### Pods 
    single set of containers
    Good for one-off dev purposes
    Rarely used directly in production
### Deployment
 runs set of identical pods (one or more)
 Monitors the state of each pod, updating as necessary
 Good for dev
 Good for production
 will have `Pod Template` to create Pod
 - template: every single Pod Config inside here
 - replicas: number of different pods will have
 - selector: similar in Services
    - matchLabels: handle on label Pod Configs will have multiple pods