#installing docker 
https://docs.docker.com/engine/install/

#installing git bash for windows users
https://git-scm.com/downloads


- history of LXC  and prior 

- microservices
  * simplicity 
  * scalability
  * upgrade
  * downtime
  * simplifiying debugging  

- containers benefits 
  * development life cycle 
    * fast deplyoments in local/lab/pre/prod
    * repitable enviroments 
    * stateless apps 
  * tracking exact version and making it reproducible 
  * pets vs cattle 
- 12 factor app 



- demo 
#intro
docker run buysybox echo hello world
docker run -it ubuntu
figlet hello 
apt update 
apt install figlet 
figlet hello 

#outputs
docker run  jpetazzo/clock
docker run -d jpetazzo/clock
docker logs {ID_CONTAINER}
docker logs {ID_CONTAINER} -f | less 
docker ps 
docker stop 
##unix kill signal 10s timeout 
docker kill 

#attach dettach
docker run -it ubuntu
top
##CTL+p+q
docket attach {ID}
##explaing CTL+C



#Layers and tagging 
docker run -it ubuntu:12.04
cat /etc/os-release
##layer
docker run -it ubuntu
figlet hello 
apt update 
apt install figlet 
docker diff {ID_CONTAINER}
docker commit {ID_CONTAINER}
docker images 
docker run -it {ID_IMAGE}
history
figlet
docker images
docker tag --help
docker tag {ID_IMAGE} {NAME_IMAGE}
docker run my_figlet  figlet message
##dockefile
cat <<EOL > Dockerfile
FROM ubuntu 
RUN apt update
RUN apt install figlet
EOL
docker build . 
docker images
docker run {ID_IMAGE}  figlet Dockerfile
#build cache and taggind
docker build -t {TAG_NAME}
docker images 


docker container run --rm --name my_nginx -p 8080:80 nginx
docker container attach my_nginx


