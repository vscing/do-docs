---
title: do_BaiduPush 组件
---

### do_BaiduPush 组件

 支持平台: iOS7.0,Android4.0
 集成百度云推送，android支持通知消息、透传消息；iOS支持通知消息

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**getIconBadgeNumber**</font>: 获取未读推送消息数量

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 返回未读推送消息数量
- 说明: 该方法可获取百度推送的未读消息数量；仅支持iOS平台
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**setIconBadgeNumber**</font>: 设置未读推送消息数量

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **quantity** |<font color ='#808000'>**number**</font> |  | 是||
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 该方法可设置百度推送的未读消息数量并显示在应用图标的右上角；仅支持iOS平台
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**startWork**</font>: Push服务初始化及绑定

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 完成Push服务的初始化，并自动完成（触发）bind工作
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**stopWork**</font>: 停止Push服务

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 停止本应用Push服务进程，并自动完成（触发）unbind工作
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**setTags**</font>: 设置标签

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **tag** |<font color ='#808000'>**object**</font> |  | 是||是一个标签数组，每一个标签是一个字符串类型
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 给当前设备设置标签，可从后台按标签分类推送，设置标签会触发setTagsResult事件，在事件中获取设置标签的结果
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**removeTags**</font>: 移除标签

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **tag** |<font color ='#808000'>**object**</font> |  | 是||是一个标签数组，每一个标签是一个字符串类型
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 移除当前设备的标签，不再接收后台按标签分组发送的推送消息，设置标签会触发removeTagsResult事件，在事件中获取移除标签的结果
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <font color ='#e96900'>**bind**</font>: 获取绑定请求的结果，需要注册在app.js或app.lua

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {errorCode:'绑定接口返回值，0-成功',appId:'',userId:'',channelId:''}
- 说明: 获取绑定请求的结果，需要注册在app.js或app.lua
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**unbind**</font>: 获取解除绑定请求的结果，需要注册在app.js或app.lua

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {errorCode:'错误码。0表示从云推送解绑定成功；非0表示失败'}
- 说明: 获取解除绑定请求的结果，需要注册在app.js或app.lua
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**notificationClicked**</font>: 接收通知点击触发，需要注册在app.js或app.lua

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {title:'推送的通知的标题',description:'推送的通知的描述',customContent:'自定义内容，为空或者json字符串'}，iOS不支持title输入，所以也不返回title
- 说明: 接收通知点击触发，需要注册在app.js或app.lua
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**message**</font>: 接收透传消息触发，需要注册在app.js或app.lua，iOS不支持

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {message:'推送的消息',customContent:'自定义内容，为空或者json字符串'}
- 说明: 接收透传消息触发，需要注册在app.js或app.lua，iOS不支持
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**iOSMessage**</font>: 需要注册在app.js或app.lua。分三种情况：1、程序已启动且运行在前台，此时iOS接到推送消息会触发该事件，可在该事件里对推送消息进行处理，否则推送消息只会显示在状态栏中；2、程序已启动但运行在后台，此时只会显示一个横幅的消息提醒，建议用notificationClicked事件处理推送消息；3、程序未运行或者被杀死进程，此时接到推送消息不会触发该事件，而会触发do_Global的launch事件，返回值中type为notification

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {message:'推送的消息',customContent:'自定义内容，为空或者json字符串'}
- 说明: 需要注册在app.js或app.lua。分三种情况：1、程序已启动且运行在前台，此时iOS接到推送消息会触发该事件，可在该事件里对推送消息进行处理，否则推送消息只会显示在状态栏中；2、程序已启动但运行在后台，此时只会显示一个横幅的消息提醒，建议用notificationClicked事件处理推送消息；3、程序未运行或者被杀死进程，此时接到推送消息不会触发该事件，而会触发do_Global的launch事件，返回值中type为notification
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**setTagsResult**</font>: 接收setTags的返回值，需要注册在app.js或app.lua

- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: 添加成功返回true，失败返回false
- 说明: 接收setTags的返回值，需要注册在app.js或app.lua
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**removeTagssResult**</font>: 接收removeTags的返回值，需要注册在app.js或app.lua

- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: 添加成功返回true，失败返回false
- 说明: 接收removeTags的返回值，需要注册在app.js或app.lua
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


