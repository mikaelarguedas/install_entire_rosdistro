# this can be templated
FROM ubuntu:bionic

# install packages
RUN apt-get update && apt-get install -y --no-install-recommends \
    dirmngr \
    gnupg2 \
    && rm -rf /var/lib/apt/lists/*

# setup keys
RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 421C365BD9FF1F717815A3895523BAEEB01FA116

# setup sources.list
RUN echo "deb http://packages.ros.org/ros-shadow-fixed/ubuntu bionic main" > /etc/apt/sources.list.d/ros-latest.list

# install ros packages
RUN apt-get update && apt-get install -q -y \
    ros-melodic* \
    && rm -rf /var/lib/apt/lists/*
