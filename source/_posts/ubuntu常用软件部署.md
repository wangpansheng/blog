---
title: ubuntu常用软件部署
tags: [linux,ubuntu ]
date: 2017-04-02 17:46:19
---

#   ubuntu中快速安装nodejs

##  1.  我们可以直接通过`apt-get`安装nodejs

```
sudo apt-get update //需要先刷新本地索引包
sudo apt-get install nodejs //然后安装nodejs包
sudo apt-get install npm    //安装npm包管理器
```

##  2. 安装好的node版本较低，我们可以使用n模块升级node到你需要打版本

####    1.  node有一个 n模块，专门用来管理nodejs版本的。不过目前并不支持windows系统。我们先安装下

```
npm install -g n
```

####    2.  升级到制定版本，我们可以在n加上指定的版本号就可以

```
sudo n 6.10.2
```

<!-- more -->
####    3.  还有一些常用打快捷方法

```
sudo n latest   //安装最新打官方版本
sudo n stanle   //安装最新打稳定版
sudo n lts      //安装最新打lts官方版
```

####    4.  删除版本

```
sudo n rm 0.9.4
sudo n -0.9.4
```

-   更多命令，我们可以使用`n --help`寻求帮助

#   ubuntu常用工具安装

##  右上角任务栏显示cpu内存使用百分比，还可以显示网络传输速率

```
sudo add-apt-repository ppa:fossfreedom/indicator-sysmonitor   //这里选择按enter键
sudo apt-get update
sudo apt-get install indicator-sysmonitor
//启动
indicator-sysmonitor &
//ctrl+c后台运行该程序
```

- 启动之后，最好让程序开机自启动，鼠标右键点击标题栏上图标，弹出菜单，把`run on startup`后边打勾打上，然后进去advanced选项卡，就可以自定义配置需要显示在任务栏的项目啦


##  安装git

```
sudo apt-get install git
git config --global user.name "name"
git config --global user.email "your@email.com"
```

##  安装编译工具

```
sudo apt-get install build-essential
```

##  安装yarn包管理工具
```
sudo npm install -g yarn
```

##  安装cnpm镜像源

>   下载包直接可以使用 `cnpm install name` 下载

```
sudo npm install -g cnpm
```

##  安装nrm，node下载数据源管理器
```
sudo npm install -g nrm
nrm -v //查看安装版本验证是否安装成功
```
####    可以查看当前所有的下载数据源链接
```
nrm ls 
```
####    测试所有打镜像源的响应速度，然后根据测试我们可以切换我们需要使用的下载源
```
nrm test
nrm use [taobao]
```

# github使用ssh

>   我们使用git去github上传东西，一般都使用ssh免密方式，所以需要首先生成一枚ssh-key密钥，然后在home文件夹进入个人文件夹中，按ctrl+h，会显示所有隐藏文件，打开.ssh文件夹中的id_rsa.pub文件，把里边内容粘贴到github上就可以啦


```
ssh-keygen -t rsa -b 4096 -C "wangpansheng@qq.com" 
```

