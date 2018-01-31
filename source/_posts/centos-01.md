---
title: centos-01
tags: [centos]
date: 2017-03-03 15:44:10
---
##  常用命令

    ```bash
    //查看当前centos系统的版本
    cat /etc/redhat-release
    //查看系统内核版本是32位还是64位
    uname -r
    //安装cnpm
    npm install cnpm -g --registry=https://registry.npm.taobao.org
    ```

##  添加用户

>   在企业生产中，一般不会直接使用root来操作，可以通过命令创建用户，并且进行切换，普通用户下，前边显示的是$符号，root下显示的是#

```bash
useradd username    //添加用户名
passwd username     //给刚才添加的用户，设置密码，然后会提示输入密码，输入两次就可以了
su - username       //可以切换到指定的用户
su - root           //可以切换到root
whoami              //可以查看当前用户是谁

```