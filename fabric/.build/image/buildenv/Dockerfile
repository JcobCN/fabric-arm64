# Copyright Greg Haskins All Rights Reserved
#
# SPDX-License-Identifier: Apache-2.0

FROM hyperledger/fabric-baseimage:arm64-0.4.21
COPY payload/protoc-gen-go /usr/local/bin/
ADD payload/gotools.tar.bz2 /usr/local/bin/

# override GOCACHE=off from fabric-baseimage
ENV GOCACHE "/tmp"
LABEL org.hyperledger.fabric.version=1.4.9 \
      org.hyperledger.fabric.base.version=0.4.21
