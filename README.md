# spring-boot-docker
Getting Started with Docker using Spring Boot

## Maven Build the code :
  mvn install
## Run the Spring Boot application :
  java -jar target/spring-boot-docker-0.1.0.jar
## Verification :
  http://localhost:8080
## Docker

1. [Docker Build](https://docs.docker.com/engine/reference/commandline/build/#tag-an-image--t)
  
`docker build --compress --force-rm -t {Docker_Hub_Username}/{Docker_Hub_RepoName}:{Tag} .`
  
**Example** : `docker build -t vinodjayachandran/spring-boot-docker:1.0 . `

2. On successful execution of above command, it will create a docker image in your local which you can verify with the below command. It will list the set of images on your machine.

`docker images`

3. [Run Docker](https://docs.docker.com/engine/reference/commandline/run/) image locally on a container with a name for the container.

**Example** : `docker run -p 8080:8080 -t vinodjayachandran/spring-boot-docker:1.0 --name=MyTestContainer`

4. Verify if the container is up. Your image will be listed with status as up along with container id. Without the option **--all** it will list only running containers

**Example**

`$ docker container ls --all`

5. Stop/Start the container with container id retrieved from Step 4. After stopping the container you verify again with commands from Step 4

**Example** 

`docker stop {CONTAINER ID}`

`docker start {CONTAINER ID}`

6. Rename container

`docker rename {EXISTING CONTAINER NAME OR ID} NEW_NAME`

7. Delete container

`docker rm {EXISTING CONTAINER NAME OR ID}`

8. [Remove one or more images](https://docs.docker.com/engine/reference/commandline/rmi/)

9. Push the docker image to docker hub/registry

   [Login to Docker Hub/Registry](https://docs.docker.com/engine/reference/commandline/login/)

           $ docker login --username={userName} --password={pwd}
   Providing password directly on CLI isn't recommended. From a security perspective, we can have the password stored in a file and [provided at run time through stdin](https://docs.docker.com/engine/reference/commandline/login/#provide-a-password-using-stdin)

      [Push the image to docker hub](https://docs.docker.com/engine/reference/commandline/push/)


10. [Configure automated builds from GitHub and BitBucket](https://docs.docker.com/docker-hub/builds/link-source/)

