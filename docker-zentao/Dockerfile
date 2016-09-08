# zentao 8.2.5
#
# VERSION              1.0

FROM centos:sshd

MAINTAINER hoperuin<wf1337@gmail.com>

ADD http://dl.cnezsoft.com/zentao/8.2.5/ZenTaoPMS.8.2.5.zbox_64.tar.gz /
RUN tar -zxvf /ZenTaoPMS.8.2.5.zbox_64.tar.gz -C /opt
RUN chmod -R 775 /opt/zbox

EXPOSE 80 3306 22

CMD \
   ip addr ls eth0 | awk '{print $2}' |\
   egrep -o '([0-9]+\.){3}[0-9]+';/usr/sbin/sshd -D |\
   /opt/zbox/zbox start
