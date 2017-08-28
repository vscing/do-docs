---
title: do_LocalNotification 组件
---

### do_LocalNotification 组件

 支持平台: iOS7,Android14 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_LocalNotification)
 

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#0092db'>同步方法</font>  |[addNotify](#addNotify)| 添加本地通知
<font color ='#0092db'>同步方法</font>  |[removeNotify](#removeNotify)| 移除通知消息
<font color ='#e96900'>事件</font>  |[message](#message)| 需要注册在app.js或app.lua。分三种情况：1、程序已启动且运行在前台，此时接到推送消息会触发该事件，可在该事件里对推送消息进行处理，否则推送消息只会显示在状态栏中（iOS不显示）；2、程序已启动但运行在后台，此时只会显示一个横幅的消息提醒，建议用messageClicked事件处理推送消息；3、程序未运行或者被杀死进程，此时接到推送消息不会触发该事件，而会触发do_Global的launch事件，返回值中type为locaLNotification
<font color ='#e96900'>事件</font>  |[messageClicked](#messageClicked)| 接收通知点击触发，需要注册在app.js或app.lua

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=addNotify><font color ='#0092db'>**addNotify**</font></span>: 添加本地通知

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **notifyTime** |<font color ='#808000'>**string**</font> | 是 | |通知一次时间格式为yyyy-MM-dd HH:mm:ss，iOS平台因系统限制，不同通知的时间不能重复
  **notifyId** |<font color ='#808000'>**number**</font> | 是 | 通知唯一标示|
  **contentText** |<font color ='#808000'>**string**</font> | 是 | |
  **contentTitle** |<font color ='#808000'>**string**</font> | 否 | |iOS平台不支持
  **extra** |<font color ='#808000'>**object**</font> | 否 | |自定义内容不显示在通知中，只在通知中携带，比如{'key1':'value1'}
  **repeatMode** |<font color ='#808000'>**string**</font> | 否 | None|None：默认值按照指定时间执行一次，Minute:每隔一分钟重复执行,Hour:每隔一小时进行重复执行,Day:每隔一天进行重复执行,Week:每隔一周进行重复执行
  **ringing** |<font color ='#808000'>**string**</font> | 否 | |只支持data://目录；不填时默认用系统通知铃声；iOS平台只支持m4a格式，且若铃声超过30秒则无效
  **isVibrate** |<font color ='#808000'>**Boolean**</font> | 否 | true|收到通知时是否震动;iOS平台是否能震动与系统设置相同
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: iOS平台应用在前台时，震动和自定义铃声无效，只触发message事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=removeNotify><font color ='#0092db'>**removeNotify**</font></span>: 移除通知消息

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **notifyIds** |<font color ='#808000'>**object**</font> | 否 | |通知id数组
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 数组不为空，移除数组里notifyId，数组为空移除所有通知，移除后通知不再触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=message><font color ='#e96900'>**message**</font></span>: 需要注册在app.js或app.lua。分三种情况：1、程序已启动且运行在前台，此时接到推送消息会触发该事件，可在该事件里对推送消息进行处理，否则推送消息只会显示在状态栏中（iOS不显示）；2、程序已启动但运行在后台，此时只会显示一个横幅的消息提醒，建议用messageClicked事件处理推送消息；3、程序未运行或者被杀死进程，此时接到推送消息不会触发该事件，而会触发do_Global的launch事件，返回值中type为locaLNotification

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {contentTitle:'通知标题',contentText:'通知内容',notifyId:'通知id',extra:'自定义内容，为空或者json字符串'}
- 说明: 需要注册在app.js或app.lua。分三种情况：1、程序已启动且运行在前台，此时接到推送消息会触发该事件，可在该事件里对推送消息进行处理，否则推送消息只会显示在状态栏中（iOS不显示）；2、程序已启动但运行在后台，此时只会显示一个横幅的消息提醒，建议用messageClicked事件处理推送消息；3、程序未运行或者被杀死进程，此时接到推送消息不会触发该事件，而会触发do_Global的launch事件，返回值中type为locaLNotification
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <span id=messageClicked><font color ='#e96900'>**messageClicked**</font></span>: 接收通知点击触发，需要注册在app.js或app.lua

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {contentTitle:'通知的标题',contentText:'通知的描述',notifyId:'通知id',extra:'自定义内容，为空或者json字符串'}，iOS不支持contentTitle输入，所以也不返回contentTitle
- 说明: 接收通知点击触发，需要注册在app.js或app.lua
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


