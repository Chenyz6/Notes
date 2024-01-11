# aarch64-gcc7.3.0编译qt5.11.1源码



## ERROR1

![image-20240106203045519](aarch64-gcc7.3.0编译qt5.11.1源码.assets/image-20240106203045519.png)

 sudo vim  /home/ze/Documents/qt-everywhere-src-5.11.1/qtbase/src/corelib/io/qfilesystemengine_unix.cpp   

删除   #include <linux/stat.h>



## ERROR2

![image-20240106203152275](aarch64-gcc7.3.0编译qt5.11.1源码.assets/image-20240106203152275.png)

![image-20240106203213705](aarch64-gcc7.3.0编译qt5.11.1源码.assets/image-20240106203213705.png)

 sudo vim /home/ze/Documents/qt-everywhere-src-5.11.1/qtbase/src/corelib/io/qfilesystemengine_unix.cpp

删除 两个static

