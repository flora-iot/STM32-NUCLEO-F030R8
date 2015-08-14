# STM32-NUCLEO-F030R8
Getting Started with the STM32 NUCLEO-F030R8

##GNU GCC Installation For Ubuntu

The following steps were performed on Ubuntu 15.05. Please adjust them accordingly for other distributions. To check which Ubuntu distribution you are using

``` 
$ lsb_release -a 
```

Since the toolchain executables are 32-bit apps, when running on 64-bit machines, be sure you install the following 32-bit libraries (for different versions check the toolchain README for the actual list):

```
sudo apt-get install lib32z1 lib32ncurses5 lib32bz2-1.0
```

on Ubuntu 15.04 the following libraries are required:
```
sudo apt-get install lib32ncurses5
```
on Ubuntu 12 LTSx64 all 32-bit libraries were packed in ia32-libs, so you can also use, but be prepared to get a lot of useless libraries:
```
sudo apt-get install ia32-libs
```
download the latest Linux install tarball file (currently gcc-arm-none-eabi-4_8-2014q1-20140314-linux.tar.bz2, more than 60MB)

https://launchpad.net/gcc-arm-embedded/+download

locate the file (usually in the Home/Downloads  folder)
decide on a location to install the toolchain; the recommended folder is: ``` /usr/local ```
unpack the archive in the destination folder

Note: It is highly recommended to do not use a different install path, since the plug-in tries to automatically discover the toolchain in this default location.
```
cd /usr/local
sudo tar xjf ~/Downloads/gcc-arm-none-eabi-4_8-2014q1-20140314-linux.tar.bz2
```
the result should be a folder like 
```
/usr/local/gcc-arm-none-eabi-4_8-2014q1
```
test if the compiler is functional
```
$ /usr/local/gcc-arm-none-eabi-4_8-2014q1/bin/arm-none-eabi-gcc --version
```

```
$ arm-none-eabi-gcc (GNU Tools for ARM Embedded Processors) 4.8.3 20140228 (release) [ARM/embedded-4_8-branch revision 208322]
DO NOT add the toolchain path to the user or system path!
```

The complete toolchain documentation is available in the 
```…/share/doc/pdf/``` folder.

If you’ll ever need to remove the toolchain, just remove the ```/usr/local/gcc-arm-none-eabi-4_8-2014q1```, there are no other components stored in system folders.

##Toolchain path

To be sure you did not miss this recommendation, here it is again:

** DO NOT add the toolchain path to the user or system path! **

