# Linux常用命令

## 清屏命令

1. clear

\#实质上是翻页,只要往上翻还是能看到之前的记录

2. ctrl + L

\#等价于 clear

## 分屏

```
:vsp filename
```

![image-20230411100658345](Linux常用命令及问题.assets/image-20230411100658345.png)

## vim

![image-20230406154924327](Linux常用命令及问题.assets/image-20230406154924327.png)

![image-20230406154951003](Linux常用命令及问题.assets/image-20230406154951003.png)

 *号从上往下找

#号从下往上找



### 设置vim  tab首行缩进为4个空格

![image-20230415134355603](Linux常用命令及问题.assets/image-20230415134355603.png)

  1 set ts=4
  2 set sw=4
  3 imap ( ()<ESC>i        "设置（自动补全
  4 imap [ []<ESC>i
  5 imap { {}<ESC>i
  6 imap < <><ESC>i
  7 imap ' ''<ESC>i
  8 imap " ""<ESC>i
  9 set nu 						"设置显示行号
 10 set ruler				    "设置标尺
 11 set ai						 "设置文本高亮
 12 set autoindent		"设置自动缩进（与上一行的缩进相同）

![image-20230619142954778](Linux常用命令及问题.assets/image-20230619142954778.png)



### 查看Man Page    --->    shift + k （K）

#### ![image-20230415135438590](Linux常用命令.assets/image-20230415135438590.png) 

### 高亮显示

在编辑器里非编辑状态，输入：
shift + 3 （#）
shift + 8 （*）
会出现高亮显示，看着很不舒服，
取消方式:
：noh



### 查找宏定义

【 + d         左中括号 ＋ d







## 删除后缀名相同文件  用*

![image-20230407161611111](Linux常用命令及问题.assets/image-20230407161611111.png)

## ldd命令 查看可执行程序加载哪些库和路径

![image-20230410160159367](Linux常用命令及问题.assets/image-20230410160159367.png)



## cat tac命令

只输入cat  用来回显   （你输入什么，它输出什么）

tac   反过来输出显示



## 大文本查看命令 more less head tail

![image-20230421175416578](Linux常用命令及问题.assets/image-20230421175416578.png)



## stat命令

文件/文件系统的详细信息显示

![image-20230421205212129](Linux常用命令及问题.assets/image-20230421205212129.png)







## 用户用户组




### whoami

查看当前用户



### chmod

![image-20230421183529530](Linux常用命令及问题.assets/image-20230421183529530.png)

![image-20230421183548438](Linux常用命令及问题.assets/image-20230421183548438.png)



### chown

![image-20230421184753438](Linux常用命令及问题.assets/image-20230421184753438.png)



### chgrp

![image-20230421185131764](Linux常用命令及问题.assets/image-20230421185131764.png)



### 直接修改用户和用户组

![image-20230421185358708](Linux常用命令及问题.assets/image-20230421185358708.png)



## find命令   -- 找文件

![image-20230421203417295](Linux常用命令及问题.assets/image-20230421203417295.png)

![image-20230421213123462](Linux常用命令及问题.assets/image-20230421213123462.png)

![image-20230421213628320](Linux常用命令及问题.assets/image-20230421213628320.png)

![image-20230421210712221](Linux常用命令及问题.assets/image-20230421210712221.png)

![image-20230421210431428](Linux常用命令及问题.assets/image-20230421210431428.png)

![image-20230421204327747](Linux常用命令及问题.assets/image-20230421204327747.png)

![image-20230421204612953](Linux常用命令及问题.assets/image-20230421204612953.png)



## grep命令   -- 找文件内容



## ps命令

ps aux    如果直接用ps命令，会显示所有进程的状态，通常结合**grep**命令查看某进程的状态

![image-20230604171622790](Linux常用命令及问题.assets/image-20230604171622790.png)

ps ajx    查看父进程ID，进程ID，进程组ID，会话ID的方法：ps ajx

![image-20230604171558335](Linux常用命令及问题.assets/image-20230604171558335.png)

ps -Lf 进程号               查看单前的进程的线程



## **sudo apt update**

列出所有可更新的软件清单命令



## **sudo apt upgrade**

升级软件包



## strace  查看系统调用



## ulimit -a 显示当前的各种用户进程限制













# Linux问题



## 用自己新加的库 编译报错

![image-20230717100259740](Linux常用命令及问题.assets/image-20230717100259740.png)

[解决error while loading shared libraries: libXXX.so.X: cannot open shared object file: No such file_Mr.deeplan的博客-CSDN博客](https://blog.csdn.net/deeplan_1994/article/details/83927832?utm_medium=distribute.pc_relevant_right.none-task-blog-BlogCommendFromMachineLearnPai2-1.nonecase&depth_1-utm_source=distribute.pc_relevant_right.none-task-blog-BlogCommendFromMachineLearnPai2-1.nonecase)

进入root用户 

![image-20230717100346782](Linux常用命令及问题.assets/image-20230717100346782.png)



## 切换root用户报错 Authentication failure

![image-20230717152518732](Linux常用命令及问题.assets/image-20230717152518732.png)