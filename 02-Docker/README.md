# Docker Setup

### Install docker using the file under 00-Setup
```
cd 02-Docker/00-Setup
docker-install.sh
docker-compose.sh
```

### Spin up the JFrog factory docker container using docker-compose
```
cd 02-Docker/01-JFrog-Artifact
docker-compose up -d
```

### Spin up the SonarQube docker container using docker-compose
```
cd 02-Docker/02-SonarQube
docker-compose up -d
```

### Spin up two Ubuntu containers
```
cd 02-Docker/03-TomcatAppServer
docker build -t ubuntu-base:v1 .
docker run -itd --name app-worker1 -p 30001:80 -p 38081:8080 ubuntu-base:v1
docker run -itd --name app-worker2 -p 30002:80 -p 38082:8080 ubuntu-base:v1
```

### In the Worder nodes set root password as "redhat" using the following command
```
docker attach <worker node name>
passwd
```

### Add the hosts by remoting into the worker nodes.
```
ssh root@<worker ip address>
```

### Get the ip address of the worker nodes and add to the ansible inventory
```
docker inspect <worker-container name> | grep -i ipaddress
```