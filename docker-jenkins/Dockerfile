# docker jenkins
#
# VERSION              1.0

FROM centos:tomcat7

MAINTAINER hoperuin<wf1337@gmail.com>

COPY /jenkins.war /usr/local/tomcat7u69/webapps/


EXPOSE 22 8080


CMD \
    ip addr ls eth0 | \
    awk '{print $2}' | \
    egrep -o '([0-9]+\.){3}[0-9]+';/usr/sbin/sshd -D| \
    /bin/sh /usr/local/tomcat7u69/bin/startup.sh