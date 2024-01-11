https://blog.csdn.net/weixin_46584887/article/details/122527982

# Ubuntu安装低版本gcc



1）官方下载网址如下：https://ftp.gnu.org/gnu/gcc/

2）创建存储目录 任意路径（用来保存编译安装后的路径）  例如   /gcc7.3.0

3）解压源码    tar -zxf gcc-7.3.0.tar.gz

4）下载编译相关依赖        ./contrib/download_prerequisites

5）配置编译选项     配置安装目录以及部分选项，全部选项在 `INSTALL` 目录里！！！！注意修改

./configure --prefix=/usr/local/gcc/gcc-6.3.0 --enable-threads=posix --disable-checking --disable-multilib --enable-languages=c,c++ --disable-libsanitizer

6）sudo make

7）sudo make install







配置系统gcc版本
查看系统已安装 gcc 版本：

ls -l /usr/bin/gcc*
1
为 gcc-6.3 设置软连接：

sudo ln -s /usr/local/gcc/gcc-6.3.0/bin/gcc /usr/bin/gcc-6
1
添加到系统管理器中：

sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-6 40
1
切换你当前使用的 gcc 版本：

sudo update-alternatives --config gcc
1
同时配置 g++6.3.0：

sudo ln -s /usr/local/gcc/gcc-6.3.0/bin/g++ /usr/bin/g++-6
1
接着

sudo update-alternatives  --install /usr/bin/g++ g++ /usr/bin/g++-6 40
1
切换系统 g++ 版本：

sudo update-alternatives --config g++
1
五、检验安装
查看系统 gcc 版本：

gcc --version
1
查看系统 g++ 版本：

g++ --version



