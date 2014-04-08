FROM bradrydzewski/base

USER root

RUN echo deb http://get.docker.io/ubuntu docker main > /etc/apt/sources.list.d/docker.list
RUN apt-get -y update
RUN apt-get -y install lxc-docker
