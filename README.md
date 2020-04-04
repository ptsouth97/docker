# Docker Commands

## docs
* [https://docs.docker.com](https://docs.docker.com)

## basic commands
* docker <command> <subcommand> (options)
* docker version  -> shows version
* docker info -> shows details about setup
* docker   -> list of commands

## run container
* docker container run --publish 80:80 --detach --name webhost nginx
* docker container ls  -> shows running containers
* docker container logs webhost  -> shows logs
* docker container top webhost -> shows processes running in container
* docker container --help
* docker container rm -f 63f  -> stop container
* docker stop webhost

## multiple containers
* docker container run -d -p 3306:3306 --name db -e MYSQL_RANDOM_ROOT_PASSWORD=yes mysql
* docker container run -d --name webserver -p 8080:80 httpd
* docker container run -d --name proxy -p 80:80 nginx
* docker container ls
* curl localhost:8080
* docker container stop _
* docker container rm _

## inside containers
* docker container top mysql
* docker container inspect mysql --> see one container
* docker container stats  --> see all containers

## shell inside containers
* docker container run -it --name proxy nginx bash  -> starts new container interactively
* docker container exec -it -> run additional command in existing container

## network concepts
* docker container run -p --> change port
* docker container port webhost  --> port check
* docker network ls --> shows networks that have been created
* docker network create --> spawns a new virtual network for you to attach containers to
* docker network inspect --> inspect a network
* docker network connect --> attach a network to a container
* docker network disconnect --> detach a network from container

* docker container ls
* docker container run -d --name my_nginx --network new_nginx
* docker container exec -it my_nginx ping new_nginx

## Assignment
* docker container run --rm -it centos:7 bash
	* ym update curl
	* docker container run --rm -it ubuntu:14:04 bash
	* curl --version

## Docker Hub
* docker pull nginx:1.11  --> gets image from docker hub

## Image Layers
* union file system
* docker image ls
* docker history nginx:latest
* docker image inspect nginx

## Image Tagging
* docker image tag --help
* refer to image by repository, tag, image id
* docker image tag nginx bretfisher/nginx  --> change repository name
* docker login --> login to docker hub profile
* docker logout

## Building Images
* FROM command
* ENV environment variable
* RUN executes shell commands
* EXPOSE ports to expose on virtual network
* CMD runs when container is launched
* docker image build -t customnginx .
* docker image prune  --> cleans up "dangling" images
