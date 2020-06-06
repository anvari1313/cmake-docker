FROM ubuntu:18.04

LABEL maintainer="Ahmad Anvari <ahmad.anv@gmail.com>"

ADD https://github.com/Kitware/CMake/releases/download/v3.16.5/cmake-3.16.5.tar.gz /tmp/cmake.tar.gz

RUN apt update && \
    apt install -y build-essential libssl-dev gcc g++ && \
    tar -zxvf /tmp/cmake.tar.gz -C /tmp/ && \
    cd /tmp/cmake-3.16.5 && \
    ./bootstrap && \
    make && \
    make install && \
    rm -rf /tmp/cmake-3.16.5 /tmp/cmake.tar.gz