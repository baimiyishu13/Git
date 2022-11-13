<h1 align=center>Git</h1>

 ![logo@2x](/images/logo%402x.png)

:tada: 在工作中必须掌握使用的

:trident: git 十分简单！

---

- [版本控制](#版本控制)
- [Git环境配置](Git环境配置)
- [Git基本理论(核心)](Git基本理论(核心))

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

+ 工作目录
+ 暂存区
+ 资源库