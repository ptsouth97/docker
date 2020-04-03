# Docker Commands

## docs
* [docs.docker.com][www.docs.docker.com]

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
