# Docker

## Basics

`docker ps` - show running containers

`docker ps -a` - show running & stopped containers

`docker stop <container>` - stop a container

`docker stop $(docker ps -aq)` - stop all running containers

`docker rm $(docker ps -aq)` - remove all containers

`docker pull <image>` - Pull an image from docker registry

`docker run -d -p 80:80 --name container_name <image>` - run image in a container

`docker build -t <image>:v2 .` - build an image

`docker container prune` - remove all stopped container


## Troubleshooting

`docker logs -f <container>` - live logs of container

`docker logs --tail 10 <container>` - tail logs


## Copying Files Between Host and Container

`docker cp ./myfile.txt my-custom-container:/path/in/container/`

`docker cp my-custom-container:/path/in/container/myfile.txt ./`

## Monitoring 
`docker stats <container>` - real-time stats

`docker top <container>` - view processes running in a container

## Networking

Network Drivers :

**bridge** - default network driver, used for standalone containers need to communicate

**host** - removes network isolation between container and docker host

**overlay** - used for connecting multiple docker daemons together (swarm mode)

**macvlan** - allows you to assign a MAC address to a container, making it appear as a physical device on the network

**none** - disables all networking for a container

`docker network ls` - list of networks

`docker network create <network_name>` - create a network

`docker network connect <network_name> <container_name>` - connect to a network