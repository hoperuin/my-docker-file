# docker wiki
#
# VERSION              1.0

FROM centos:jdk8

MAINTAINER hoperuin<wf1337@gmail.com>

ADD /atlassian-confluence-5.9.7.tar.gz /
RUN mv /atlassian-confluence-5.9.7 /usr/local/atlassian-confluence-5.9.7
RUN chmod 777 /usr/local/atlassian-confluence-5.9.7/bin/*.sh

RUN mkdir -p /var/confluence/data

COPY /atlassian-extras-decoder-v2-3.2.jar /usr/local/atlassian-confluence-5.9.7/confluence/WEB-INF/lib
COPY /mysql-connector-java-5.1.36.jar /usr/local/atlassian-confluence-5.9.7/confluence/WEB-INF/lib
COPY /Confluence-5.9.7-language-pack-zh_CN.jar /usr/local/atlassian-confluence-5.9.7/confluence/WEB-INF/lib

EXPOSE 8090 22
CMD \
    ip addr ls eth0 | \
    awk '{print $2}' | \
    egrep -o '([0-9]+\.){3}[0-9]+';/usr/sbin/sshd -D | \
    /bin/sh /usr/local/atlassian-confluence-5.9.7/bin/start-confluence.sh
