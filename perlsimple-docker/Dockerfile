FROM ghcr.io/acdh-oeaw/generic-environments/shell:latest
MAINTAINER Hannes Pirker <hannes.pirker@oeaw.ac.at>

## minimal "perl" environment for testing

RUN apt-get -y update && \
apt-get install -y cpanminus && \
cpanm Data::Dumper && \
cpanm Date::Calc && \
cpanm RDF::Simple


## remove user 'user' before injecting it agin
#RUN sed -i '/^user:\w/d' /etc/shadow
#RUN userdel user 
## User named user does not exist if image is build without docker-tool 

#@INJECT_USER@

WORKDIR /home/user

CMD ["bash", "-c", "while : ; do sleep 600 ;done"]

# CMD ["bash", "--init-file", "/home/user/_bashrc_for_Docker", "-c", "-i", "while : ; do sleep 600 ;done"]
