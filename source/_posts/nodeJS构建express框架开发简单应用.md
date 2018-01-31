---
title: NodeJS构建express框架开发简单应用
tags: [NodeJS express]
date: 2017-01-10 21:39:28
---

>   使用node express简单构建，配合MongoDB数据库，实现简单的增删改查操作

## 首先我们需要构建express本地框架结构

```npm
    express demo
    //在demo文件夹中构建express结构
```

##  然后我们运行一下，

```
    npm start
```
执行之后，我们在浏览器打开localhost:3000就可以看到初始化的页面，

##  因为我们是使用 MongoDb数据库，所以需要安装mongodb的nodeJS包，

mongodb包的api基本上mongodb数据库的命令行操作命令差不多，所以，如果你比较清楚命令行操作命令，使用起来就会非常方便，
```
//安装mongodb包
npm install mongodb --save
//安装依赖包
npm install
```
至此，所有的准备工作基本完成，当然，前提你已经装好mongodb数据库，而且在使用的时候，需要全程开启数据库服务器。mongodb数据库的安装，我以前有文章有介绍过，有兴趣的可以去看看。

## 我们使用MVC架构来实现针对数据库的增删改查，

-   我们创建一个文件夹 module，就是连接控制数据库的文件。
-   我们使用routes来代替controller同样的功能，来连接视图层和数据库的连接。
-   我们的整体逻辑是，我们路由中添加一个get请求，请求中调用module中的一个操作方法，然后module中的添加方法，再去调用数据库连接，然后在使用操作api操作数据库。
##  在module中首先连接到数据库

```js
//得到MongoClient对象
var MongoClient = require("mongodb").MongoClient;
var url = "数据库主机ip:port/数据库名"

module.exports = function(callback){

    MongoClient.connect(url,function(err,db){
        if(err){
            //代表连接失败
        return callback(err);
        }
        callback(null,db)
    })
}

```

