# Taking as base image a Ubuntu Desktop container with web-based noVNC connection enabled
FROM dorowu/ubuntu-desktop-lxde-vnc
MAINTAINER Miguel O. Bernabeu (miguel.bernabeu@ed.ac.uk)

##
# Dependencies
##
# Ubuntu's VMTK package is in the Multiverse repository, OpenMPI in Universe
RUN apt-get update && \
    apt-get install -y software-properties-common && \
    add-apt-repository "deb http://us.archive.ubuntu.com/ubuntu/ trusty universe" && \
    add-apt-repository "deb http://us.archive.ubuntu.com/ubuntu/ trusty multiverse" && \
    apt-get update

RUN apt-get install -y \
    git \
    libcgal-dev \
    libvtk5-dev \
    python-vtk \
    vmtk \
    python-wxtools \
    python-wxversion \
    swig

RUN pip install \
    cython \
    numpy \
    PyYAML
