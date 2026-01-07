## image and container:
* image = bare minimum os + system packages + application runtime + app code + dependencies
* container = if we run the image we get container, container is running instance
## docker commands:
* docker pull -> pull the image from docker repository
* docker images -> show all images
* docker rmi <image_name or image_id> -> remove images 
* docker ps -> all running containers
* docker ps -a -> all containers
* docker start <image_name or image_id> -> start the container
* docker stop <image_name or image_id> -> stop the container
* docker rm <image_name or image_id> -> delete stopped container
* docker rm -f <image_name or image-id> -> delete running container
* docker rm -f `docker ps -a -q` -> remove all containers at a time
* docker rmi -f `docker images -a -q` -> remove all images at a time
* docker inspect <cont-id or image-id> -> info about container or image
* docker login -u <user-name> and password -> login for docker repo in your ec2 instance
* docker build -t <image-name>:<tag-name> . -> . refers current directory
* docker build --no-cache --progress=plain -t <image-name> -> view every step of installation
* docker run -d <image-name>:<tag-name> --no-trunc -> showing the complete container
* docker tag <oldtag-name> <newtag-name>
* docker push <url>/<account-name>/<image-name> -> push image into docker repository
* docker run -d --name <cont-name> -p <host-port:cont-port> <image-name> -> pull + start + run the container
* -d -> detached mode 
* -p -> port
* --name -> name of the container
* docker exec -it <cont-name or cont-id> bash -> goto inside container
* exec -> execute
* -it -> intaractive terminal
* bash -> inside the terminal using bash script
* /var/lib/docker -> docker home repository
* Dockerfile -> instructions to build custom images using dockerfile
## instructions:
* FROM -> refers to base os of the image
* RUN -> configure and install the packages ex dnf install nginx -y
* CMD -> start the image
*     -> given command overridden
## RUN VS CMD
* RUN : execute the time of image building
: multiple run instructions
* CMD : execute the time of container starting
*     : single cmd instructions if we give multiple last one is consider
*     : given command overridden
* docker run <image-name:version> -> without giving anything default value taken
* docker run <image-name:version> ping www.facebook.com -> overright the given value
* docker images -f "label=trainer=sivakumar" filter the images
# ENV -> environment variables
* docker run -d -e COURSE=DEVOPS run:v1 -> overwrite the env variables
* ENTRYPOINT -> ENTRYPOINT not overridden the command it's append the command
* docker run <image_name:version> ping www.facebook.com -> it's append not overridden
# CMD VS ENTRYPOINT
# CMD
* execute the time of container starting
* if pass command while running the container then override
* command can be used supply args to entrypoint
# ENTRYPOINT
* if pass command while running the container then it is not overridden.
* it is append and throughs some error
* docker run <image_name:version> www.google.com -> it is append (ping already given in docker file not required in execution/run time )
# USER
* when you add the user into dockerfile then you did't give direct root access to the container,you enter the container with created user.
# ARG
* arg is the first instruction of some exceptional case, it will supply version of the image, after FROM instruction we cannot run the ARG variable
* docker build -t <image_name:version> --build-arg VESION=9 .
* arg can't run inside the image
# ENV VS ARG
* ENV supply the key,value pairs of the images 
* ARG supply the version of the image
* ARG cannot run inside the container
# ONBUILD
* this instruction is we put condition for someone is using my image
* ex: index.html is mandatory for every frontend webpage we set this condition





