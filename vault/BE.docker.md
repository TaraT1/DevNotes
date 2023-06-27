---
id: h1ncuonitjmz28hklzweh4w
title: docker
desc: ''
updated: 1688053623748
created: 1687868149484
---
Refs:   
https://www.youtube.com/watch?v=gAkwW2tuIqE  
source: https://github.com/fireship-io/docker-nodejs-basic-demo  
tut: https://fireship.io/lessons/docker-basics-tutorial-nodejs/

Docker is a way to package software so it can run  on any hdwr; reproduces dev environments
- dockerfile - blueprint for building docker img
- image - template for running docker cntainers; immutable snapshot; can be uploaded to cloud in both public and private registries
- container - a running process of an image

## Install
docker desktop (win or mac)
- gui and access to CL
- IDE extension - gives language support and link to remote registries

``` bash 
docker ps ## lists running containers
```
## Dockerfile
- contains code to build Docker img
```
FROM

WORKDIR

COPY

RUN

COPY

ENV

EXPOSE

CMD
```
## Build Image
``` bash
docker build -t dockerhubUserName/name:v.1 .  

#>>> successfully built <img id>
```
Can use as base img to create other imgs or run containers 

## PUSH
To use img push to container registry (dockerhub or cloud provider)
docker push <img id>

##RUN
```
docker run -p <img id or tag name>   
## -p: port forwarding from local : docker
```
Docker container still runs when terminal window closed. Use dashboard to close container.  State or data is lost.

## Volumes
To persist files, use volumes  
volume - dedicated folder on host machine. Container can create files that can be remounted into future containers.

``` 
docker volume create <>
## can mount inside container when run
```
Multiple containers can mount vol simultaneously and access set of files. Files persist when containers shut down

## Debugging
- docker desktop container holds logs
- cli in container or docker exec in linux env
- each container should run 1 process

## Docker Compose
Use multiple containers and define microservices  

docker-compose.yml inside root dir

``` bash
docker-compose up
## shut down
docker-compose down
```