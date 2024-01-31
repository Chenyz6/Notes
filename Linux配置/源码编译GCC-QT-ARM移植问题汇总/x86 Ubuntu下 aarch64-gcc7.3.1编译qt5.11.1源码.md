x86 Ubuntu下 aarch64-gcc7.3.1编译qt5.11.1源码



## error1 

qt-everywhere-src-5.11.3/qtbase/src/corelib/global/qrandom.cpp:455:62: error: no matching function for call to ‘std::mersenne_twister_engine

![img](https://img-blog.csdnimg.cn/37ee5cf722914af6ad01aed5593d6911.png)

 解决方法：定位到qrandom.cpp 文件，文件编辑器打开后，在220行添加类型声明：typedef quint32 result_type;

![img](https://img-blog.csdnimg.cn/6353101cb1fc4774a6143df954468b4a.png)





## error2

qt-everywhere-src-5.11.3/qtbase/src/corelib/tools/qbytearraymatcher.h:103:38: error: ‘numeric_limits’ is not a member of ‘std’

![img](https://img-blog.csdnimg.cn/e719d771914c4e949c366b5c96bc5cad.png)

 解决方法：因为qbytearraymatcher.h 文件缺少 limits头文件，所以打开此文件添加#include <limits>

执行命令：vim qbytearraymatcher.h

![img](https://img-blog.csdnimg.cn/3e185fb50c21430e8af1a5cc54b7ad2f.png)



## error3

![image-20240126165943381](x86 Ubuntu下 aarch64-gcc7.3.1编译qt5.11.1源码.assets/image-20240126165943381.png)

![image-20240126165953107](x86 Ubuntu下 aarch64-gcc7.3.1编译qt5.11.1源码.assets/image-20240126165953107.png)

删除  111 和 115  行的static

![image-20240126170025746](x86 Ubuntu下 aarch64-gcc7.3.1编译qt5.11.1源码.assets/image-20240126170025746.png)





## error4

![image-20240130113330745](x86 Ubuntu下 aarch64-gcc7.3.1编译qt5.11.1源码.assets/image-20240130113330745.png)

![image-20240130113512202](x86 Ubuntu下 aarch64-gcc7.3.1编译qt5.11.1源码.assets/image-20240130113512202.png)