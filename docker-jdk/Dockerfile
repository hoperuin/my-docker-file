# docker jdk 1.7.79
#
# VERSION              1.0

FROM centos:sshd

MAINTAINER hoperuin<wf1337@gmail.com>

ADD ./jdk-7u79-linux-x64.tar.gz /

RUN mkdir /usr/java/

RUN mv /jdk1.7.0_79 /usr/java/

ENV JAVA_HOME /usr/java/jdk1.7.0_79
ENV JRE_HOME /usr/java/jdk1.7.0_79/jre

RUN echo 'export JAVA_HOME=/usr/java/jdk1.7.0_79' >> /etc/profile
RUN echo 'export JRE_HOME=$JAVA_HOME/jre' >> /etc/profile
RUN echo 'export PATH=$JAVA_HOME/bin:$JRE_HOME/bin:$PATH' >> /etc/profile
RUN echo 'export CLASSPATH=.:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar:$JRE_HOME/lib' >> /etc/profile
RUN source /etc/profile
