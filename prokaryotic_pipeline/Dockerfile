################################################################# 
# Dockerfile
#
# Version: 1
# Software: spades
# Software Version: 3.6.0
# Description: Tools (written in C using htslib) for manipulating next-generation sequencing data
# Website: http://bioinf.spbau.ru/spades
# Tags: Genomics
# Provides: spades 3.11.1
# Base Image: biodckr/biodocker
# Build Cmd: docker build --rm -t biodckrdev/spades 3.6.0/.
# Pull Cmd: docker pull biodckrdev/spades
# Run Cmd: docker run --rm -it biodckrdev/spades <options> <files>
#################################################################

# Set the base image to Ubuntu 
FROM ubuntu:17.10

################## BEGIN INSTALLATION ###################### 

ENV ZIP=SPAdes-3.11.1-Linux.tar.gz 
ENV URL=https:http://cab.spbu.ru/files/release3.11.1
ENV FOLDER=SPAdes-3.11.1-Linux 
ENV DST=/home/docker/bin 

RUN wget $URL/$ZIP -O $DST/$ZIP && \ 
	tar xvf $DST/$ZIP -C $DST && \ 
	rm $DST/$ZIP && \ 
	cd $DST/$FOLDER && \ 
	mv $DST/$FOLDER/bin/* /home/biodocker/bin && \
	rm -rf $DST/$FOLDER

# CHANGE WORKDIR TO /DATA
WORKDIR /home/docker

# DEFINE DEFAULT COMMAND
CMD ["bwa-spades"]

##################### INSTALLATION END #####################

# File Author / Maintainer
MAINTAINER Saulo Alves Aflitos <sauloal@gmail.com>
