FROM ubuntu:20.04

LABEL maintainer="Charles Dias <charlesdias@tecnofuturo.com.br>"

# Download Linux support tools
RUN apt-get update && \
      apt-get clean && \ 
      apt-get install -y \
      build-essential \
      wget \
      curl

# Set up a development tools directory
WORKDIR /home/dev
ADD . /home/dev

# Get and install the Arm gcc compiler
RUN wget https://developer.arm.com/-/media/Files/downloads/gnu/11.2-2022.02/binrel/gcc-arm-11.2-2022.02-x86_64-arm-none-eabi.tar.xz \
      && tar -xf gcc-arm-11.2-2022.02-x86_64-arm-none-eabi.tar.xz \
      && rm gcc-arm-11.2-2022.02-x86_64-arm-none-eabi.tar.xz

# Set up the compiler path
ENV PATH="/home/dev/gcc-arm-11.2-2022.02-x86_64-arm-none-eabi/bin:${PATH}"

# Get and install the CMake
RUN wget https://github.com/Kitware/CMake/releases/download/v3.23.2/cmake-3.23.2-linux-x86_64.sh \
      -q -O /tmp/cmake-install.sh \
      && chmod u+x /tmp/cmake-install.sh \
      && mkdir /usr/bin/cmake \
      && /tmp/cmake-install.sh --skip-license --prefix=/usr/bin/cmake \
      && rm /tmp/cmake-install.sh

# Set up the CMake path
ENV PATH="/usr/bin/cmake/bin:${PATH}"

# Set up the working directory
WORKDIR /home/project

    