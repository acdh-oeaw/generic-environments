FROM ubuntu:20.04
MAINTAINER Hannes Pirker <hannes.pirker@oeaw.ac.at>

# copy to both $HOME and /root (which is the $HOME for root
COPY _bashrc_for_Docker $HOME/.bashrc
COPY _bashrc_for_Docker /root/.bashrc
# COPY _bashrc_for_Docker /.bashrc

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
       cpanminus \
       apt-utils \
       xml-twig-tools \
       rsync \
       locales \
       postgresql-client   \
       libjudy-dev   \
       wget  \
       pcregrep   \
       rename \
       apache2-utils \
       pwgen \
       lsof \
       zip \
       curl \
       diffutils  \
       w3c-sgml-lib \
       tree \
	  xsltproc \
	  p7zip-full \
	  p7zip-rar \
	  rar \
	  unrar

RUN apt-get -y update && \
     apt-get install -y \
		xz-utils \
		liblzma-dev \
		locate \
		tzdata

RUN rm -f /etc/localtime && \
    ln -s /usr/share/zoneinfo/Europe/Vienna /etc/localtime && \
    dpkg-reconfigure --frontend noninteractive tzdata

# when installing xsltproc asks for region and country 
# will this work ? -> for now: install manually! 
## => the problem was with tzdata - this should be remedied by now! 

#RUN apt-get -y update && \
#	apt-get install -y xsltproc


# set up utf-8 locale (defaults in offical centos/ubuntu images are POSIX)
RUN locale-gen en_US.UTF-8
ENV LANG en_US.UTF-8
ENV LANGUAGE en_US:en

## should be python 2.7 : needed for rftagger 
RUN apt-get -y install python2


### additions
## 2018-04 added psql - client for administrating tokeneditor
## 2018-04 add libjudy for docker
## 2019-09 rename : on Ubuntu this installs Larry Wall's perl-version!

WORKDIR /home/user

CMD ["bash", "-c", "while : ; do sleep 600 ;done"]
