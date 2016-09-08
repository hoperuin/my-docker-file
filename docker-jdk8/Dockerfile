# docker jdk 1.8.102
#
# VERSION              1.0

FROM centos:sshd

MAINTAINER hoperuin<wf1337@gmail.com>

ADD ./jdk-8u102-linux-x64.tar.gz /

RUN mkdir /usr/java/

RUN mv /jdk1.8.0_102 /usr/java/

ENV JAVA_HOME /usr/java/jdk1.8.0_102
ENV JRE_HOME /usr/java/jdk1.8.0_102/jre

RUN echo 'export JAVA_HOME=/usr/java/jdk1.8.0_102' >> /etc/profile
RUN echo 'export JRE_HOME=$JAVA_HOME/jre' >> /etc/profile
RUN echo 'export PATH=$JAVA_HOME/bin:$JRE_HOME/bin:$PATH' >> /etc/profile
RUN echo 'export CLASSPATH=.:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar:$JRE_HOME/lib' >> /etc/profile
RUN source /etc/profile
