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
  
   `docker run -d \`  
    `--name postgres-db \`  
    `-p 5432:5432 \`  
    `-e POSTGRES_USER=berkan \`  
    `-e POSTGRES_PASSWORD=passpass \`  
    `-e POSTGRES_DB=books \`  
    `-v pgdata:/var/lib/postgresql/data \`  
    `postgres`  
    
Alternatively, run docker-compose up on the path, where docker-compose.yaml exists. Connecting to the posgres container to execute queries without any tool  

`docker exec -it <container_id> psql -U <user_name> <database_name>`

If an sql file needs to be executed, run the following commands  
`docker cp ./localfile.sql containername:/container/path/file.sql`  
`docker exec -u postgresuser containername psql dbname postgresuser -f /container/path/file.sql`
