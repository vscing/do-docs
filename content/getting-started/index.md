---
title: Getting Started
---
## do_Http组件

当前版本:3.1
支持平台: iOS7.0, Android
说明: 用于执行http或https请求。这个是非常基础的组件,所有和服务端web交互都需要使用,通常使用的方式就是构建一个do_Http对象,然后设置它的属性,最后通过request方法或其它方法触发请求.

<span id = "top">目录</span>

[TOC]

#### 1. 属性

###### 1.1 **body**: post请求的内容
- 数据类型 :	任何
- 默认值 : 无
- 说明 :	请求数据，method为get、delete时不支持

###### 1.2 **contentType**: 请求的内容类型
- 数据类型 :	string
- 默认值 : 无
- 说明 :	请求数据，method为get、delete时不支持

```javascript
	var button = ui("button-id");
	var imageview = ui("imageview-id");
	var listview = ui("listview-id1");
	var label = ui("aaa");
	...

```
[回到顶部](#top)

#### 2. 同步方法

##### 2.1 **download**: 下载文件到本地
- 参数

 名称 | 数据类型 |默认值|是否必填|缺省值|说明
 ---- |-------------  |----------|--------------|--------|------
 **path** |string|无|是|无|保存的文件地址,只支持data://开头的地址
- 返回值: 无
- 返回值类型: string
- 说明: 从服务端下载一个文件到本地

##### 2.2 **download1**: 下载文件到本地,支持断点续传
- 参数

 名称 | 数据类型 |默认值|是否必填|缺省值|说明
 ---- |-------------  |----------|--------------|--------|------
**path** |string | 无 | 是|无|保存的文件地址,只支持data://开头的地址
**taskId** |string | 无 | 是|无|任务id
- 返回值: 无
- 返回值类型: string
- 说明: 从服务端下载一个文件到本地
- 示例:

```javascript
	var button = ui("button-id");
	var imageview = ui("imageview-id");
	var listview = ui("listview-id1");
	var label = ui("aaa");
	...

```
[回到顶部](#top)
#### 3. 异步方法

##### 2.1 **upload**: 下载文件到本地
- 参数

 名称 | 数据类型 |默认值|是否必填|缺省值|说明
 ---- |-------------  |----------|--------------|--------|------
**path** |string | 无 | 是|无|保存的文件地址,只支持data://开头的地址
- 返回值: 无
- 返回值类型: string
- 说明: 从服务端下载一个文件到本地

##### 2.2 **upload1**: 下载文件到本地,支持断点续传
- 参数

 名称 | 数据类型 |默认值|是否必填|缺省值|说明
 ---- |-------------  |----------|--------------|--------|------
**path** |string | 无 | 是|无|保存的文件地址,只支持data://开头的地址
**taskId** |string | 无 | 是|无|任务id, 支持枚举类型值
- 返回值: 无
- 返回值类型: string
- 说明: 从服务端下载一个文件到本地
- 示例:

```javascript
	var button = ui("button-id");
	var imageview = ui("imageview-id");
	var listview = ui("listview-id1");
	var label = ui("aaa");
	...

```

[回到顶部](#top)
#### 4. 事件

###### 4.1 **success**: 请求成功事件
- 返回类型 : 任何
- 返回值: 返回http接收到的数据
- 说明 :

###### 4.2 **result**: 请求结束事件
- 返回类型 : 任何
- 返回值: 返回http接收到的数据
- 说明 :

```javascript
	var button = ui("button-id");
	var imageview = ui("imageview-id");
	var listview = ui("listview-id1");
	var label = ui("aaa");
	...

```
[回到顶部](#top)
