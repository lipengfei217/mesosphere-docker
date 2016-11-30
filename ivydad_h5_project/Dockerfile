# DOCKER-VERSION 1.0.1
# VERSION        0.5
# SOURCE         https://github.com/jplock/docker-zookeeper

FROM hub.c.163.com/lipengfei217/sshd:0.1 

MAINTAINER Pengfei Lee <pengfei.li@ivydad.com>

RUN yum update -y && rpm -Uvh http://nginx.org/packages/centos/7/noarch/RPMS/nginx-release-centos-7-0.el7.ngx.noarch.rpm && yum install -y nginx


RUN mkdir -p /opt/nginx/html

#RUN /sbin/init

ADD ivydad.tar.gz /opt/nginx/html

#ADD ./run.sh /opt/run.sh

#RUN chmod 777 /opt/run.sh

EXPOSE 80

VOLUME ["/ect/nginx/conf.d","/var/log/nginx"]

WORKDIR /opt/nginx/html/ivydad

CMD ["nginx", "-g", "daemon off;"]

