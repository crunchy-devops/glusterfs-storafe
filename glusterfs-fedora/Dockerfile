FROM fedora

RUN set -eux && \
    yum -y update && \
    mkdir /gluster && \
    cd /gluster && \
    yum -y install wget && \
    wget https://github.com/gluster/glusterfs/archive/refs/tags/v10.4.tar.gz && \
    tar -zxvf v10.4.tar.gz && \
    yum install -y  @"Development Tools" && \
    cd /gluster/glusterfs-10.4 && \
    yum -y install autoconf automake libtool && \
    ./autogen.sh && \
     yum  -y install rpcgen gperftools flex bison openssl-devel openssl libuuid-devel libacl-devel python3-devel \
             openssl-devel libxml2-devel libtirpc-devel liburing-devel userspace-rcu-devel && \
    ./configure && \
    make && \
    make install

RUN mkdir -p /opt/data/brick1

VOLUME ['/opt/data/brick1']
