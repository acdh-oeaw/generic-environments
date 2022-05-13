FROM ubuntu:20.04
MAINTAINER Hannes Pirker <hannes.pirker@oeaw.ac.at>

# copy to both $HOME and /root (which is the $HOME for root
COPY _bashrc_for_Docker $HOME/.bashrc
COPY _bashrc_for_Docker /root/.bashrc

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get -y update && \
apt-get install -y \
       less  \
       unzip     \
       parallel  \
       time \
       vim       \ 
       htop      \ 
       build-essential  \
       apt-utils \
       locales \
       tzdata \
       supervisor 

RUN rm -f /etc/localtime && \
    ln -s /usr/share/zoneinfo/Europe/Vienna /etc/localtime && \
    dpkg-reconfigure --frontend noninteractive tzdata

# set up utf-8 locale (defaults in offical centos/ubuntu images are POSIX)
RUN locale-gen en_US.UTF-8
ENV LANG en_US.UTF-8
ENV LANGUAGE en_US:en

ENV JAVA_HOME /usr/lib/jvm/java-8-openjdk-amd64

RUN apt update && \
apt-get install -y  openjdk-8-jdk ant && \
apt-get install -y  xsltproc

WORKDIR /home/user

CMD ["bash", "-c", "while : ; do sleep 600 ;done"]

