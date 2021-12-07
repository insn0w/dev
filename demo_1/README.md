Demo 1
ntroduction to docker cli

View the Docker version and commands

docker
docker version
docker info
docker run --help
docker images --help
Download Node.js 16 Apline and Nginx 1.20 Alpine

docker images
docker pull node:16-alpine
docker pull nginx:1.20-alpine
docker images
docker inspect nginx:1.20-alpine | jq
Start a container in foreground and background mode

docker ps
docker run nginx:1.20-alpine
docker ps
docker ps -a
docker rm $(docker ps -l -q)
docker ps -a
CONTAINER_ID=$(docker run -d nginx:1.20-alpine)
echo $CONTAINER_ID
docker ps
docker inspect $CONTAINER_ID | jq
Exec a command in the container

docker exec $CONTAINER_ID echo Hi from the container
docker exec -it $CONTAINER_ID /bin/sh
exit
Stop and delete a container

docker stop $CONTAINER_ID
docker ps -a
docker rm $CONTAINER_ID
docker ps -a
Start a container in interactive mode with auto remove

docker run -it --rm nginx:1.20-alpine /bin/sh
hostname
exit
docker ps -a
Start a named container

docker run -d --name nginx nginx:1.20-alpine
docker ps -a
docker rm -f nginx
docker ps -a
Navigation

Back to main
Next demo
