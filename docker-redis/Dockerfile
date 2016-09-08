#
# Redis Dockerfile
#
# https://github.com/dockerfile/redis
#

# Pull base image.
FROM centos:sshd

RUN yum install -y wget gcc

RUN echo 512 > /proc/sys/net/core/somaxconn
RUN sysctl vm.overcommit_memory=1
RUN echo never > /sys/kernel/mm/transparent_hugepage/enabled

# Install Redis.
RUN \
  cd /tmp && \
  wget http://download.redis.io/redis-stable.tar.gz && \
  tar xvzf redis-stable.tar.gz && \
  cd redis-stable && \
  make && \
  make install && \
  cp -f src/redis-sentinel /usr/local/bin && \
  mkdir -p /etc/redis && \
  cp -f *.conf /etc/redis && \
  rm -rf /tmp/redis-stable* && \
  sed -i 's/^\(bind .*\)$/# \1/' /etc/redis/redis.conf && \
  sed -i 's/^\(daemonize .*\)$/# \1/' /etc/redis/redis.conf && \
  sed -i 's/^\(dir .*\)$/# \1\ndir \/data/' /etc/redis/redis.conf && \
  sed -i 's/^\(logfile .*\)$/# \1/' /etc/redis/redis.conf && \
  sed -i 's/protected-mode.*yes.*/protected-mode no/' /etc/redis/redis.conf
# Define mountable directories.
VOLUME ["/data"]

# Define working directory.
WORKDIR /data

# Define default command.
CMD \
    ip addr ls eth0 | \
    awk '{print $2}' | \
    egrep -o '([0-9]+\.){3}[0-9]+';/usr/sbin/sshd -D | \
	  redis-server /etc/redis/redis.conf

# Expose ports.
EXPOSE 6379 22
