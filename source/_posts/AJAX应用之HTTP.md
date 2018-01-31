---
title: AJAX应用之HTTP
date: 2016-03-14 19:42:23
tags: [ajax,http]
---

#	http 协议。

>	协议就是约束，http协议是w3c制定的，用来约束客户端浏览器与web服务器进行通讯的数据格式,http 协议是基于请求，响应的协议。客户端浏览器给服务器发送一个请求，服务器给客户端一个响应

##	http协议的数据格式分为两部分
-	客户端发送到服务器的请求，称为请求的数据格式。
-	服务器响应给客户端的数据，为响应的数据格式.

-	请求的数据格式，是客户端发送给服务器的，分为四个部分
	1.	请求首行
	2.	请求头
	3.	请求空行
	4.	请求体

###	1.	get请求数据格式

-	请求首行
	```
	GET /day08/code/01http/01get.html HTTP/1.1
	[GET 告诉服务器提交方式]
	[/day08/code/01http/01get.html 告诉服务器，我要去请求的资源的地址]
	[HTTP/1.1 协议的版本] 有两个版本，
	1.0
	1.1
	```

-	请求头 
	```
	Host	127.0.0.1	【请求头的名称，请求头的值】
	Cache-Control	max-age=0	这个做缓存控制的.
	Upgrade-Insecure-Requests	1   没有用过.
	User-Agent	Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/53.0.2785.143 Safari/537.36 	这个是告诉服务器，我客户端浏览器的版本，操作系统的版本
	Accept	text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8	接收，告诉服务器，我客户端可以接收那些数据格式.
	Referer	http://127.0.0.1/day08/code/01http/
	Accept-Encoding	gzip, deflate, sdch   接收的压缩格式. gzip
	Accept-Language	zh-CN,zh;q=0.8		接收的语言
	If-None-Match	"7700000000217a-96-548afe60e947a"
	If-Modified-Since	Fri, 17 Feb 2017 01:33:19 GMT
	```

###	2.	post 请求的数据格式的介绍

-	请求首行
	```
	POST /day08/code/01http/02post.php HTTP/1.1
	```
<!-- more -->
-	请求头
	```
    Host: 127.0.0.1
    内容长度，指的 请求体的长度
    Content-Length: 21
    缓存的
    Cache-Control: max-age=0
    请求的站点的主域名
    Origin: http://127.0.0.1
    Upgrade-Insecure-Requests: 1
    告诉服务器客户端浏览器的版本，操作系统的版本.
    User-Agent: Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/53.0.2785.143 Safari/537.36
    //这个是post 提交独有第一个请求头，如果发送到服务器的数据有中文，会吧中文进行编码
    在发送给服务器，服务器得到数据会自动解码.
    Content-Type: application/x-www-form-urlencoded
    //接收的数据格式
    Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8
    告诉服务器，请求来自于那个页面
    Referer: http://127.0.0.1/day08/code/01http/02post.html
    接收压缩格式
    Accept-Encoding: gzip, deflate
    接收的语言
    Accept-Language: zh-CN,zh;q=0.8
    请求空行 [用来将请求头跟请求体进行一个区分，方便服务器解析数据]
    ```
-   请求体[客户端发送到服务器的数据.]
    ```
    username=dasfadsfdafs
    ```

### 3.  get  跟post 的区别：

1.  get 提交请求的数据都在地址栏中，相对来不安全。

2.  get 请求的数据都请求地址的后面，对请求的数据的大小由限制，限制大概1kb

3.  get 没有请求体

4.  ost 请求的数据在请求体当中，相对来说安全

5.  ost 请求的数据大小没有限制。文件上传，这个必须是post 方式提交

6.  ost 提交有一个特殊的请求头:`Content-Type:application/x-www-form-urlencoded`
可以对请求的数据包含中文的数据进行编码.

7.  get 的请求没有没有请求体，也会少一些请求头，所以它传递到服务端的数据要少一些。性能要高一些。

### 4.  服务器响应给客户端的数据也分为四个部分

1.  响应首行
2.  响应头
3.  响应空行
4.  响应体

####    1. 响应首行
```
协议的版本
200 状态吗 代表ok
HTTP/1.1 200 OK
```

-   实际上我们开发的过程当中还有很多的状态吗
404 代表请求的资源没有找到，以后假设出现404
500 代表服务器内部错误
405 代表请求的方式不支持,如果我的一个php接收post 方式的数据 $_POST
然后你以get 方式去请求，就会出现405
304 请求的资源没有发生改变. 这个是用来做缓存用的.
当我第一次访问http://127.0.0.1/day08/code/01http/01get.html
这个页面，服务器会给我一个响应头.
Last-Modified:Fri, 17 Feb 2017 01:33:19 GMT
告诉客户端浏览器，这个文件的最后修改时间.

当我再次去访问http://127.0.0.1/day08/code/01http/01get.html
会给服务器协议这样的一个请求头
If-Modified-Since:Fri, 17 Feb 2017 01:33:19 GMT
这个时候服务器就会给客户端一个304 的状态吗，你请求的这个资源
http://127.0.0.1/day08/code/01http/01get.html 没有做任何的修改
客户端浏览器得到是304，它就会从本地去读取页面


####    2.  响应头 
告诉客户端服务器端的时间.
Date: Fri, 17 Feb 2017 01:35:58 GMT
告诉客户端服务器的版本
Server: Apache/2.2.21 (Win32) PHP/5.3.10
文件的最后修改时间
Last-Modified: Fri, 17 Feb 2017 01:33:19 GMT

ETag: "7700000000217a-96-548afe60e947a"
Accept-Ranges: bytes
内容的长度
Content-Length: 150
//内容类型，告诉客户端浏览器，我给你返回的是一个文本，html 格式的文本,
客户端浏览器得到这个，就会以html 的方式去解析.
Content-Type: text/html;
header("Content-Type:text/html;charset=utf-8")
####    3.  响应空行
####    4.  响应体

客户端发送到服务器的时候有一个请求头叫做
User-Agent:告诉服务器客户端浏览器的版本，操作系统的版本.

####    5.  响应的头，Refresh 的响应头
服务器给客户端，如果客户端得到这个响应头，它会自动跳转页面.


Referer 的头，告诉服务器，请求来自于那个页面.
    1:广告流量统计，统计到我的网站在那个网站上面打的广告更加有效果。

    2：防盗链，bs 架构，我们可以看到后台的链接，一个连接对应一个资源。
 互联网上创业，有些软件做功能，有些软件做内容。
     一个连接对应一个资源 ，视频行业，最砸钱，谁有视频的资源。视频的资源
 现在都要买版权，都要收费。

     www.kuaibo.com ，进入到快播的一个页面，
 快播视频播放，我就可以引入优酷上面的一个视频资源。
    这个时候会给优酷发送一个请求，就会优酷携带一个请求头
    Referer:www.kuaibo.com
    我在优酷的后台我就可以判断，如果你请求的Referer 的值不是来自于优酷自己的站点
我让你跳转优酷的首页，看看广告.

    http 协议 里面面试的时候一些重点的东西：
            1:get 跟post 的区别
            2:请求的数据格式，
                    特殊的请求头
                    post 提交有一个特殊的请求头
                    Content-Type:"application/-w-form-data"
            3:响应的数据格式。
                    你知道哪些常见的状态吗
                    200
                    404
                    405
                    500
                    304   请求的资源没有发生任何改变，浏览器从缓存里面去找
                    302   请求重定向

                    http://www.tieba.com

                    这个地址会给我一个302 的状态吗
                    它还会给以location 的地址

                    302
                    Location:http://tieba.baidu.com  //响应头：地址

     你在请求开发的过程当成碰到什么乱码问题没有
            1：客户端的数据发送到服务器，
                   1:如果说有中文，我们一般使用post 方式提交

                    //使用js 对魔兽.exe 进行编码. utf-8
                    //服务器根据这个去进行解码. 以utf-8 去解码
                   2:<a href="adsfadsf.php?fileName="魔兽.exe">问价下载 </a>
            2：服务器的数据响应给客户端。

                  1： 当前文件采用的是什么编码
                  2:  然后 给客户端一个响应头 Content-Type:text/html;charset=当前文件的编码







