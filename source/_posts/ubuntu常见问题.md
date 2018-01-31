---
title: ubuntu常见问题处理
tags: [linux,ubuntu ]
date: 2017-04-02 17:46:19
---
<iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width=298 height=52 src="//music.163.com/outchain/player?type=0&id=611811413&auto=1&height=32"></iframe>


##  常见问题处理

### 1.  win10和ubuntu双系统时，硬盘无法加载问题

- 需要依赖于ntfs-3g，如果没有需要先安装这个
```
sudo apt-get install ntfs-3g
```
- 然后只用ntfsfix修复，即可
```
  sudo ntfsfix /绝对路径
```


##  常用软件推荐

### 1.   图片处理:GIMP
- 对于非专业性的图片处理，该款APP已经十分足够了，功能也挺丰富、强大的。

### 2.  视频播放：VLC

- 能够播放rmvb、mp4、avi等多种格式的视频文件，支持快速播放等功能。
- 安装
```
$ sudo add-apt-repository ppa:videolan/stable-daily
$ sudo apt-get update
$ sudo apt-get install vlc
```

### 3.  启动栏：Docky
- ndicator-sysmonitor 这是一款能够实时查看当前系统的CPU、内存、网络、IP等信息
