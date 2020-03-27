# About

This is a brief overview of how to get started with `lpc21isp`.

## Requirements
  - cmake
  - gcc
  - git

## Gotchas

If you intend to use lpc21isp on en embedded device e.p. raspberry pi 3 compute module it needs to be compiled on that platform or cross compiled for that platform.

## Building on platform with GPIO_SUPPORT with cmake

1. install all the required tools on the Device `sudo apt-get update && sudo apt-get install cmake gcc git`
2. clone the project repository `git clone https://github.com/DynonAvionics/lpc21isp.git`
3. move into the project `cd lp21isp`
4. create an out of source build directory `mkdir _build`
5. move into that directory `cd _build`
6. invoke cmake with GPIO_SUPPORT `cmake .. -DGPIO_SUPPORT=ON`
7. build lpc21isp `make all -j5`
