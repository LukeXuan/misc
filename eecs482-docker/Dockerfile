FROM centos:7
MAINTAINER Luke Xuan <aoser97@gmail.com>

RUN yum update -y && \
  yum install make cmake gcc gcc-c++ tmux -y && \
  yum -y clean all && rm -rf /var/cache/yum

WORKDIR /shared
CMD /bin/bash
