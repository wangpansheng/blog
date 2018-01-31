---
title: hexo搭建博客常见问题
tags: [hexo ubuntu]
date: 2016-04-24 16:47:17
---


##  1.  当执行hexo-d时报错,执行以下代码之后,重新提交就可以了

```
git config --global core.autocrlf false
```
<!-- more -->
##  2. ENOSPC报错
>    在ubuntu系统中，执行hexo时，出现ENOSPC报错,可以运行来修复$ npm dedupe，如果还是不行，尝试以下命令：（亲测可行）
```
$ echo fs.inotify.max_user_watches = 524288 | sudo tee -a /etc/sysctl.conf && sudo sysctl -p

```