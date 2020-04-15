FROM nvidia/opengl:1.0-glvnd-runtime-ubuntu16.04

SHELL ["/bin/bash", "-c"]
ENV DEBIAN_FRONTEND=noninteractive
ENV ROS_DISTRO=kinetic
ENV LANG=ja_JP.UTF-8

RUN apt-get update && apt-get upgrade -y && rm -rf /var/lib/apt/lists/*
# Editors and so on
RUN apt-get update && apt-get upgrade -y && apt-get install -y build-essential vim git tmux bash-completion x11-apps mesa-utils dirmngr sudo locales curl gnupg2 lsb-release python-pip && rm -rf /var/lib/apt/lists/*
RUN locale-gen ja_JP ja_JP.UTF-8
RUN update-locale LC_ALL=ja_JP.UTF-8 LANG=ja_JP.UTF-8

RUN sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
RUN curl -sSL 'http://keyserver.ubuntu.com/pks/lookup?op=get&search=0xC1CF6E31E6BADE8868B172B4F42ED6FBAB17C654' | sudo apt-key add -
RUN apt-get update && apt-get install -y ros-kinetic-desktop-full
RUN apt-get update && apt-get install -y python-rosdep python-rosinstall python-rosinstall-generator python-wstools && rm -rf /var/lib/apt/lists/*
RUN rosdep init && rosdep update
