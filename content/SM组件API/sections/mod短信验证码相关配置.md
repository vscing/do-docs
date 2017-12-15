---
title: mob短信验证码相关配置
---

* [一、公共设置](#一)
* [二、应用配置](#二)
* [三、常见返回错误码含义](#三)

<h2 id="一">一、公共设置</h2>
### 1.创建应用
注册并登陆[mob官网地址](http://www.mob.com/) 登陆成功，点击‘进入后台’-‘创建应用’
 ![](../../images/mob001.png)
### 2.填写应用信息
2.1填写应用名称，因为Android和iOS都是使用的同一个应用，只需添加一个即可，名称可依据需要取。
 ![](../../images/mob002.png)
2.2配置应用发送短信权限
2.2.1添加SMSSDK
管理控制台下应用下点击SMSSDK，并点击确定添加：
 ![](../../images/mob003.png)
 ![](../../images/mob004.png)
2.3生成AppKey和APP secret
2.3.1点击应用的概况，显示出该应用的AppKey和APPsecret，复制两个字段值
 ![](../../images/mob005.png)


<h2 id="二">二、应用配置</h2>
1.创建应用 
添加组件do_SMSVerificationCode，添加成功，已添加组件中搜索出该组件，并点击展开秘钥设置，填写之前复制好的key和secret,Android和iOS使用的是一样的。
 ![](../../images/mob006.png)

2.保存成功，打包使用即可。



<h2 id="三">三、常见返回错误码含义</h2>
地址：http://wiki.mob.com/%E9%94%99%E8%AF%AF%E7%A0%81%E8%AF%B4%E6%98%8E-2/


[回到顶部](#top)
