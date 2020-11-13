# Docker
* to show all images present locally
> docker images
* pull image
> docker pull nginx
## CONTAINERS
* run image in docker
* containers are running instances of images
> docker run nginx:latest
* show running containers
> docker container ls
-d in detached mode
docker run -d nginx:latest
* another way to check running container
> docker ps
* map localhost 8080 port to port 80 inside docker
> docker run -d -p 8080:80 nginx:latest
* import multiple ports
> docker run -d -p 8080:80 -p 3000:80 nginx:latest
* stop container by name
> docker stop zen_jepsen
> docker start zen_jepsen
* show all/stopped container
> docker ps -a
* delete container
> docker rm name/id
* remove all container, if all containers are stopped
> docker rm $(docker ps -aq) 
* force to remove also running containers
> docker rm -f $(docker ps -aq) 
* get only ids of all containers
> docker ps -aq
* give name to a container
> docker run --name website -d -p 8080:80 nginx:latest
* formatting docker ps result
> export FORMAT=#ID\\t{{.ID}}\nName\\t{{.Names}}\nImage\\t{{.Image}}\nPorts\\t{{.Ports}}
>   \nCommand\\t{{.Command}}\nCreated\\t{{.CreatedAt}}\nStatus\\t{{.Status}}\n”
> docker ps --format=$FORMAT
## VOLUMES
* volumes allows to share data between host and container and between containers ro: readonly
> docker run --name website -d -p 8080:80 -v ~/work/Test/dockerExercise/website:/usr/share/nginx/html:ro nginx:latest
* remove docker container
> docker rm -f website
* get inside docker
> docker exec -it website bash
any change in volumes folder will be shown on both sides
* share volumes between containers
> docker run --help
> docker run --name website-copy --volumes-from website -d -p 8081:80 nginx
mount volumes from specified container
## Docker File
dockerfile -> image -> container
[Reference](https://docs.docker.com/engine/reference/builder/)
all commands to create a docker file
> FROM nginx:latest
> ADD . /usr/share/nginx/html
from nginx image
add everything in current directory to following directory
* look for docker file in . current directory and build from it
> docker build --tag website:latest .
Show all images
> docker run --name website -p 8080:80 -d website:latest
create Dockerfile
take node image -> go to /app directory -> copy directory -> RUN cmd -> command
run 
> FROM node:latest
> WORKDIR /app
> ADD . .
> RUN npm install
> CMD node index.js
build Dockerfile
> docker build -t user-service-api:latest
running image
> docker run --name user-api -d -p 3000:3000 user-service-api:latest
build image again
## Caching and Layers
Layer is used by commands and layer is used in caching
> npm i -S react webpack gulp grunt
if any step is changed all steps after that are build again
So to take advantage of caching so it will not run nom install again
> FROM node:latest
> WORKDIR /app
> ADD package*.json ./
> RUN npm install
> ADD . .
> CMD node index.js
build again now npm will not run when source is changed
## ALPINE
improve image size, small-simple-secure
pull node image with latest alpine
> docker pull node:lts-alpine
> docker pull nginx:alpine
change image to alpine image in Dockerfile
> FROM node:alpine
> FROM nginx:alpine
## Tags, Versioning and Tagging
Allow you to control image version, avoid breaking changes and Safe
> FORM node:14.15.0-alpine3.12
> FORM nginx:1.19.4-alpine
remove image, build and run
Only one image can be with same repository and tag, otherwise it is named none
> docker build -t alianjum0-website:latest .
> docker tag alianjum0-website:latest alianjum0-website:1
change title in index
> docker build -t alianjum0-website:latest .
> docker tag alianjum0-website:latest alianjum0-website:2
now we have images with tag 1,2 and latest
run each image
> docker run --name alianjum-latest alianjum0-website:latest
> docker run --name alianjum-1 alianjum0-website:1
> docker run --name alianjum-2 alianjum0-website:2
## Docker Registries
let you store and distribute images
used in CI/CD pipeline
* Docker Hub
* quay.io
* Amazon ECR
create repository website in docker hub
tag images accoring to the repository alianjum0/website:tag
> docker tag alianjum0-website:1 alianjum0/website:1
> docker tag alianjum0-website:2 alianjum0/website:2
> docker tag alianjum0-website:latest alianjum0/website:latest
login to dokcer in terminal
> docker login
push image to repository
> docker push alianjum0/website:1
> docker push alianjum0/website:2
> docker push alianjum0/website:latest
remove images
> docker rmi alianjum0/website:1
> docker rmi alianjum0/website:2
> docker rmi alianjum0/website:latest
pull latest image from docker hub
> docker pull alianjum0/website
> docker run --name alianjum0-website -p 9000:80 -d alianjum0/website
## Docker inspect
debug docker container
fully inspect container
> docker inspect 87b54e016129
shows id, creation time, state, arguments, image, log path, name, platform,
hoscongfig, network config, devices, readonly paths, mounts, config, envioment
variable, node version
## Docker Logs
show docker logs
> docker logs 87b54e016129
follow the current logs
> docker logs -f 87b54e016129
## Docker exec
go inside container and see whats happening
-i interactive, -t tty
check from cmd arguments in inspect of bash path
> docker exec -it 87b54e016129 /bin/sh
# Kubernetes
* container orchestration tool
* 100 may be 1000 of containers
* trend to eicroservices
* increasd usage of containers
* proper way to manage 
Features:
high availability -> no downtime
scalability -> high performance
disaster recovery -> backup and restore
Basic Architecture
atleast one Master
worker nodes: kubelet- talk to cluster
different number of docker container runing on worker nodes
master node run multiple kubernetes processes, which are nessary to run cluster
properly
* API server- a container- entry point ot k8s cluster to which other clients will  talk to e.g. UI,API, CLI
* Controller Manager: keep an overview of whats happening
* scheduler: responsible for scheduling containers on different node according
  to work load and server resources
* etcd: key value storage, hold any time current state of k8s cluster
backup and restore is done through etcd
* Virtual Network: all nodes inside the cluster, VN allow to talk Master to
  Worker nodes. creates one unified machine 
Worker nodes do most of the work and needs more resources
however master node is much more important
should have a backup of master node
## POD, Service and Ingress
basic components of k8s
POD: smaller unit in k8s
abstraction over container
you only interact with k8s layer
usually 1 application/container per Pod
each Pod gets its internal ip address
Pod can die easily and another Pod is created in that place with different IP
Service:
permanent IP address can be connect to service
life cycle of service and Pod is not connected
if Pod dies, service and its IP address will stay
External service, internal service
Ingress:
it is in-front of service to change ip:port to url
routing traffic
ingress -> service -> Pod
### ConfigMap and Secret
external configuration to application
e.g DB_URL=mongo-db
Secret: 
use to store secret data
stored in base 64 encoded
use it as environment variable of properties file
### Data Storage
Volumes: persistent storage
storage on local machine or remote or outside of k8s cluster
if data Pod is restarted it the data is taken from volumes
K8s cluster is separate from storage
k8s doesn't manage storage
### Blueprint: Deployment Stateful set
Replicate everything on multiple server
service is persistent IP address and also load balancer
define blueprint for Pod and then create deployment e.g how many Pods to build
Deployments:
blueprint, deployment, abstraction of Pods
in practice work with Deployment rather than Pods
DB can't be replicated because of state management
StatefulSet:
This solve the problem of state management in StatefulSet
It is difficult to manage
So it is common practice to host database outside K8s cluster
### Minikube and Kubectl
Minikube:
test on local envirnoment K8s cluster
Master and worker process run on one node cluster
docker container runtime pre-installed
run through virtualbox
Kubectl:
Allow to interact with k8s cluster
Allow to also interact with Minikube cluster
It interacts with API server with command line
### Installing Minikube
install a hypervisor
> brew install hyperkit
for ubuntu install virtualbox
> sudo apt-get install virtualbox virtualbox-ext-pack
install minikube
> brew install minikube
minikube install kubectl as a dependency
start minikube
> minikube start --vm-driver=virtualbox
use virtualbox hypervisor to start minikube
get status of the k8s cluster nodes
> kubectl get nodes
minikube status
> minikube status
client version, server version
> kubectl version
minikube for start up and deleting the cluster
kubectl for everything else. configuring the cluster
### Create deployment
get pod
> kubectl get pod
get services
> kubectl get services
get deployment
> kubectl get deployment
**create** command is used to create k8s components
There is an abstraction layer over Pod that is **deployment**
create and nginx Deployment
> kubectl create deployment nginx-depk --image=nginx
to show the logs of the application inside pod by name
> kubectl logs nginx-depk-867fbf486c-m9zcf
create a mongo-db deployment
> kubectl create deployment mongo-depl --image=mongo
get more information about pod starting
> kubectl describe pod mongo-depl-5fd6b7d4b4-7cb6k
gets the terminal of the container
> kubectl exec -it mongo-depl-5fd6b7d4b4-7cb6k -- bin/bash
### Kubectl APPLY F
k8s configuration file
**apply** takes the file with the configuration to run
> kubectl apply -f nginx-deployment.yaml
[nginx-depl.yaml](https://gitlab.com/nanuchi/youtube-tutorial-series/-/blob/master/kubernetes-configuration-file-explained/nginx-deployment.yaml)
it can create and also update deployment
if replicas is changed to 2, it will create a new pod
**delete** deployment from file
> kubectl delete -f nginx-deployment.yaml
## Deploying mongodb and mongo express
MongoDB Pod (will have an) -> Internal Service (will provide db URL)
[ConfigMap][d2] (will have db URL)
[Secret][d3](will have db user, password)
[mongo.yaml][d1] (will use ConfigMap, Secret to create mongoDB and Internal Service)
[mongoExpress.yaml][d4] (will use ConfigMap, Secret to create mongo Express and
external service)
[ingress.yaml][d5] (for entry point)
Mongo Express (will have) -> External Service (external IP, port)
[d1](https://gitlab.com/nanuchi/youtube-tutorial-series/-/blob/master/demo-kubernetes-components/mongo.yaml)
[d2](https://gitlab.com/nanuchi/youtube-tutorial-series/-/blob/master/demo-kubernetes-components/mongo-configmap.yaml)
[d3](https://gitlab.com/nanuchi/youtube-tutorial-series/-/blob/master/demo-kubernetes-components/mongo-secret.yaml)
[d4](https://gitlab.com/nanuchi/youtube-tutorial-series/-/blob/master/demo-kubernetes-components/mongo-express.yaml)
[d5](https://gitlab.com/nanuchi/youtube-tutorial-series/-/blob/master/demo-kubernetes-components/ingress.yaml)
### Main mongo.yaml configurations
kind for the type of component
> kind: Deployment
metadata contains name and labels of the component
> metadata: name, labels
spec contains number of replicas to create, 
template contains blueprint for the Pod e.g container name, image, ports,
environment variable
environment variables are taken from Secret component 
> spec: replicas, template
We are using mongo image,
It has default port 27017 and we are using environment variable for
username, password
Create Service
We can create a separate yaml file or use the same file, 
yaml can have multiple document by using ---
They usually belong together, so its a good idea to put them together
> kind: Service
selector tell the Pod to connect to using label of the Pod
port: service port to export
targerPort: is the port of the Pod
### mongo-secret.yaml
kind: Secret
type: Opaque is the default key value pair type, TLS is also present
data contains username, password
Secret contains base-64 encoded values, 
simple way to create base64 value
> echo -n 'text' | base64
Secret component is created before mongodb, because mongodb is using
Secret, otherwise we are using it without creating it
> kubectl apply-f mongo-secret.yaml
now run mongodb Deployment and service
> kubectl apply -f mongo.yaml
to get detail of the service
> kubectl describe service mongodb-service
**EndPoints** is the IP address and port of the pod
We can check the IP of the Pod by showing additional output
> kubectl get pod -o wide
get all the component for one application
> kubectl get all | grep mongodb
### mongo express deployment
name: mongo-express
image: mongo-express
image starts at port 8081
we will export the port by containerPort
MongoDB address and credentials need to be provided by environment variables
It requires ConfigMap for DB URL
we need to create ConfigMap first
Create external service to access from outside
create service in the same file
> kind: Service
LoadBalancer type in spec make service except external request by assigning service an external
address, LoadBalancer name is confusing because if two internal container are
present, internal service will also act as LoadBalancer
> type: LoadBalancer
we have to define another port, which is the port of the node,
this port is between 30000-32767
> nodePort: 30000
This service will have a type of LoadBalancer, 
Whereas if type is not defined, default type is assigned which is ClusterIP
### mongo-configmap.yaml
> kind: ConfigMap
It is like Secret except there is only one type so type variable is not present
the name of the mongodb service is the DB URL.
> database_url: mongodb-service
create configMap
> kubectl apply -f mongo-configmap.yaml
now create mongo-express and service
> kubectl apply -f mongo-express.yaml
log mongo-express
> kubectl logs mongo-express-78fcf796b8-tzb9b
> kubectl get service
External IP of mongo-express-service is showing pending, on a real k8s setup,
it will show actual IP address a public one
In munikube we assign a public IP address by using command
> minikube service mongo-express-service
This will assign a public IP and open in browser mongo-express
So when a request is made by browser, It will follow this scenario

> browser -> mongo-express-service -> mongo-express -> mongodb-service -> mongodb

[reference](https://youtu.be/bhBSlnQcq2k)
