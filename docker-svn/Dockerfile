# docker svn
#
# VERSION              1.0

FROM centos:tomcat7

MAINTAINER hoperuin<wf1337@gmail.com>

#ADD /svnadmin.zip /

COPY /svnadmin.war /usr/local/tomcat7u69/webapps/

VOLUME /data
EXPOSE 3690

RUN yum install subversion -y
RUN mkdir -p /var/svn/repo
RUN svnadmin create /var/svn/repo

CMD ["svnserve", "--foreground", "-d", "-r", "/var/svn/repo"]
