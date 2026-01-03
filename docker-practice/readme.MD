image and container:
image = bare minimum os + system packages + application runtime + app code + dependencies
container = if we run the image we get container, container is running instance
docker commands:
docker pull -> pull the image from docker repository
docker images -> show all images
docker rmi <image_name or image_id> -> remove images 
docker ps -> all running containers
docker ps -a -> all containers
docker start <image_name or image_id> -> start the container
docker stop <image_name or image_id> -> stop the container
docker rm <image_name or image_id> -> delete stopped container
docker rm -f <image_name or image-id> -> delete running container
docker inspect <cont-id or image-id> -> info about container or image
docker login -u <user-name> and password -> login for docker repo in your ec2 instance
docker build -t <image-name>:<tag-name> . -> . refers current directory
docker tag <oldtag-name> <newtag-name>
docker push <url>/<account-name>/<image-name> -> push image into docker repository
docker run -d --name <cont-name> -p <host-port:cont-port> <image-name> -> pull + start + run the container
-d -> detached mode 
-p -> port
--name -> name of the container
docker exec -it <cont-name or cont-id> bash -> goto inside container
exec -> execute
-it -> intaractive terminal
bash -> inside the terminal using bash script
/var/lib/docker -> docker home repository
Dockerfile -> instructions to build custom images using dockerfile
instructions:
FROM -> refers to base os of the image


