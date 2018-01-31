---
title: 快速搭建hexo个人博客站点
date: 2016-03-10 23:51:18
tags: [ hexo,个人博客,技术分享 ]
---

##  1.  首先安装hexo命令行，

```
sudo npm install hexo-cli -g
//安装之后输入下面命令验证是否安装成功
hexo -v
```

##  2.  接着我们找一个我们打算把博客放在打文件夹中，打开终端

```
//输入下面命令，会自动部署博客框架
hexo init [blog]
//blog 就是我们防止博客文件的文件夹，可以不写，就会在打开终端打目录下直接创建
//完成之后，进入blog文件夹安装依赖
npm install
```

##  3.  本地预览

```
hexo s
```
输入命令之后，看到下面这行提示之后，就可以再浏览器输入地址，预览配置好的页面。
```
INFO  Start processing
INFO  Hexo is running at http://localhost:4000/. Press Ctrl+C to stop.
```

<!-- more -->
##  4.  创建新文章

```
hexo new 文章标题
```

输入命令之后，就可以再\hexo\source\_posts\路径下看到自己输入名字的md文件，文章标题默认就是创建时候写的。

##  5. 生成部署

```
hexo g
```

输入命令之后，会生成静态页面，

##  6. 提交

```
hexo d
```

输入命令，可以把生成的静态页，提交到自己的github主页上。


