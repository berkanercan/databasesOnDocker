# Databases On Docker
This repository is a quick start guide for running various databases on docker

1. Docker Basics:
   - List all containers  
     `docker ps -a`
   - List all images  
     `docker images -a`
   - Remove all exited containers  
     `docker rm $(docker ps -a -f status=exited -q)`
   - Remove all images  
     `docker rmi $(docker images -a -q)`
   - Execute an interactive bash shell on docker container  
     `docker exec -it <container_name> bash`
   - Execute a command a command as the root user  
     `docker exec -u 0 <container> <command>`
   - Set environment variables  
     `docker exec -e var='value' <container> <command>`
   
   


1. PostgreSql


