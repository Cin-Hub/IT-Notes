# Docker
- [Official homepage](https://www.docker.com/)
- [Docker hub](https://hub.docker.com/)
- [Docker Engine installation guide](https://docs.docker.com/engine/install/)
- [Docker CLI commands](https://docs.docker.com/engine/reference/commandline/docker)
- [Docker Compose CLI commands](https://docs.docker.com/compose/reference/)
- [Compose file version 3 reference](https://docs.docker.com/compose/compose-file/compose-file-v3/)

# CLI commands

## Version

```shell
docker version
```

</br>

## List all containers  
```shell
docker ps -a
```  

</br>

## Display a live stream of container resource usage  
```shell
docker stats
```  

</br>

## Start one or more stopped containers  
```shell
docker start <CONTAINER_NAME_or_ID>
```

</br>

## Stop one or more running containers  
```shell
docker stop <CONTAINER_NAME_or_ID>
```  

</br>

Stop all running containers
```shell
docker stop $(docker ps -a -q)
```  

</br>

## List all volumes
```shell
docker volume ls
```

</br>

## Remove all unused local volumes

```shell
docker volume prune
```

</br>

## Remove specific unused volume  
```shell
docker volume rm <VOLUME_NAME_or_ID>
```  

</br>

## List images  
```shell
docker images -a
```  

</br>

## Remove images  
```shell
docker rmi <IMAGE_NAME_or_ID> <IMAGE_NAME_or_ID>.....
```  

</br>

## Remove all unused or dangling images  
```shell
docker image prune -a -f
```  

</br>

## rm - Remove container  
[docker rm - online manual](https://docs.docker.com/engine/reference/commandline/rm/)  
```shell
docker rm <CONTAINER_NAME_or_ID>
```  
```shell
docker rm -v <CONTAINER_NAME_or_ID>
```  

| Option | Description                                            |
|:------:| ------------------------------------------------------ |
|   -v   | Remove anonymous volumes associated with the container | 

</br>

## Search the Docker Hub for images  
```shell
docker search <TERM>
```

</br>

## Pull an image or a repository  
```shell
docker pull <IMAGENAME[:TAG|@DIGEST]>
```  

</br>

## Run a command in a new container  
```shell
docker run [OPTIONS] IMAGE [COMMAND] [ARG...]
```  

</br>

## List port mappings for the container  
```shell
docker container port <CONTAINER_NAME_or_ID>
```  

</br>

## Open bash shell in Container  
```shell
docker exec -it <CONTAINER_NAME_or_ID> /bin/bash
```

</br>

## Execute command inside container  
```shell
docker exec -it <CONTAINER_NAME_or_ID> <COMMAND>
```

Example: `docker exec -it wireguard wg`

-------

</br>


