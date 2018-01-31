---
title: 框架封装之Ajax
tags: [框架封装，ajax]
date: 2016-11-17 09:31:26
---
 

##	ajax请求步骤

1.	创建请求对象
2.	格式化数据
3.	与服务器建立连接
4.	监听请求状态
5.	发送请求

##	创建请求对象

1.	原生方法
	-	w3c:XMLHttpRequest
	-	IE：ActiveXObject


##	封装Ajax模块

1.	确定Ajax配置的默认值
	-	url => ""
	-	type => "get"
	-	data => {}
	-	success => null
	-	fail => null
	-	async => true
	-	dataType => "json"
	-	contentType => "application/x-www-form-ulencoded"

2.	ajax默认配置放在哪？
	-	要用一个对象来存储上述Ajax配置信息，像jQuery一样，将其放到工厂函数上；
	放在工厂函数jq上

<!-- more -->
###	改造extend方法

1.	如果只传入一个参数，给this扩展成员，
2.	或者传入两个以上，就是给第一个参数扩展成员，，

##	跨域
1.	jsonp跨域的一种方式，缺点：只能发送跨域get请求

2.	本质：利用script标签的src属性可以跨域的特性

3.	实现流程：
	-	创建script标签，添加到head下
	-	常见一个全局函数，用来处理服务器响应的数据
	-	指定script标签src的属性值，同时将全局函数发送到服务区
	-	要与后台人员沟通，将发送全局函数的参数名告诉后台人员
	-		
4.	实现步骤：
	-	常见请求对象，script标签
	-	格式化数据
	-	创建一个全局函数，将函数添加到data内，
	-	监听请求的状态-》使用timeout来做请求状态的监听，如果在超过时间内，表示成功，否则就报超时，
	-	发送请求，-》给script标签指定src属性值