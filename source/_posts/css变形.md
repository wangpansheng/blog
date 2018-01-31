---
title: css变形
tags: [css3]
date: 2017-07-11 09:23:13
---
<h1>css变形</h1>

>   我们可以借助css3实现图片元素的倾斜、缩放、移动、以及翻转效果。

##  1.  tranfrom属性语法

>   tranfrom属性让元素在一个坐标系统中变形，包含一系列变形函数，可以移动、旋转和缩放元素。


```css
    transfrom: none | <transfrom-function>
```

-   默认值为:none,表示不对元素进行变形;
-   也可以指定一个或者多个变形函数，以空格分开。如：rotate、scale、trasnslate;

##  2.  变形函数介绍

>   所有的2D变形函数可以应用于3D变形规范中。

    函数 | 功能描述
    ----|-------
    translate() | 移动元素，可以根据X轴和Y轴坐标重新定位自己的位置，有tranlateX(),translateY()
    scale() | 缩小或者方法元素，可以使元素尺寸发生变化，有scaleX()和scaleY()
    rotate() | 旋转元素
    skew() | 让元素倾斜，在此基础上有两个扩展函数，skewX()和skewY()
    matrix()|定义矩阵变形，基于X轴和Y轴坐标重新定位元素位置

