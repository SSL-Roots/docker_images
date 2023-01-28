FROM ubuntu:20.04

# .grsim.xml file will be saved to $HOME directory.
ENV HOME=/root/robocup
WORKDIR $HOME

# set DEBIAN_FRONTEND=noninteractive to avoid interaction with tzdata
RUN apt-get update \
    && DEBIAN_FRONTEND=noninteractive apt-get install -y git build-essential cmake pkg-config qt5-default \
        libqt5opengl5-dev libgl1-mesa-dev libglu1-mesa-dev \
        libprotobuf-dev protobuf-compiler libode-dev libboost-dev \
    && rm -rf /var/lib/apt/lists/*

# Build and Install grSim
RUN git clone --depth=1 https://github.com/RoboCup-SSL/grSim.git \
    && cd grSim \
    && mkdir build \
    && cd build \
    && cmake .. \
    && make \
    && make install

WORKDIR $HOME/grSim/bin