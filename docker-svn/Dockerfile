# docker svn
#
# VERSION              1.0

FROM centos:tomcat7

MAINTAINER hoperuin<wf1337@gmail.com>

COPY /svnadmin /usr/local/tomcat7u69/webapps/svnadmin


EXPOSE 3690 22 8080

RUN yum install -y subversion

RUN mkdir -p /var/svn/repo
RUN svnadmin create /var/svn/repo

CMD ip addr ls eth0 | awk '{print $2}' | egrep -o '([0-9]+\.){3}[0-9]+';/usr/sbin/sshd -D|svnserve --foreground -d -r /var/svn |/bin/sh /usr/local/tomcat7u69/bin/startup.sh
