#
# Copyright Greg Haskins All Rights Reserved.
#
# SPDX-License-Identifier: Apache-2.0
#
#FROM adoptopenjdk:8u222-b10-jdk-openj9-0.15.1
FROM adoptopenjdk:jdk-arm64
#RUN echo " " > /etc/apt/sources.list && \
#echo "deb http://mirrors.163.com/ubuntu/ focal main restricted universe multiverse" > /etc/apt/sources.list && \
#echo "deb http://mirrors.163.com/ubuntu/ focal-security main restricted universe multiverse" >> /etc/apt/sources.list && \
#echo "deb http://mirrors.163.com/ubuntu/ focal-updates main restricted universe multiverse"  >> /etc/apt/sources.list && \
#echo "deb http://mirrors.163.com/ubuntu/ focal-backports main restricted universe multiverse"  >> /etc/apt/sources.list

RUN echo "deb https://mirror.tuna.tsinghua.edu.cn/ubuntu-ports/ focal main restricted universe multiverse\n \
deb https://mirror.tuna.tsinghua.edu.cn/ubuntu-ports/ focal-updates main restricted universe multiverse\n \
deb https://mirror.tuna.tsinghua.edu.cn/ubuntu-ports/ focal-backports main restricted universe multiverse \n \
deb https://mirror.tuna.tsinghua.edu.cn/ubuntu-ports/ focal-security main restricted universe multiverse \n \
deb https://mirror.tuna.tsinghua.edu.cn/ubuntu-ports/ focal-proposed main restricted universe multiverse" > /etc/apt/sources.list

COPY scripts /tmp/scripts
RUN cd /tmp/scripts && \
    common/packages.sh && \
    common/setup.sh && \
    docker/fixup.sh && \
    common/cleanup.sh && \
    rm -rf /tmp/scripts
ENV GOPATH=/opt/gopath
ENV GOROOT=/opt/go
ENV PATH=$PATH:$GOROOT/bin:$GOPATH/bin
