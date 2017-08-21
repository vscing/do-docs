---
title: do_SinaWeiBo 组件
---

### do_SinaWeiBo 组件

 支持平台: iOS7.0,Android4.0
 提供sina微博用户登录和分享相关功能

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <font color ='#0092db'>**login**</font>: 使用sina微博登录

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **appId** |<font color ='#808000'>**string**</font> |  | 是||在微博开发平台上申请的appId
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回用户登录信息{'uid': '2806220780', 'access_token': '2.00UNcuDDswn6rCccbb272dc4SsU7dC', 'refresh_token': '2.00UNcuDDswn6rCa14e51baccu2BzTD','expires_in': '1429210895335'}
- 说明: 使用sina微博登录获取用户登录的信息
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**getUserInfo**</font>: 获取用户信息

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **uid** |<font color ='#808000'>**string**</font> |  | 是||
  **accessToken** |<font color ='#808000'>**string**</font> |  | 是||
  **refreshToken** |<font color ='#808000'>**string**</font> |  | 是||
  **expires** |<font color ='#808000'>**string**</font> |  | 是||
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

>##### <font color ='#0092db'>**share**</font>: 分享到新浪微博

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **appId** |<font color ='#808000'>**string**</font> |  | 是||在微博开发平台上申请的appId
  **type** |<font color ='#808000'>**number**</font> | 0 | 是|0|0：默认，图文分享；1：网页分享；2：音乐分享；3：视频分享；4：音频分享；
  **title** |<font color ='#808000'>**string**</font> |  | 是||分享的标题, 最长30个字符
  **image** |<font color ='#808000'>**string**</font> |  | 是||分享后显示的图片，只支持本地图片data://
  **url** |<font color ='#808000'>**string**</font> |  | 是||文件的远程链接, 以URL的形式传入
  **summary** |<font color ='#808000'>**string**</font> |  | 否||分享的消息摘要，最长40个字符
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: true 分享成功，false 分享失败
- 说明: 分享到新浪微博
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件


