---
title: do_HuanXinIM 组件
---

### do_HuanXinIM 组件

* 支持平台: iOS7.0,Android4.0
环信即时通讯IM

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**enterChat**</font>: 进入聊天

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **userID** |<font color ='#808000'>**string**</font> |  | 是||会话用户ID
  **userNick** |<font color ='#808000'>**string**</font> |  | 是||会话用户昵称
  **userIcon** |<font color ='#808000'>**string**</font> |  | 否||仅支持网络图片
  **selfNick** |<font color ='#808000'>**string**</font> |  | 否||仅支持网络图片
  **selfIcon** |<font color ='#808000'>**string**</font> |  | 否||仅支持网络图片
  **tag** |<font color ='#808000'>**string**</font> |  | 否||可随消息发送到消息接受者receive监听中
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 进入与指定用户发起聊天
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**logout**</font>: 注销用户

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <font color ='#0092db'>**login**</font>: IM用户登录

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **username** |<font color ='#808000'>**string**</font> |  | 是||
  **password** |<font color ='#808000'>**string**</font> |  | 是||
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 登录是否成功，返回信息为{state:' 0 成功 | 1 失败 ',message:' 回执信息 '}
- 说明: 使用用户名、密码登录，需先使用环信账户创建一个应用，然后在该应用下创建或通过接口注册IM用户
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件

>###### <font color ='#e96900'>**receive**</font>: 接收到新消息触发事件

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回的信息为{ from : '会话用户ID', nick : '会话用户昵称', icon:'会话用户头像', message : '会话消息内容', time : '消息发送时间' , type : '消息类型', tag : '自定义文本'  }
- 说明: 接收到新消息触发事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**connection**</font>: 监听连接状态

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {state:1 显示帐号已经被移除 | 2 显示帐号在其他设备登陆 | 3 连接不到聊天服务器  | 4 当前网络不可用 请检查网络设置 }
- 说明: 监听连接状态
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**chatStatusChanged**</font>: 聊天状态改变

- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 1 : 已进入聊天状态; 0 : 未进入聊天状态
- 说明: 聊天状态改变
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


