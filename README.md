<h1 align=center>Git</h1>

 ![logo@2x](/images/logo%402x.png)

:tada: 在工作中必须掌握使用的

:trident: git 十分简单！

---

- [版本控制](#版本控制)
- [Git环境配置](Git环境配置)
- [Git基本理论(核心)](Git基本理论(核心))
- [Git基础理论](Git基础理论)
- [Git项目搭建](Git项目搭建)
- [Git文件操作](Git文件操作)
- [Git分支](Git分支)

#### 版本控制

记住四个字：版本迭代

版本控制工具：新的版本出现，不能直接废弃旧版本；

> 常见的版本控制工具

git、svn、cvs、vss等

为什么学习 git原因：**git目前是世界上最先进的分布式版本控制系统。**

注意：git是分布式版本控制系统，SVN是集中式版本控制系统

#### Git环境配置

> 软件下载

https://git-scm.com/

下载对应的版本即可，按照：无脑下一步即可！

> 环境变量

环境变量只是为了全局使用而已！

默认会配置：Path：C:\Program Files\Git\cmd

> 启动git

任意文件夹下右键看到对应的程序

+ git bush
+ git cmd
+ git GUI

> git 配置

**所有的配置文件都保存在本地**

 `git config -l `查看默认的配置

` git config --system --list`查看系统配置的

```sh
diff.astextplain.textconv=astextplain
filter.lfs.clean=git-lfs clean -- %f
filter.lfs.smudge=git-lfs smudge -- %f
filter.lfs.process=git-lfs filter-process
filter.lfs.required=true
http.sslbackend=openssl
http.sslcainfo=C:/Program Files/Git/mingw64/ssl/certs/ca-bundle.crt
core.autocrlf=true
core.fscache=true
core.symlinks=false
pull.rebase=false
credential.helper=manager-core
credential.https://dev.azure.com.usehttppath=true
init.defaultbranch=master
user.email=baimyishu13@163.com
user.name=baimiyishu13
```

查看自己配置的

```SH
$ git config --global --list
user.email=baimyishu13@163.com
user.name=baimiyishu13
```

Git相关的配置文件:

系统配置：‪C:\Program Files\Git\etc\gitconfig	对应 git的系统配置

用户配置：‪C:\Users\admin\.gitconfig

**本质：都是一些本地文件**



> 设置用户名 & 邮箱

```SH
$ git config --global user.name "baimiyishu13"
$ git config --global user.email "baimyishu13@163.com"
```



#### Git基础理论

> 工作区域

Git本地有三个工作区域

+ 工作目录（Workspace）：工作区，就是你平时存放项目代码的地方
+ 暂存区（index/stage）: 暂存区，用于零时存放你的改动，事实上它就是一个文件，保存即将提交到文件列表信息
+ 资源库（Repository）：仓库区（或本地仓库）安全存放数据的位置，有所提交的所有版本的数据，其中HEAD指向最新放入库的版本

如果在加上远程git仓库就可以分成四个工作区域，文件在这四个工作区域之间的转换关系如下：

![git00](/images/image-20221114181426826.png)

本地仓库（HEAD文件）.git隐藏文件夹

```
ref: refs/heads/main	//  主分支（会将代码提交到住分支）
```



**工作基本流程：**

git的工作流程一般是这样的：

1. 在工作目录中添加、修改文件
2. 将需要进行版本管理的文件放入暂存区域；   （git add）
3. 将暂存区域的文件提交到git仓库                      （git commint）

因此，git管理的文件有三种状态：已修改，已暂存、已提交



#### Git项目搭建

> 创建工作目录与常用指令

工作目录（workSpace）一般是希望Git帮助管理文件夹，可以是项目目录，也可使空目录，建议不要有中文。

日常使用只需记住几个命令：

![git01](/images/image-20221114175940379.png)

> 本地创建仓库

初始化：

1. git init （生成一个.git文件）

> 远程仓库

1. 克隆一个远程仓库：如 git clone https://github.com/baimiyishu13/Git.git



#### Git文件操作

> 将目录下文件提交到暂存区

```
git add .		// 添加所有文件到暂存区
git status		// 查看暂存区文件
git commit -m	// 提交暂存区内容到本地仓库 -m 提交信息
// $git commit -m "new file"

```

> 忽略文件

在住目录下创建“.gitgnore”文件，此文件有如下规则：

```SH
# 为注释
*.txt		// 忽略所有.txt文件
!lib.txt	// 但lib.txt文件除外
/temp		// 仅忽略项目根目录下的文件，不包括其他目录temp
build/		// 忽略build目录下所有文件
doc/*.txt   // 忽略doc/notes.txt 但不包括 doc/server.arch.txt
```

> SSH免密登录

C:\Users\admin\.ssh

```
# 生成公钥
$ ssh-keygen.exe
```

将公钥添加到ssh公钥：id_rsa.pub

https://github.com/settings/keys



**GO中集成Git**

> 新建项目，绑定git 

将远程的git文件目录拷贝到项目中即可

> 修改文件，使用Go操作git

1. 添加到暂存区
2. commint提交
3. push到远程仓库



#### Git分支

