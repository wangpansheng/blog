---
title: git应用之认识bash
date: 2016-05-13 09:22:24
tags: [git,shell,bash]
---

## 什么是shell

Shell俗称壳，是指"提供使用者使用界面"的软件，接收用户命令，然后调用相应的应用程序。

### shell分类


####	图形化shell

通过友好的可视化界面，调用相应应用程序，如windows系类操作系统，类Unix，Linux系统上的图形化应用程序Gnome，Kde等。

####	命令行shell

通过输入特定命令调用相应的应用程序。如window系统的cmd，Windows PowerShell；Linux系统的bash。

### 认识bash

* 在window下使用bash，需要一个软件，这个软件模拟集成了bash大部分命令，

* 各个shell的功能都差不多，linux默认使用bash，所以主要学习bash。

#### bash常用命令

* pwd(Print Working Directory) 查看当前目录;

* cd(Change Directory) 切换目录，如cd etc,cd ..返回上一层目录;

* ls(List) 查看当前目录下内容，如ls-al;
* ls -l 以列表形式产看当前目录内容

<!-- more -->
* mkdir(Make Directory) 创建目录，可以指定路径创建目录，如mkdir blog;

* touch	创建文件，

* cat 查看文件全部内容，cat ./路径/文件名

* more(unix支持) less(linux支持) 分页查看文件，空格翻页，q退出。

* rm(remove) 删除文件，如rm 文件名
* rm -rf 强制删除目录内所有文件，-r(recursion)是递归删除，-f强制删除

* rmdir(Remove Directory)   删除文件夹，只能删除空文件夹

* mv(move) 移动文件或重命名,mv index.html ./00/00/index.html

* cp(copy) 复制文件 

* head	查看文件前几行，如 head -g index.html

* tail	查看文件后几行， -n-f,

* tab	自动补全，连续按两次会将所有匹配内容显示出来

* history	查看操作历史

* ssh	远程免密码登录，如ssh root@gitlab.study.com

* > 和 >>	重定向，>覆盖，>>追加，如cat index.html > log.txt;

* clear 清空当前窗口

* curl	网络请求，

* whoami	查看当前用户

* 以下在winodw集成环境不支持

* weget	下载

* tar	解压缩

* 管道符可以将多个命令来连接在一起，上一次命令的执行结果当成下一次命令的参数。
* grep	匹配内容，一般结合管道符使用。