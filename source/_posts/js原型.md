---
title: JS原型链总结
date: 2016-10-10 21:22:24
tags: [JS,原型,原型链,函数]
---

## 原型

### 定义：是函数的prototype属性所引用的对象

### 目的：为了同类对象之间的数据共享

### 实际开发的使用

```javascript
  // 1: 定义构造函数，实现函数体部分
	// 使用构造函数 结合原型
	function Person(name, age, sex) {
		// 特有的属性写在这里
	}
	// 2：将该对象相关的方法定义在原型上
	// 将共有的属性（一般是方法）
	Person.prototype.say = function() {};
	Person.prototype.run = function() {};
	// 或者
	Person.prototype = {
		constructor: Person,
		say: function() {},
		run: function() {}
	};
	// 3：创建对象
	var zs = new Person();

```

## 继承

### 定义：指一个对象有权去访问另一个对象上的成员

### 继承的实现

1. 原型式

2. 混入式

3. 借用构造函数

 ```javascript
 function Animal( name, age, sex ) {
 	this.name = name;
 	this.age = age;
 	this.sex = sex;
 }

 function Person( name, age, sex, phoneNo ) {
 	Animal.call( this, name, age, sex );
 	this.phoneNo = phoneNo;
 }

 var zs = new Person( '张三', 18, 'boy', '13838383838' );
 ```


## 原型链

### 本质是通过\__proto__属性连接起来的，体现继承层次关系的。

### 掌握程度
	
1. 给定一个对象，可以迅速找到该对象的原型链

2. 找到该对象的三口之家

## 函数

### 函数是js的一等公民

1. 函数有双重身份
	* 对象-可以添加属性和方法--静态成员
	* 函数-在调用时，就存在四种调用模式；递归调用

2. 可以嵌套使用
	* js使用词法作用域，那么会产生作用域链

3. 可以作为其他函数的实参
	* 回调函数

4. 可以作为其他函数的返回值
	* 闭包

5. 可以限定作用域

6. 可以作为对象的属性值
```

<tag>哈哈哈哈</tag>