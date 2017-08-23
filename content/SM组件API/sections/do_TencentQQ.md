---
title: do_TencentQQ 组件
---

### do_TencentQQ 组件

 支持平台: iOS7.0,Android4.0
 提供QQ登录和分享相关的功能

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <font color ='#0092db'>**login**</font>: 使用QQ登录

- 参数:

  名称 | 类型 |是否必填|缺省值|说明
  ---- |-------------  |--------------|--------|------
  **appId** |<font color ='#808000'>**string**</font> |  | 是|在QQ互联申请的appId
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回用户登录的信息{"ret": 0,"pay_token": "0778657200B8F00BAFD7F4BB07814C25","pf": "desktop_m_QQ-10000144-android-2002-","query_authority_cost": 288,"authority_cost": -831427405,"openid": "7FA197F8DCDD7AAF58ADFB78ED5EAC1F","expires_in": 7776000,"pfkey": "357daa137145123b502e4617986ebef3","msg": "","access_token": "08883692C36350C78D7E0F25CBC796F6","login_cost": 342}
- 说明: 使用QQ登录获取用户登录的信息
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**getUserInfo**</font>: 获取用户信息

- 参数:

  名称 | 类型 |是否必填|缺省值|说明
  ---- |-------------  |--------------|--------|------
  **token** |<font color ='#808000'>**string**</font> |  | 是|
  **expires** |<font color ='#808000'>**string**</font> |  | 是|
  **openId** |<font color ='#808000'>**string**</font> |  | 是|
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回是一个String,里面包含了用户的基本信息，头像，昵称...
- 说明: 获取用户信息
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**logout**</font>: 注销

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: true 注销成功，false 注销失败
- 说明: 注销登录
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**shareToQQ**</font>: 分享到QQ好友

- 参数:

  名称 | 类型 |是否必填|缺省值|说明
  ---- |-------------  |--------------|--------|------
  **appId** |<font color ='#808000'>**string**</font> |  | 是|在QQ互联申请的appId
  **type** |<font color ='#808000'>**number**</font> | 0 | 是|0：默认，图文分享；1：纯图分享，只支持本地图；2：音乐分享；3：应用分享
  **title** |<font color ='#808000'>**string**</font> |  | 是|分享的标题, 最长30个字符
  **url** |<font color ='#808000'>**string**</font> |  | 否|分享后点击文本后打开的地址
  **image** |<font color ='#808000'>**string**</font> |  | 否|分享后显示的图片，纯图分享时候不能为空，仅支持本地图片data://目录
  **summary** |<font color ='#808000'>**string**</font> |  | 否|分享的消息摘要，最长40个字
  **audio** |<font color ='#808000'>**string**</font> |  | 否|音乐文件的远程链接, 以URL的形式传入, 不支持本地音乐
  **appName** |<font color ='#808000'>**string**</font> |  | 否|
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: true 分享成功，false 分享失败
- 说明: 分享到QQ好友
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**shareToQzone**</font>: 分享到QQ空间

- 参数:

  名称 | 类型 |是否必填|缺省值|说明
  ---- |-------------  |--------------|--------|------
  **appId** |<font color ='#808000'>**string**</font> |  | 是|在QQ互联申请的appId
  **type** |<font color ='#808000'>**number**</font> | 0 | 是|0：默认，图文分享；1：应用分享
  **title** |<font color ='#808000'>**string**</font> |  | 是|分享的标题, 最长200个字符
  **url** |<font color ='#808000'>**string**</font> |  | 是|分享后点击文本后打开的地址
  **image** |<font color ='#808000'>**string**</font> |  | 是|分享后显示的图片，仅支持本地图片data://目录
  **summary** |<font color ='#808000'>**string**</font> |  | 否|分享的消息摘要，最长600个字
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: true 分享成功，false 分享失败
- 说明: 分享到QQ空间
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件


