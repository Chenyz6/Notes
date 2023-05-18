# Linux常用命令

### 清屏命令

1. clear

\#实质上是翻页,只要往上翻还是能看到之前的记录

2. ctrl + L

\#等价于 clear

### 分屏

```
:vsp filename
```

![image-20230411100658345](Linux系统编程笔记.assets/image-20230411100658345.png)

### vim

![image-20230406154924327](Linux系统编程笔记.assets/image-20230406154924327.png)

![image-20230406154951003](Linux系统编程笔记.assets/image-20230406154951003.png)

 *号从上往下找

#号从下往上找



#### 设置vim  tab首行缩进为4个空格

![image-20230415134355603](Linux系统编程笔记.assets/image-20230415134355603.png)

#### 查看Man Page    --->    shift + k （K）

#### ![image-20230415135438590](Linux系统编程笔记.assets/image-20230415135438590.png) 

#### 高亮显示

在编辑器里非编辑状态，输入：
shift + 3 （#）
shift + 8 （*）
会出现高亮显示，看着很不舒服，
取消方式:
：noh



### 删除后缀名相同文件  用*

![image-20230407161611111](Linux系统编程笔记.assets/image-20230407161611111.png)

### ldd命令 查看可执行程序加载哪些库和路径

![image-20230410160159367](Linux系统编程笔记.assets/image-20230410160159367.png)



### cat tac命令

只输入cat  用来回显   （你输入什么，它输出什么）

tac   反过来输出显示



### 大文本查看命令 more less head tail

![image-20230421175416578](Linux系统编程笔记.assets/image-20230421175416578.png)



### stat命令

文件/文件系统的详细信息显示

![image-20230421205212129](Linux系统编程笔记.assets/image-20230421205212129.png)







### 用户用户组




#### whoami

查看当前用户



#### chmod

![image-20230421183529530](Linux系统编程笔记.assets/image-20230421183529530.png)

![image-20230421183548438](Linux系统编程笔记.assets/image-20230421183548438.png)



#### chown

![image-20230421184753438](Linux系统编程笔记.assets/image-20230421184753438.png)



#### chgrp

![image-20230421185131764](Linux系统编程笔记.assets/image-20230421185131764.png)



#### 直接修改用户和用户组

![image-20230421185358708](Linux系统编程笔记.assets/image-20230421185358708.png)



### find命令   -- 找文件

![image-20230421203417295](Linux系统编程笔记.assets/image-20230421203417295.png)

![image-20230421213123462](Linux系统编程笔记.assets/image-20230421213123462.png)

![image-20230421213628320](Linux系统编程笔记.assets/image-20230421213628320.png)

![image-20230421210712221](Linux系统编程笔记.assets/image-20230421210712221.png)

![image-20230421210431428](Linux系统编程笔记.assets/image-20230421210431428.png)

![image-20230421204327747](Linux系统编程笔记.assets/image-20230421204327747.png)

![image-20230421204612953](Linux系统编程笔记.assets/image-20230421204612953.png)



### grep命令   -- 找文件内容







## 包管理工具  Centos  yum

![image-20230421181444060](Linux系统编程笔记.assets/image-20230421181444060.png)



## Linux系统文件类型

普通文件：-

目录文件：d

字符设备文件：c

块设备文件：b

软连接：l

管道文件：p

套接字：s

未知文件。



## gcc编译四步骤 

![image-20230404154726099](Linux系统编程笔记.assets/image-20230404154726099.png)

## gcc参数

![image-20230404161400503](Linux系统编程笔记.assets/image-20230404161400503.png)

![image-20230404161520267](Linux系统编程笔记.assets/image-20230404161520267.png)

-I    指定头文件的路径



## 32位系统 内存存储情况 数据段合并

![image-20230410162148613](Linux系统编程笔记.assets/image-20230410162148613.png)

​		32位的CPU(准确的说是运行在32位模式下的CPU)只能寻址最大4GB的内存，受制于此，32位的操作系统也只能识别最大4GB的内存，由于在系统中，除了内存之外，还有很多存储设备，因此，真正可以利用的内存空间肯定小于4GB，也就是我们看到的系统属性中显示的3.xxG。
　　但64位CPU则有了很大改变，64位CPU的最大寻址空间为2的64次方bytes，计算后其可寻址空间达到了惊人的16TB(treabytes)，即16384GB。当然，这只是理论，从实际应用上，win10 64bit的各版本分别为8GB-192GB，其中，家庭普通版能支持8GB内存，家庭高级版能支持16GB内存，而64位的win10专业版、企业版和旗舰版最高可支持192GB内存。

![image-20230518195204351](Linux系统编程笔记.assets/image-20230518195204351.png)



## 动态库和静态库理论对比

![image-20230404164840928](Linux系统编程笔记.assets/image-20230404164840928.png)



## 静态库

![image-20230406153845686](Linux系统编程笔记.assets/image-20230406153845686.png)

![image-20230406112053503](Linux系统编程笔记.assets/image-20230406112053503.png)

出现以下情况，一般都是链接器出现的问题

![image-20230406111705923](Linux系统编程笔记.assets/image-20230406111705923.png)

![image-20230406154122003](Linux系统编程笔记.assets/image-20230406154122003.png)

![image-20230406150358936](Linux系统编程笔记.assets/image-20230406150358936.png)



## 动态库

![](Linux系统编程笔记.assets/image-20230407160813762.png)

**PIC表示位置无关代码**

gcc **-c** add.c -o add.o -fPIC

gcc -shared **-o** libmylib.so add.o

![image-20230407162844170](Linux系统编程笔记.assets/image-20230407162844170.png)

![image-20230410160923267](Linux系统编程笔记.assets/image-20230410160923267.png)

**export LD_LIBRARY_PATH=./   写路径**

**环境变量 是进程的概念**

![image-20230410154750795](Linux系统编程笔记.assets/image-20230410154750795.png)





## 软连接和硬链接

![image-20230421181850284](Linux系统编程笔记.assets/image-20230421181850284.png)

软连接在创建的时候  尽量使用绝对路径  便于移植

![image-20230421183118773](Linux系统编程笔记.assets/image-20230421183118773.png)









## GDB调试

![image-20230411104647638](Linux系统编程笔记.assets/image-20230411104647638.png)

![image-20230411104658925](Linux系统编程笔记.assets/image-20230411104658925.png) 

![image-20230411110243028](Linux系统编程笔记.assets/image-20230411110243028.png)



## Makefile

什么是makefile？或许很多Winodws的程序员都不知道这个东西，因为那些Windows的IDE都为你做了这个工作，但我觉得要作一个好的和professional的程序员，makefile还是要懂。这就好像现在有这么多的HTML的编辑器，但如果你想成为一个专业人士，你还是要了解HTML的标识的含义。特别在Unix下的软件编译，你就不能不自己写makefile了，会不会写makefile，从一个侧面说明了一个人是否具备完成大型工程的能力。

因为，**makefile关系到了整个工程的编译规则。一个工程中的源文件不计数，其按类型、功能、模块分别放在若干个目录中，makefile定义了一系列的规则来指定，哪些文件需要先编译，哪些文件需要后编译，哪些文件需要重新编译，甚至于进行更复杂的功能操作，因为makefile就像一个Shell脚本一样，其中也可以执行操作系统的命令。**

makefile带来的好处就是——“自动化编译”，一旦写好，只需要一个make命令，整个工程完全自动编译，极大的提高了软件开发的效率。make是一个命令工具，是一个解释makefile中指令的命令工具，一般来说，大多数的IDE都有这个命令，比如：Delphi的make，Visual C++的nmake，Linux下GNU的make。可见，makefile都成为了一种在工程方面的编译方法。

现在讲述如何写makefile的文章比较少，这是我想写这篇文章的原因。当然，不同产商的make各不相同，也有不同的语法，但其本质都是在“文件依赖性”上做文章，这里，我仅对GNU的make进行讲述，我的环境是RedHat Linux 8.0，make的版本是3.80。必竟，这个make是应用最为广泛的，也是用得最多的。而且其还是最遵循于IEEE 1003.2-1992 标准的（POSIX.2）。

在这篇文档中，将以C/C++的源码作为我们基础，所以必然涉及一些关于C/C++的编译的知识，相关于这方面的内容，还请各位查看相关的编译器的文档。这里所默认的编译器是UNIX下的GCC和CC。
————————————————
版权声明：本文为CSDN博主「haoel」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/haoel/article/details/2886



![image-20230412112311419](Linux系统编程笔记.assets/image-20230412112311419.png)

![image-20230412112725993](Linux系统编程笔记.assets/image-20230412112725993.png)



![image-20230415121625492](Linux系统编程笔记.assets/image-20230415121625492.png)

![image-20230415121729033](Linux系统编程笔记.assets/image-20230415121729033.png)

**clean的时候记得一定要   加一个-n查看一下要删除的内容是不是源码**

![image-20230415113246715](Linux系统编程笔记.assets/image-20230415113246715.png)

![image-20230415121444087](Linux系统编程笔记.assets/image-20230415121444087.png)





## Read/Write 函数

![image-20230518201413133](Linux系统编程笔记.assets/image-20230518201413133.png)



## 阻塞/非阻塞

![image-20230518202351565](Linux系统编程笔记.assets/image-20230518202351565.png)
