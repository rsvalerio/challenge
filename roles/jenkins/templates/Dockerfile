FROM jenkins
# if we want to install via apt

USER root

RUN apt-get update && apt-get install -y apt-transport-https ca-certificates

RUN apt-key adv --keyserver hkp://p80.pool.sks-keyservers.net:80 --recv-keys 58118E89F3A912897C070ADBF76221572C52609D

RUN echo "deb https://apt.dockerproject.org/repo ubuntu-trusty main" > /etc/apt/sources.list.d/docker.list

RUN apt-get update

#RUN apt-get install -y linux-image-extra-$(uname -r) linux-image-extra-virtual

RUN apt-get install -y docker-engine

RUN service docker start

USER jenkins # drop back to the regular jenkins user - good practice