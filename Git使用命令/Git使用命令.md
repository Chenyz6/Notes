## 完全地覆盖本地的代码，只保留服务器端代码，则直接回退到上一个版本，再进行pull

`git reset --hard` 

`git pull origin master`

注：master为分支名



## CentOS 7 git 配置

// 安装git

sudo yum -y install git

git --version

// 配置名字和邮箱

git config --global user.name "ze"

git config --global user.email "1079903036@qq.com"

// 查看配置信息

git config --global --list

// 安装SSH密钥  会提示路径

ssh-keygen -t rsa -C "1079903036@qq.com"

![image-20230612154521330](Git使用命令.assets/image-20230612154521330.png)

// 读取密钥

vim id_rsa.pub 

// 克隆仓库

git clone git@github.com:Chenyz6/CentOS764bit_Code.git

![image-20230612154837949](Git使用命令.assets/image-20230612154837949.png)



// 提交到远程仓库-------------------

git push --progress "origin" main

// 添加本地文件到缓存区

将需要上传的代码或文件拷贝到新建文件夹里

在Git里输入以下代码回车

```text
git add .
```

注意add与“.”之间有一个空格。

// 为上传文件添加注释

等待缓存完毕，输入命令：

```text
git commit -m "first push"
```

其中的first push为注释的内容，请自定义填写。

// 提交本地文件到github新建项目中

等待上步完成，继续输入执行命令：

```text
git push origin main
```