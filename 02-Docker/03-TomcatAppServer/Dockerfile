FROM ubuntu:16.04

RUN apt-get update && apt-get install -y python openssh-client openssh-server && apt-get clean

RUN service ssh restart

EXPOSE 80
EXPOSE 8080
