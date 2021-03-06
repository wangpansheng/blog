---
title: git应用之git基本工作流程
date: 2016-06-13 13:58:24
tags: [git,版本控制,工具]
---

##	初始化本地仓库

*	git init

*	如果我们想让git去管理某个目录下的文件，首先需要在该目录下初始化仓库。

##	三种状态

-	学习git之前，我们需要首先了解git管理的3种状态，分别是**已提交**，**已修改**，**已暂存**。

-	这三种状态分别对应三种目录空间，

*	已修改 ->  工作目录
*	已暂存 ->	本地仓库暂存区 通常存放在git目录中的HEAD或INDEX文件中
*	已提交 ->  本地仓库的版本库

##	git基本工作流程

<!-- more -->
*	git的工作流程大概分成三个步骤：

1.	在工作区域修改文件。

2.	将工作目录的文件提交到暂存区域，

3.	最后再将暂存区文件提交的本地版本库，形成一个版本保存起来

*	每一次从暂存区提交到版本库，都会形成一个新的版本库。
