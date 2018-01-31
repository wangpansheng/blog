---
title: PHP简单入门
date: 2015-08-14 19:52:11
tags:
---
<iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width=298 height=52 src="//music.163.com/outchain/player?type=0&id=611811413&auto=1&height=32"></iframe>

##	php基础

-	定义变量

	-	变量使用$开头，不能以数字开头，
	-	大小写敏感(区分大小写)

-	php代码必须写在`<?php 代码  ?>`,

-	在第一行加上下面这行代码可以防止中文乱码问题

	```php
	header("Content-Type:text/html;charset=utf-8");
	```
-	php变量的类型：	字符串，整型，浮点型，布尔类型，数组

<!--more-->

-	函数	
	-	与js基本一致
	-	函数的形参可以设置一个默认值。
	```
	function foo($username = "zs") {
		echo "你好".$username;
	}
	foo();
	```

-	

##	数组

-	php里面有两种类型的数组，普通数组和关联数组

1.	普通数组

	-	定义
	```
	$arr1 = array("zs","ls");
	```
	-	数组没有length属性，
	-	遍历数组,使用for循环，可以得到数组的长度
	-	php有一个函数可以获取数组的长度，count($arr);

2.	关联数组
	
	-	以键值对的方式进行存储的数组，我们叫做关联数组，
	```php
	$array = array("key" => "value");
	$array["key];
	//通过key可以获取值
	```
3.	二维数组

	-	数组里边还有数组

## 输出打印	
-	php提供了三个用来输出的方法

1.	echo ""; 	用来输出字符串的

2.	print_r();	用来输出数组或者对象的。

3.	var_dump();	这个也是用来输出数组里面的详细信息

##	php常见函数方法

1.	count();	得到数组长度

2.	in_array();	
	-	判断数组中是否存在某个元素，这个是用在普通数组当中的

3.	array_key_exists();	
	-	检测数组中是否存在某个key，这个用在关联数组中

4.	file_get_contents();	
	-	读取文件里边的内容，读取出来的是字符串，

5.	move_upload_file();	移动上传的文件


##	表单处理

-	name属性 是用来提供给服务端接收数据而设置的

-	action属性 设置接收数据的处理程序

-	method属性	设置发送数据的方式

-	当上传文件时，必须设置 `enctype="multipart/form-data"`,且只能使用post方式

-	$_GET	接收get传来的数据

-	$_POST	接收post传来数据

-	$_FILES	接收上传的文件

##	get和post提交

1.	get

	-	点击超链接，表单提交默认方式就是get，地址栏输入地址，

	-	传递到服务端的都是参数，参数值，可以传递多个参数参数值
	-	第一个必须是？ 参数名=参数值
	-	可以发送多个参数到服务器
	-	假设我要发送多个数据，
	-	第二个参数之前添加&字符
	```
	<a href="01.php?username=zs&age=12"></a>
	```
	-	在php要对请求进行处理，处理我们分为三个步骤，

	1.	接收请求，接收客户端传递到服务端的数据，
		-	如果客户端是get方式提交，用$_GET去接收数据，对应的值是一个数组，是一个关联数组。
	2.	处理请求：	接收到数据之后具体做什么，就是要使用php去操作了。
	3.	响应处理，给客户端一个响应

2.	post提交

	-	表单提交一般都是使用post
	```
	<!--post 提交，我需要表单提交，设置成post-->
    <form action="02post.php" method="post">
        用户名:<input type="text" name="username">
        <input type="submit" value="post 提交">
    </form>
	```
	- 服务端处理
	1.	接收请求
	```
	$username = $_POST["username"];
	```
	2.	处理请求
	-	php后端处理数据
	3.	完成响应
	-	返回信息到客户端

##	文件上传

####	前端页面

-	必须满足以下条件才可以上传文件

1.	必须是表单提交

2.	表单里面必须有 input type="file"

3.	必须是post方式提交

4.	必须设置 `enctype="multipart/form-data"`属性

