FROM centos:latest

MAINTAINER Adam E. Taylor <Adam.Taylor@Logimehods.com>
ADD https://mirror.its.sfu.ca/mirror/CentOS-Third-Party/NSG/common/x86_64/jdk-7u80-linux-x64.rpm /tmp/
RUN rpm -Uvh /tmp/jdk-7u80-linux-x64.rpm
RUN alternatives --install /usr/bin/java java /opt/jdk1.7.0_80/bin/java 2
RUN mkdir /opt/java
RUN ln -s /usr/java/jdk1.7.0_80 /opt/java/jdk1.7
RUN yum -y install bc wget unzip openjdk-7-jre curl
RUN groupadd -r tibgrp -g 433 && \
	useradd -u 431 -r -m -g tibgrp -d /home/tibusr -s /bin/bash -c "TIBCO Docker image user" tibusr && \
	chown -R tibusr:tibgrp /home/tibusr && \
	mkdir /opt/tibco && \
	chown -R tibusr:tibgrp /opt/tibco && \
	mkdir /tmp/install && \
	chown -R tibusr:tibgrp /tmp/install
	
USER tibusr	