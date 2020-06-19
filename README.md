# Databases On Docker
This repository is a quick start guide for running various databases on docker

## Docker Basics:
   - List all containers  
     `docker ps -a`
   - List all images  
     `docker images -a`
   - Run the command in the background  
      `docker -d <command>`
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

## PostgreSql  
   `docker pull postgres`
   
   Initialize the docker with a user, password and db name.
   ```
   docker run -d \
    --name postgres-db \
    -p 5432:5432 \
    -e POSTGRES_USER=berkan \
    -e POSTGRES_PASSWORD=passpass \
    -e POSTGRES_DB=books \
    -v pgdata:/var/lib/postgresql/data \
    postgres
    ```
   
   


