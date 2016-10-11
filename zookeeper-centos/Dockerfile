# DOCKER-VERSION 1.0.1
# VERSION        0.5
# SOURCE         https://github.com/jplock/docker-zookeeper

FROM hub.c.163.com/public/centos:7.2.1511
MAINTAINER Pengfei Li <lipengfei217@163.com>

RUN yum -y update && yum install -y java-1.7.0-openjdk-headless.x86_64 

RUN ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime

RUN echo "Asia/Shanghai" >> /etc/timezone


RUN wget -O - http://apache.mirrors.pair.com/zookeeper/zookeeper-3.4.6/zookeeper-3.4.6.tar.gz | tar -xzf - -C /opt \
    && mv /opt/zookeeper-3.4.6 /opt/zookeeper \
    && cp /opt/zookeeper/conf/zoo_sample.cfg /opt/zookeeper/conf/zoo.cfg \
    && mkdir -p /tmp/zookeeper

ENV JAVA_HOME /usr/lib/jvm/java-1.7.0-openjdk-1.7.0.111-2.6.7.2.el7_2.x86_64/jre 

ADD ./run.sh /opt/run.sh
RUN chmod 777 /opt/run.sh

EXPOSE 2181 2888 3888

WORKDIR /opt/zookeeper

VOLUME ["/opt/zookeeper/conf", "/tmp/zookeeper"]

CMD ["/opt/run.sh"]
