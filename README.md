# How to test the Docker Images


## Docker Image gcc-arm-cmake

This Docker image was create FROM ubuntu:20.04 and has the following packages:
- build-essential;
- wget;
- curl;
- gcc version 11.2.1 20220111 (GNU Toolchain for the Arm Architecture 11.2-2022.02 (arm-11.14));
- CMake version 3.23.2.

1. Pull the latest docker image version
```console
$ docker pull charlesdias/gcc-arm-cmake
```    

2. Check the version of GCC   
```console
$ docker run --rm charlesdias/gcc-arm-cmake arm-none-eabi-gcc -v
```    

3. Check the version of CMake
```console
$ docker run --rm charlesdias/gcc-arm-cmake cmake --version
```  

