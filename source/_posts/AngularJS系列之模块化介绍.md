---
title: AngularJS系列之模块化介绍
date: 2016-07-20 13:07:39
tags:
---
## 模块化介绍

* 通过AngularJS构建应用时，是以模块化的方式组织的，即将整个应用划分成若干个模块，每个模块都各有其职责，最终组合成一个整体。
* 采用模块化的组织方式，可以最大程度的实现代码的复用，可以像搭积木一样进行开发。

## 定义应用

* 通过为任一HTML标签添加ng-app属性，可以指定一个应用，表示此标签所包裹的内容都属于应用的一部分。

  ```angular2html
  <!--为html标签添加ng-app表明整个文档都是应用-->
  <!--ng-app属性可以不赋值，但是要关联相应模块时则必须赋值-->
  <html lang="zh-CN" ng-app="App"></html>
  ```
## 定义模块

* AngularJS提供了一个全局对象angular，在此全局对象下存在若干方法，其中angular.module()方法用来定义一个模块。
  
  ```javascript
  //通过module方法定义模块
  //需要传递两个参数，第一个表示模块的名字，
  // 第二个表示此模块依赖的其它模块
  var app = angular.module("app",[]);
  ```
  注：应用本质也是一个模块（一个比较大的模块）；
  
## 定义控制器

<!-- more -->
* 控制器（Controller）作为连接模型（model）和视图（view）的桥梁存在，所以当我们定义好了控制器以后，也就定义好了模型和视图。

  ```javascript
  //app是一个模型实例对象
  //通过这个实例对象定义控制器，需要两个参数
  //第一个参数表示控制器名称，
  //第二个参数是一个数组，这个数组除最后一个单元是函数外，其余都是字符串，标明此控制器的依赖关系
  app.controller('studentController',['$scope',function($scope) {
    //模型（model）
    $scope = [
      {name: "李白", sex: '男', age: "23"},
      {name: '华仔', sex: '男', age: '34'}
    ]
  }])
  ```
  
* 模型数据时要展示到视图上的，所以需要将控制器关联到视图上，通过为HTML标签添加ng-controller属性并赋值相应的控制器的名称，就确立了关联关系，

  ```html
  <!--添加ng-controller属性，并赋值为相应的控制器名称-->
   <table ng-controller="StudentController">
   <tr>
   <th>姓名</th>
   <th>性别</th>
   <th>年龄</th>
   </tr>
   <tr ng-repeat="student in students">
   <td>{{student.name}}</td>
   <td>{{student.sex}}</td>
   <td>{{student.age}}</td>
   </tr>
  </table>
  ```

* 以上为AngularJS最基本的MVC工作模式。