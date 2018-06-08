FROM centos:7
MAINTAINER Luke Xuan <aoser97@gmail.com>

RUN yum update -y && \
  cd /tmp && \
  yum install make gcc-c++ gcc git wget which patch unzip m4 ocaml -y && \
  curl -L https://raw.github.com/ocaml/opam/master/shell/opam_installer.sh | sh -s /usr/local/bin && \
  /usr/local/bin/opam init -y && \
  eval `opam config env` && \
  opam install coq menhir -y && \
  git clone https://github.com/AbsInt/CompCert && \
  cd CompCert && \
  ./configure -clightgen x86_32-linux && \
  make && \
  make install && \
  yum install glibc-devel.i686 -y && \
  yum remove make gcc-c++ git wget which patch unzip m4 -y && \
  yum -y clean all && rm -rf /var/cache/yum

WORKDIR /shared
CMD /bin/bash
