FROM ubuntu:22.04

LABEL maintainer="Charles Dias <charlesdias@tecnofuturo.com.br>"

ENV TZ=America/Fortaleza
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

# Download Linux support tools
RUN apt-get update && apt-get clean && apt-get install -y \
      build-essential git wget curl python3 gcovr lcov

# Set up a development tools directory
WORKDIR /home/dev
ADD . /home/dev

# Get and install the Arm GNU Toolchain
RUN wget https://developer.arm.com/-/media/Files/downloads/gnu/11.3.rel1/binrel/arm-gnu-toolchain-11.3.rel1-x86_64-arm-none-eabi.tar.xz \
      && tar -xf arm-gnu-toolchain-11.3.rel1-x86_64-arm-none-eabi.tar.xz \
      && rm arm-gnu-toolchain-11.3.rel1-x86_64-arm-none-eabi.tar.xz

# Set up the compiler path
ENV PATH="/home/dev/arm-gnu-toolchain-11.3.rel1-x86_64-arm-none-eabi/bin:${PATH}"

# Get and install the CMake
RUN wget https://github.com/Kitware/CMake/releases/download/v3.24.2/cmake-3.24.2-linux-x86_64.sh \
      -q -O /tmp/cmake-install.sh \
      && chmod u+x /tmp/cmake-install.sh \
      && mkdir /usr/bin/cmake \
      && /tmp/cmake-install.sh --skip-license --prefix=/usr/bin/cmake \
      && rm /tmp/cmake-install.sh

# Set up the CMake path
ENV PATH="/usr/bin/cmake/bin:${PATH}"

# Set up the working directory
WORKDIR /home/project

    