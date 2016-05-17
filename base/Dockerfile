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

# CppUnit fails to compile if downloaded by HemeLB's CMake, install it system-wide
RUN apt-get install -y git cmake libcppunit-dev libcgal-dev libvtk5-dev python-vtk vmtk python-wxtools python-wxversion swig openmpi-bin
RUN pip install cython numpy PyYAML

