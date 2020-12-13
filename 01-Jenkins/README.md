# Jenkins Installation & Configuration


### Change current user privilege to root
```
sudo su - 
```

### Install Java Default-JDK and Maven Package Builder
```
apt-get install default-jdk -y
java -version

apt-get install maven -y 
mvn --version
```

### Download Jenkins
```
  wget https://get.jenkins.io/war-stable/2.249.2/jenkins.war
  mv jenkins.war /root/
```

### Run Jenkins on port '9090'
```
nohup  java -jar /root/jenkins.war --httpPort=9090 > output.txt & 
```

### Access the Jenkins via Web Browser and Complete the Setup process 

```
http://<hostname>:9090
```

### Read the initial Admin Password
```
 cat /root/.jenkins/secrets/initialAdminPassword
```