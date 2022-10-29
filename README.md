# How to test the Docker Images


## Docker Image gcc-arm-cmake

This Docker image was create FROM ubuntu:22.04 and has the following packages:
- git version 2.34.1;
- Arm GNU Toolchain 11.3.Rel1;
- CMake version 3.24.2;
- Python 3.10.6;
- build-essential;
- wget;
- curl.


1. Pull the latest docker image version
```console
docker pull charlesdias/gcc-arm-cmake
```    

2. Check the version of Arm GNU Toolchain 
```console
docker run --rm charlesdias/gcc-arm-cmake arm-none-eabi-gcc -v
```    

3. Check the version of CMake
```console
docker run --rm charlesdias/gcc-arm-cmake cmake --version
```  
```    

2. Check the version of GCC   
```console
$ docker run --rm charlesdias/gcc-arm-cmake arm-none-eabi-gcc -v
```    

3. Check the version of CMake
```console
$ docker run --rm charlesdias/gcc-arm-cmake cmake --version
```  

