# datalab
Embedded Linux Introduction Lab




Install common development tools
```
$ sudo apt install build essential
$ sudo apt install git vim
```

Git configuration (if you don't have a git config already) 
```
$ git config --global user.name “User Name”
$ git config --global user.email email@luxoft.com
```

Create a workspace directory 
```
$ mkdir $HOME/workspace

```

Install development dependencies 
```
$ sudo apt install build-essential autoconf libtool cmake pkg-config git python-dev swig3.0 libpcre3-dev nodejs-dev gawk wget diffstat bison flex
$ sudo apt install device-tree-compiler libncurses5-dev
```


Installing the GNU Cross compilation tools for ARM Architecture
GNU binutils
```
$ sudo apt install binutils-arm-linux-gnueabihf
```

GNU GCC cross toolchain
```
$ sudo apt install gcc-arm-linux-gnueabihf
$ sudo apt install gcc-aarch64-linux-gnu
$ sudo apt install g++-aarch64-linux-gnu
```

Building and running QEMU with a aarch64 pre-built image
```
$ cd $HOME/workspace
$ sudo apt build-dep qemu
$ git clone git://git.qemu.org/qemu.git qemu
$ cd qemu
$ ./configure --target-list=aarch64-softmmu
$ make
$ cd ..
$ ./qemu/build/aarch64-softmmu/qemu-system-aarch64 \
-machine virt \
-cpu cortex-a53 \ 
-machine type=virt \
-nographic \
-smp 1 \
-m 2048 \
-kernel aarch64-linux-3.15rc2-buildroot.img  \
--append "console=ttyAMA0" ;
```
