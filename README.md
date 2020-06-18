# CMake Docker

CMake is an open-source, cross-platform family of tools designed to build, test and package software. CMake is used to control the software compilation process using simple platform and compiler independent configuration files, and generate native makefiles and workspaces that can be used in the compiler environment of your choice. The suite of CMake tools were created by Kitware in response to the need for a powerful, cross-platform build environment for open-source projects such as ITK and VTK.

This repo contains cmake docker images. You can easily pull images with different tags based on your need  from [DockerHub](https://hub.docker.com/r/anvari/cmake).

Please feel free to open issue [here](https://github.com/anvari1313/cmake-docker/issues).

## How to use this image?

Multi-stage docker build can be used like this for your C++ application:

```Dockerfile
FROM anvari/cmake:3.17.3-bionic AS build

# Add source code to image
ADD . /app

WORKDIR /app

RUN mkdir /app/build && \
    cd /app/build
    cmake .. && \
    make 

FROM ubuntu:bionic

COPY --from=build /app/build/application /usr/local/bin

CMD ["application"]
```