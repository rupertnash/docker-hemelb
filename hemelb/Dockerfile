FROM ubuntu:14.04.3
MAINTAINER Miguel O. Bernabeu (miguel.bernabeu@ed.ac.uk)

RUN apt-get update && \
    apt-get install -y software-properties-common && \
    add-apt-repository "deb http://us.archive.ubuntu.com/ubuntu/ trusty universe" && \
    apt-get update
    
# HemeLB dependencies
RUN apt-get install -y \
    cmake \
    git \
    libcppunit-dev \
    openmpi-bin

# Download and install HemeLB
WORKDIR /tmp
RUN git clone https://github.com/UCL/hemelb.git
RUN mkdir hemelb/build && \
    cd hemelb/build && \
    cmake .. -DHEMELB_STEERING_LIB=none -DHEMELB_USE_SSE3=ON && \
    make

# Create a mount point for data
VOLUME /data
