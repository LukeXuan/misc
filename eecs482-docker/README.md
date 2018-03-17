# EECS482 Docker Environment

This folder contains a `Dockerfile` which can be used to build a (somewhat minimal) docker image with the basic components that EECS482 needs.

## Content
- make
- cmake
- gcc
- g++
- tmux

## How to use

### Build

```
docker build -t `whoami`/centos-dev .
```

### Usage

This command boot the image while sharing current folder and killing it after exit

```
docker run --rm -it --mount src=`pwd`,target=/shared,type=bind `whoami`/centos-dev /bin/bash
```
