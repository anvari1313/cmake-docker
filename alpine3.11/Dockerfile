FROM alpine:3.11

LABEL maintainer="Ahmad Anvari <ahmad.anv@gmail.com>"

# Version of CMake
ARG VERSION=3.17.3

ADD https://github.com/Kitware/CMake/releases/download/v$VERSION/cmake-$VERSION.tar.gz /tmp/cmake.tar.gz

RUN apk add build-base linux-headers libressl-dev && \
    tar -zxvf /tmp/cmake.tar.gz -C /tmp/ && \
    cd /tmp/cmake-$VERSION && \
    ./configure && \
    make && \
    make install && \
    rm -rf /tmp/cmake-$VERSION /tmp/cmake.tar.gz