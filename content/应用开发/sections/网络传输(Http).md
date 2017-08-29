---
title: 网络传输(Http)
---
### 网络传输(Http)
<mark>注意：官方推出了类似ajax的封装js库，如果对ajax熟悉，可以直接使用</mark>，[下载地址](http://github.com/do-js)

**do_Http**组件就是实现http/https协议的组件.
>首先要说明一下，Do平台只是一个移动端开发的平台，不涉及任何后台服务端的技术，你可以使用你自己任何熟悉的语言和技术来实现服务端，do_Http组件就是用来和服务端通信。

http是一个最基础的应用层的通信协议，开发者应该很熟悉，但是在QQ群和很多同学讨论，发现有不少人没有很好的理解http。我这里再简单描述一下，熟悉的人就跳过吧。
###协议的介绍

所谓`协议`就是指http的客户端和服务端的一个协商的一个标准，一个规范，是一个可以用文字来描述能用纸来记录下来的文档。

比如说假设一个规范规定

     客户端发送“hi”给服务端，服务端必须回答“hi client"
	 客户端发送“hello”给服务端，服务端必须回答“hello hello”
	 ......

那么不管你客户端是用Java还是什么语言，服务端是用C#还是别的语言，都必须按照这个规范，都必须客户端发`hi`，服务端返回`hi client`。

当然http协议要复杂很多，详细的可以参考http协议的介绍。常用的语言比如Java，C#，ios等等都有这个协议的实现，do_Http也一样。这些语言实现的方式各有不同，有不同名字的属性，事件，方法，但是本质上都是实现这套规范。


###HTTP通信的过程
- 客户端利用一些属性事件方法，拼接出一个请求报文。这个报文是有一定格式的，而且这个格式必须正确。报文通常分报文header和报文body。它的大概格式类似如下例子：

```text
POST /sn/index HTTP/1.1
Accept: */*
Accept-Language: zh-cn
host: localhost

Content-Type: application/x-www-form-urlencoded
Content-Length: 12
Connection:close

sn=123&n=asa
```
do_Http组件提供了一些属性和方法来拼接这个请求报文：

	body ：post的数据
	contentType：post的数据格式
	method：数据请求的方法，基本的是GET，POST，也支持DELETE，PUT等标准
	timeout：毫秒为单位的超时设置
	url：请求的地址
	setRequestHeader():设置header里的属性和属性值，可以执行多次，每次增加一条

- 客户端把报文发送到服务端，do_Http组件提供了4个方法来处理，本质上这4个方法都是一样，只不过为了方便，分成了4个应用不同的场景。


	request()：最基本的请求方法，通常只能发送文本
	download():可以直接发送一个请求把服务端的文件下载下来保存到手机端，可以监控下载的进度。
	upload():可以把本地的文件上传到服务端，可以监控上传的进度。
	form():有点类似request和upload的混合，它可以同时发送多个文本也能发送多个文件。类似 web的表单提交。

- 服务端接受到客户端发送过来的请求报文，然后解析成数据。这一块和do平台无关，可以用你自己熟悉的后台开发语言来实现。

- 服务端对请求作出相应处理之后，返回一个 响应报文给前端，这个报文也是有格式的，报文通常分报文header和报文body。类似下面的格式：

```html
HTTP/1.1 200 OK
Date: Sat, 31 Dec 2005 23:59:59 GMT
Content-Type: text/html;charset=ISO-8859-1
Content-Length: 122

＜html＞
＜head＞
＜title＞Wrox Homepage＜/title＞
＜/head＞
＜body＞
＜!-- body goes here --＞
＜/body＞
＜/html＞
```
这个步骤也和do平台无关。


- 客户端接收服务端返回的响应报文做相应的处理。
do_Http提供4个接口来处理返回的数据


	fail：请求出错事件
	progress：发送和接受数据时可以用这个监控进度
	result:发送后接受完数据会触发这个事件
	success：只有接受到状态码200才会触发这个事件，这个事件不够完善，还是用result事件更合适


###完整的测试示例
1. 客户端：分别实现get，post，upload，form，download的http请求。本质上其实就2种get和post。do_http还支持put,delete等，这里没有演示。
为了看到请求的报文，服务端会把请求的报文作为响应的报文数据一部分返回到客户端。需要输入你自己搭建的服务端的IP地址和端口。
![](../../images/http001.png)

2. 服务端利用java的servlet来模拟一个服务端，使用的jetty容器，可以不用安装tomcat服务，直接当成一个应用可以运行。就是作为大家做服务端的参考和调试用。源代码在[GIT](https://github.com/do-project/code4do/tree/master/HttpService)。服务端启动一个8080端口的web服务。
详细的示例参考[这里](http://doc.deviceone.net/web/doc/code4do/do_http.htm)

[回到顶部](#top)
