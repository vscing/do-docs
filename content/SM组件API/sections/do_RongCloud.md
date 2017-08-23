---
title: do_RongCloud 组件
---

### do_RongCloud 组件

 支持平台: iOS7,Android14
 融云即时通信

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**setTitleBarColor**</font>: 设置标题栏颜色,不调用此方法默认标题栏颜色为蓝色

- 参数:

  名称 | 类型 |是否必填|缺省值|说明
  ---- |-------------  |--------------|--------|------
  **color** |<font color ='#808000'>**string**</font> |  | 是|
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**setTitleColor**</font>: 设置标题颜色,不调用此方法默认标题颜色为白色

- 参数:

  名称 | 类型 |是否必填|缺省值|说明
  ---- |-------------  |--------------|--------|------
  **color** |<font color ='#808000'>**string**</font> |  | 是|
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**logout**</font>: 退出登录

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 退出登录后,接收不到推送消息
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**getLatestMessage**</font>: 获取会话列表最新一条消息

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回格式为[{userId:'qwert',message:'123456',receivedTime:'1500346713',sentTime:'1500346715',isSend:true},{userId:'wwee',message:'erwere',receivedTime:'1500346713',sentTime:'1500346715',isSend:false}]，其中userId为消息用户id；message为消息内容，若为语言或图片消息时，仅返回[图片]或[语音]；receivedTime和sentTime为消息接收和发送的时间，类型为long型；isSend为消息是否发送成功，当最新一条消息为接收消息时，不返回该字段
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <font color ='#0092db'>**login**</font>: 用户登录

- 参数:

  名称 | 类型 |是否必填|缺省值|说明
  ---- |-------------  |--------------|--------|------
  **appKey** |<font color ='#808000'>**string**</font> |  | 是|
  **token** |<font color ='#808000'>**string**</font> |  | 是|
  **extraData** |<font color ='#808000'>**string**</font> |  | 否|仅支持Android平台，用来配置Android推送的一些数据，目前用到小米推送，集成后推送整体到达率会大大提升，格式为{'xiaomi':{'appId':'KWSFSKDFBKS','appKey':'DFGHFHFFRT'}}
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 登录成功返回当前登录的用户id,登录失败返回错误信息
- 说明: 使用token登录
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**openConversation**</font>: 打开单个会话

- 参数:

  名称 | 类型 |是否必填|缺省值|说明
  ---- |-------------  |--------------|--------|------
  **userId** |<font color ='#808000'>**string**</font> |  | 是|
  **title** |<font color ='#808000'>**string**</font> |  | 是|通常是用户名
  **headPortrait** |<font color ='#808000'>**string**</font> |  | 否|支持本地文件,data:// source:// 打头的URI格式和网络图片,不写为默认头像
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 根据用户id打开会话
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**openConversationList**</font>: 打开会话列表

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**openGroupConversation**</font>: 打开群聊会话

- 参数:

  名称 | 类型 |是否必填|缺省值|说明
  ---- |-------------  |--------------|--------|------
  **groupId** |<font color ='#808000'>**string**</font> |  | 是|
  **title** |<font color ='#808000'>**string**</font> |  | 是|通常是群组名
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 根据groupId打开会话
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**setUserInfo**</font>: 设置当前用户信息

- 参数:

  名称 | 类型 |是否必填|缺省值|说明
  ---- |-------------  |--------------|--------|------
  **nickName** |<font color ='#808000'>**string**</font> |  | 否|
  **headPortrait** |<font color ='#808000'>**string**</font> |  | 否|支持本地文件,data:// source:// 打头的URI格式和网络图片,不写为默认头像
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: 设置成功返回true，失败返回false
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件

>###### <font color ='#e96900'>**message**</font>: 接收到新消息触发事件

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回的信息为{ conversationType : '所属会话类型', messageId : '消息的唯一id', fromUserId:'发送者id', sendTime : '发送时间', receiveTime : '接收时间' , messageType : '消息类型(text,location,file,image,voice)', messageContent : '消息内容'  }
- 说明: 接收到新消息触发事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**userPortraitClick**</font>: 头像点击事件

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回的信息为{ conversationType : '当前所属会话类型', userId : '所点击头像的用户id',userName : '所点击头像的用户昵称'  }
- 说明: 头像点击事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


