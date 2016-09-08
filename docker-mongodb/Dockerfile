# docker mongodb
#
# VERSION              1.0

FROM centos:sshd

MAINTAINER hoperuin<wf1337@gmail.com>

ADD /mongodb-linux-x86_64-3.2.8.tgz /

RUN mv /mongodb-linux-x86_64-3.2.8 /usr/local/mongodb
RUN mkdir /usr/local/mongodb/logs
RUN mkdir /usr/local/mongodb/db
RUN mkdir /usr/local/mongodb/conf

COPY /mongodb.conf /usr/local/mongodb/conf/

EXPOSE 22 27018
CMD \
    ip addr ls eth0 | \
    awk '{print $2}' | \
    egrep -o '([0-9]+\.){3}[0-9]+';/usr/sbin/sshd -D | \
    /usr/local/mongodb/bin/mongod --config /usr/local/mongodb/conf/mongodb.conf
