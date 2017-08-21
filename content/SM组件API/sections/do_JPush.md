---
title: do_JPush 组件
---

### do_JPush 组件

 支持平台: iOS7,Android14
 集成极光推送，支持通知和自定义消息(应用在前台时触发)，受极光sdk的影响，Android平台在应用未启动的情况下无法收到推送消息，但发送的消息不会丢失，会在应用启动后送达

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**getIconBadgeNumber**</font>: 获取未读推送消息数量

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 返回未读推送消息数量
- 说明: 该方法可获取极光推送的未读消息数量；仅支持iOS平台
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
- 说明: 该方法可设置极光推送的未读消息数量并显示在应用图标的右上角；仅支持iOS平台
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**resumePush**</font>: 恢复推送服务

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 调用了此API后，极光推送完全恢复正常工作；仅支持Android平台
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**stopPush**</font>: 停止推送服务

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 调用了本API后，极光推送服务完全被停止；仅支持Android平台
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**getRegistrationID**</font>: 获取注册ID

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回触发didLogin事件后返回的RegistrationID
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**setRinging**</font>: 设置自定义消息铃声

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **ringing** |<font color ='#808000'>**string**</font> |  | 是||只支持data://目录，支持wav,m4a格式（音频文件需小于30秒,超过30秒IOS端会使用默认铃声）.Android端自定义铃音生效的推送消息类型为'自定义消息';iOS端自定义铃音生效的推送消息类型为'发送通知',然后在设置界面中展开'可选设置'，更改'sound'为ringing参数的音频文件名
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <font color ='#0092db'>**setTags**</font>: 设置标签

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **tag** |<font color ='#808000'>**object**</font> |  | 是||是一个标签数组，每一个标签是一个字符串类型。不支持增量添加，每次添加都会覆盖之前的标签；如果数组为空，则为删除所有的tag
- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: 添加成功true,失败false
- 说明: 给当前设备设置标签，可从后台按标签分类推送
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**setAlias**</font>: 设置别名

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **alias** |<font color ='#808000'>**string**</font> |  | 是||alias 命名长度限制为 40 字节，设置为空表示取消之前的设置，每次调用设置有效的别名，覆盖之前的设置
- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: 添加成功true,失败false
- 说明: 给当前设备设置别名，每个用户只能指定一个别名
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件

>###### <font color ='#e96900'>**didConnect**</font>: 已连接，需要注册在app.js或app.lua

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 初始化连接成功
- 说明: 已连接，需要注册在app.js或app.lua
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**didClose**</font>: 未连接，需要注册在app.js或app.lua

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 断开连接，当无网络时会触发或者被极光关闭
- 说明: 未连接，需要注册在app.js或app.lua
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**didLogin**</font>: 返回登陆成功后的RegistrationID，在极光的后台可以根据这个id进行个推，需要注册在app.js或app.lua

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {registrationID:'1114a89792aa12dfd2c'}
- 说明: 返回登陆成功后的RegistrationID，在极光的后台可以根据这个id进行个推，需要注册在app.js或app.lua
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**message**</font>: 需要注册在app.js或app.lua。分三种情况：1、程序已启动且运行在前台，此时接到推送消息会触发该事件，可在该事件里对推送消息进行处理；2、程序已启动但运行在后台，此时ios只会显示一个横幅的消息提醒，android会在状态栏中显示消息提醒，建议用messageClicked事件处理推送消息；3、程序未运行或者被杀死进程，此时接到推送消息不会触发该事件，而会触发do_Global的launch事件，返回值中type为notification，若消息未读，会在状态栏中显示

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {title:'推送的通知的标题',content:'推送的消息',extra:'自定义内容，为空或者json字符串'}；iOS不支持title输入，所以也不返回title；当android发送推送消息时不填写标题，title则会获取到应用名称
- 说明: 需要注册在app.js或app.lua。分三种情况：1、程序已启动且运行在前台，此时接到推送消息会触发该事件，可在该事件里对推送消息进行处理；2、程序已启动但运行在后台，此时ios只会显示一个横幅的消息提醒，android会在状态栏中显示消息提醒，建议用messageClicked事件处理推送消息；3、程序未运行或者被杀死进程，此时接到推送消息不会触发该事件，而会触发do_Global的launch事件，返回值中type为notification，若消息未读，会在状态栏中显示
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**customMessage**</font>: 自定义推送消息，收到自定义消息并且应用在前台时触发，需要注册在app.js或app.lua

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {content:'推送的消息',extra:'自定义内容，为空或者json字符串'}
- 说明: 自定义推送消息，收到自定义消息并且应用在前台时触发，需要注册在app.js或app.lua
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**messageClicked**</font>: 点击通知消息触发，需要注册在app.js或app.lua

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {title:'推送的通知的标题',content:'推送的消息',extra:'自定义内容，为空或者json字符串'}，iOS不支持title输入，所以也不返回title
- 说明: 点击通知消息触发，需要注册在app.js或app.lua
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


