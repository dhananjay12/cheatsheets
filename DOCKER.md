## DOCKER CHEAT SHEET

### Login

```
docker login <docker-host defaults to dockerhub>
```
or

```
docker login -u <username> <docker-host defaults to dockerhub>
```
or
```
docker login -u <username> -p <password> <docker-host defaults to dockerhub>
```

### Build

```
docker build -t <image-name>:<tag> .
```
If docker file is not `Dockerfile`:
```
docker build -t <image-name>:<tag> -f .\Dockerfile-tomcat .
```
If pusing to a custom docker repository:
```
docker build -t <docker-host>/<username/project>/<image-name>:<tag> -f .\Dockerfile-tomcat .
```

### Retag

```
docekr tag <old-image>:<old-tag> <old/new-image>:<new-tag>
```

### Remove

Remove all containers:
```
docker rm -f $(docker ps -a -q)
```
Remove all images with a pattern:
```
docker rmi -f $(docker images -a | grep "pattern" | awk '{print $3}')
```

Check and remove unused network:
```
docker network ls
docker network rm <id>
```
or remove all unused netowrk
```
docker network prune
```

### Extract docker Images (useful if you cannot exec into it)

```
id=$(docker create image-name)
docker cp $id:. - > local-tar-file
docker rm -v $id
```
The dot in the `$id:.` tells that you want to extract from the root. Use any other path for something specific
