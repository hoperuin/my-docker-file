# docker nexus
#
# VERSION              1.0

FROM centos:sshd-jdk

MAINTAINER hoperuin<wf1337@gmail.com>

ENV JAVA_HOME /usr/java/jdk1.7.0_79
ENV RUN_AS_USER nexus

RUN useradd nexus

ADD /nexus-2.13.0-01-bundle.tar.gz /
RUN mv /nexus-2.13.0-01 /usr/local/nexus
RUN mv /sonatype-work /usr/local/sonatype-work

RUN chmod -R 775 /usr/local/nexus
RUN chown -R nexus:nexus /usr/local/nexus
RUN chown -R -v nexus:nexus /usr/local/sonatype-work

VOLUME /usr/local/sonatype-work

EXPOSE 8081 22
CMD \
    ip addr ls eth0 | \
    awk '{print $2}' | \
    egrep -o '([0-9]+\.){3}[0-9]+';/usr/sbin/sshd -D | \ 
    su - nexus -c "/usr/local/nexus/bin/nexus start"
