## DOCKER CHEAT SHEET

### Login

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
If docker file is not `Dockerfile`
```
docker build -t <image-name>:<tag> -f .\Dockerfile-tomcat .
```
If pusing to a custom docker repository
```
docker build -t <docker-host>/<username/project>/<image-name>:<tag> -f .\Dockerfile-tomcat .
```

### Retag

```
docekr tag <old-image>:<old-tag> <old/new-image>:<new-tag>
```

### Remove

Remove all containers
```
docker rm -f $(docker ps -a -q)
```
