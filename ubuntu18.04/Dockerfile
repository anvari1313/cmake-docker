FROM ubuntu:18.04

LABEL maintainer="Ahmad Anvari <ahmad.anv@gmail.com>"

# Version of CMake
ARG VERSION=3.16.5

ADD https://github.com/Kitware/CMake/releases/download/v$VERSION/cmake-$VERSION.tar.gz /tmp/cmake.tar.gz

RUN apt update && \
    apt install -y build-essential libssl-dev gcc g++ && \
    tar -zxvf /tmp/cmake.tar.gz -C /tmp/ && \
    cd /tmp/cmake-$VERSION && \
    ./bootstrap && \
    make && \
    make install && \
    rm -rf /tmp/cmake-$VERSION /tmp/cmake.tar.gz