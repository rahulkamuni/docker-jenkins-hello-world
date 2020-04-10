
#### Steps

##### Clone source code from git
```
$  git clone https://github.com/rahulkamuni/docker_jenkins_hello_world.git .
```

##### Build Docker image
```
$ docker build -f Dockerfile -t docker_jenkins_hello_world .
```
This will first run maven build to create jar package and then build docker jenkins hello world image using built jar package.

>Note:if you run this command for first time it will take some time in order to download base image from [DockerHub](https://hub.docker.com/)

##### Run Docker Container
```
$ docker run -p 8080:8080 -it --rm 593946c7a8cb ----> (ImageId)
```

##### Test application

```
$ docker-machine ip (http://192.168.99.100:8080/)
```

the respone should be:
```
Welcome to Project Rahul Kamuni
```

#####  Stop Docker Container:
```
docker stop `docker container ls | grep "docker-jenkins-hello-world:*" | awk '{ print $1 }'`
```

## Run with docker-compose 

Build and start the container by running 

```
$ docker-compose up -d 
```

##### Test application with command

```
$ docker-machine ip (http://192.168.99.100:8080/)
```

the respone should be:
```
Welcome to Project Rahul Kamuni
```

##### Stop Docker Container:
```
docker-compose down
```
