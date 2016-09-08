# docker tomcat
#
# VERSION              1.0

FROM centos:sshd-jdk

MAINTAINER hoperuin<wf1337@gmail.com>


ADD /apache-tomcat-7.0.69.zip /

RUN mv /apache-tomcat-7.0.69 /usr/local/tomcat7u69

EXPOSE 8080
CMD /bin/sh /usr/local/tomcat7u69/bin/startup.sh
