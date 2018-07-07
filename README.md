# docker-cli

#1. Build docker image
docker build -t <tag_name> .

#2. Run docker image
docker run image_name:tag_name

#3. List up images
docker images

#4. Remove docker image
//Remove single image
docker rmi <docker_image_id>
 
//Remove single image with force mode -f
docker rmi -f <docker_image_id>
 
//Remove all images
docker rmi $(docker images -a -q)
 
//Remove all images with force mode -f
docker rmi -f $(docker images -a -q)

#5. List up docker containers
docker container ls -l

#6. Stop docker container
//Stop single container
docker stop <container_id>
 
//Stop all container
docker stop $(docker ps -a -q)

#7. Remove docker container
//Remove single container
docker rm <container_id>
 
//Remove all container with force mode -f
docker rm -f $(docker ps -a -q)

#8. Using command in docker container
//View running containers
docker ps
 
//The format of executing command shell in docker
docker container exec <container_id> <shell_command>
 
 
//Example-1: List up resource in container
docker container exec 0c61b918d40e ls -l

#9. Copy file from container to localhost system file
//The format of copy file from running container to localhost system file
docker cp <container_id>:/<source_container> /<localhost_system_file>
 
//Example
docker cp 0c61b918d40e:/usr/src/app /home/data_container

#10. Copy file from localhost system file to container
//The format of copy file from local system fie to running container
docker cp /<destination_host> <container_id>:/<source_container>
 
//Example
docker cp /home/data.txt 0c61b918d40e:/usr/src/app/
