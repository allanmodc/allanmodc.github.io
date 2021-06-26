---
title: Intalling Overture
style: cfd_cat
author: AllanMoDC
----

[Overture](https://www.overtureframework.org/) is a framework to solve partial differential equations, some of its features are very  vinteresting. Many of the frameworks available does not have a complete set of tools for the entire CFD process. Overture, on the ot her hand, have tools for CAD editing, meshing and also for ploting the solver resutls, this makes a very complete tool for computational fluid dynamics, for this reason, I'll give it a try.

# Intallation

The first step is the stallation processes. I'm confident the [manual](https://www.overtureframework.org/documentation/Installing_Overture_on_Ubuntu_10_04_LTS.pdf) should cover the entire intallation, flawless. 

## Require packages

There is an extense list of  required packages to be installed, some of them are too old and no longer avilable in the latest repositories of **Debian**. Others must be their names changed to comply with **Debian** nomenclature, the list of required packages and its counterpart are

`build-essential` \
`manpages-dev` \
`gfortran` \
`autoconf` \
`automake` \
`mpich2` ➡️ should be the version ([3.5-15](https://janitor.debian.net/git/mpich/tarball/debian/3.1-5/)). \
`libmotif3` ➡️ requires **Debian 8 (jessie)** (oldoldstable) repositories. \
`libmotif3-dev` ➡️ `libmotif-dev` (latest version). \
`libgl1-mesa-dev`\
`libglu1-xorg` ➡️ `libglu1-mesa` \
`libglu1-xorg-dev` ➡️ `libglu1-mesa-dev` \
`libglut3` ➡️ `freeglut3` \
`libglut3-dev` ➡️ `freeglut3-dev` \
`x11proto-gl-dev` \
`x11proto-print-dev` \
`libjpeg62-dev` ➡️ `libjpeg62-turbo-dev` \
`libzip-dev` \
`libperl-dev` \
`libXpm-dev` ➡️ `libxpm-dev` \
`libXp-dev` ➡️ `lixp-dev` \
`libxmu-dev` \
`libxi-dev` \
`libhdf5-103` \
`libhdf5-openmpi-103` \
`libhdf5-mpich2-dev` \

To add the **Debian 8 (jessie)** (oldoldstable) repository, create a file (for example `jessie.list`, any name should work) in directory`/etc/apt/sources.list.d` and add the following:

```console
deb https://deb.debian.org/debian/ jessie main
```
Then, update `apt`

```console
sudo apt update
```

All these packages, except `mpich2`, can then be installed in **Debian 19 (buster)** using the package manager, in terminal:

```console
sudo apt install build-essential manpages-dev gfortran autoconf 
automake libmotif3 libmotif-dev libgl1-mesa-dev libglu1-mesa 
libglu1-mesa-dev freeglut3 freeglut3-dev x11proto-gl-dev 
x11proto-print-dev libjpeg62-turbo-dev libzip-dev libperl-dev 
libxpm-dev libxp-dev libxmu-dev libxi-dev
```

To install `mpich2`, download the sources of version ([3.5-15](https://janitor.debian.net/git/mpich/tarball/debian/3.1-5/)), unpack 

```console
tar xvf mpich@debian-3-1-5.tar.gz
cd mpich@debian-3-1-5
```
The compile and install commands depends on your command interpreter, for `csh` or `sh` shells:
  
```console  
./configure --prefix=/home/<USERNAME>/mpich-install |& tee c.txt
make |& tee m.txt
make install |& tee mi.txt
```

If your shell is `csh` or `tchs`: 

```
./configure --prefix=/home/<USERNAME>/mpich-install 2>&1 | tee c.txt
make 2>&1 | tee m.txt
make install 2>&1 | tee mi.txt
```


