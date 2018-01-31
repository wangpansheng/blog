---
title: MongoDB数据库配合NodeJS简单使用
tags: [MongoDB,NodeJS]
date: 2017-01-09 19:11:15
---





## 关于 MongoDB

>   我们一般把数据库分为关系型数据库和非关系型数据库，MongoDB就是属于非关系型数据库的一种。

- 官网：https://www.mongodb.com/
- 下载地址：https://www.mongodb.com/download-center?jmp=nav

## 环境安装
- https://www.smartftp.com/support/kb/the-program-cant-start-because-api-ms-win-crt-runtime-l1-1-0dll-is-missing-f2702.html?lang=zh-CN
- http://stackoverflow.com/questions/33265663/api-ms-win-crt-runtime-l1-1-0-dll-is-missing-when-opening-microsoft-office-file


## 启动和关闭 MongoDB 数据库服务程序
mongod.exe 是我们要启动的服务器文件
mongo的客户端去连我们的服务器
- 打开终端，输入 `mongod` 回车
  + `mongod` 命令用来启动 MongoDB 数据服务
  + MongoDB 服务默认将 C:/data/db 目录作为数据目录
  + 所以你需要先在 C:/ 根目录新建一个目录：C:/data/db
  + 当你执行 mongod 命令的时候，默认会去使用 c:/data/db 目录作为数据存储目录
  + 如果你不想使用 c:/data/db 目录
  + mongod --dbpath=路径

- 32位操作系统启动 MongoDB
  + http://jingyan.baidu.com/article/76a7e409e1bb49fc3b6e1516.html
  + `mongod --dbpath 数据存储路径 --journal --storageEngine=mmapv1`
  mongod --dbpath C:/data/db --journal --storageEngine=mmapv1`


## 基础概念

### 数据库

1. 什么是数据？


> 数据是信息的表现形式和载体，可以是符号、文字、数字、语音、图像、视频等。通俗一点，数据就是信息，例如，个人信息、账户信息、家庭信息、企业信息、财务信息等等。


2. 什么是数据库（Database，DB）？

>  数据库是按照数据结构来组织、存储和管理数据的仓库。


3. 为什么要使用数据库？

>    我们需要使用数据库来存储我们网站的数据，然后通过增删改查进行数据交互，数据库，为我们提供了存储数据的仓库。

4. 什么是数据库管理系统（DataBase Management System，DBMS）？

>  数据库管理系统（DataBase Management System，DBMS）是为管理数据库而设计的大型电脑软件管理系统.例如，Oracle、Microsoft SQL Server、Access、MySQL、PostgreSQL、db2等等.我们可以简称这些数据库管理系统为数据库，虽然这种叫法不是很严谨，但是一般人都听的懂。

5. 数据库的分类

- 关系型数据库 sql语言

> 关系数据库管理系统(Relational Database Management System)，
是将数据组织为相关的行和列的系统，而管理关系数据库的计算机软件就是关系数据库管理系统，常用的数据库软件有Oracle、SQL Server、MySQL等。

- 非关系型数据库 nosql
  + 内存数据库 redis
  + 面向文档数据库 mongodb



##  文档 document

> 文档是MongoDB中最基本的单元，里边包含多个键值对。

```json
{name:"zhangsan",age:12}
{name:"lisi"}
```

##  集合 collection

> 集合就是一组文档，特点是动态模式，集合中每一个文档都有可能不一样。但是在实际开发中，最好我们保存一样格式的文档。


##  常用指令

####  1.  列出所有的数据库

```bash
show dbs
```

####  2.  进入或者新建数据库user

```bash
use user
//如果已经有了user数据库，就会进入user数据库
//如果没有user数据库，就会自动新建数据库，如果数据库中没有任何文档，则用show dbs不会显示该仓库
```

####  3.  新建文档

```bash
db.user.insert({name:"wang"})
//在user集合中添加一条文档数据
```

####  4.  查看user集合中的文档

```bash
db.user.find()

```

####    5.  更新文档内容

```bash
db.user.update({name:"wang"},{$set:{name:"ang"}})
```

####    6.  删除文档

```bash
db.user.remove({name:"wang"})
//如果不传入参数，则会直接删除集合
```

### 7.  删除数据库

```bash
use user
db.dropDatabase()
```

##  js链接MongoDb

>  mongodb包提供的方法api和monggodb的命令基本一样，我们可以在nodejs中使用mongodb数据库进行增删改查操作。

- api地址：http://mongodb.github.io/node-mongodb-native/2.2/api