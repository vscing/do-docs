---
title: do_TencentWX 组件
---

### do_TencentWX 组件

 支持平台: iOS7.0,Android4.0
 接入微信开放平台，可使用微信登录、分享和支付功能

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**isWXAppInstalled**</font>: 微信APP是否安装

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: true 安装，false 没有安装
- 说明: 判断当前设备中是否安装微信APP
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <font color ='#0092db'>**login**</font>: 微信登录

- 参数:

  名称 | 类型 |是否必填|缺省值|说明
  ---- |-------------  |--------------|--------|------
  **appId** |<font color ='#808000'>**string**</font> |  | 是|在微信开发平台申请的appId
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 用户点击授权后，微信客户端会被调起，跳转至授权界面，用户在该界面点击允许或取消，返回数据给调用方。返回
ErrCode	ERR_OK = 0(用户同意)
ERR_AUTH_DENIED = -4（用户拒绝授权）
ERR_USER_CANCEL = -2（用户取消）
code	用户换取access_token的code，仅在errCode为0时有效
state	第三方程序发送时用来标识其请求的唯一性的标志，由第三方程序调用sendReq时传入，由微信终端回传，state字符串长度不能超过1K
lang	微信客户端当前语言
country	微信用户当前国家信息
- 说明: 使用微信登录获取用户登录的信息
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**pay**</font>: 微信支付

- 参数:

  名称 | 类型 |是否必填|缺省值|说明
  ---- |-------------  |--------------|--------|------
  **appId** |<font color ='#808000'>**string**</font> |  | 是|在微信开放平台创建应用后，分配的appid
  **partnerId** |<font color ='#808000'>**string**</font> |  | 是|微信支付分配的商户号
  **prepayId** |<font color ='#808000'>**string**</font> |  | 是|商户服务器返回的的预支付交易会话ID,长度为32个字符
  **package** |<font color ='#808000'>**string**</font> |  | 是|商户服务器返回的扩展字段,长度不超过128个字符
  **nonceStr** |<font color ='#808000'>**string**</font> |  | 是|商户服务器返回的随机字符串，长度不能超过32个字符
  **timeStamp** |<font color ='#808000'>**string**</font> |  | 是|商户服务器返回的时间戳,长度为10个字符
  **sign** |<font color ='#808000'>**string**</font> |  | 是|商户服务器返回的签名,长度为32个字符
- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 0 支付完成,-1 错误,-2 用户取消
- 说明: 调用微信支付
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**share**</font>: 微信分享

- 参数:

  名称 | 类型 |是否必填|缺省值|说明
  ---- |-------------  |--------------|--------|------
  **appId** |<font color ='#808000'>**string**</font> |  | 是|在微信开放平台申请的appId
  **scene** |<font color ='#808000'>**number**</font> | 0 | 是|0：分享到微信好友；1：分享到微信朋友圈
  **type** |<font color ='#808000'>**number**</font> | 0 | 是|0：默认，图文分享；1：纯图分享，只支持本地图片；2：音乐分享
  **title** |<font color ='#808000'>**string**</font> |  | 否|分享的标题
  **content** |<font color ='#808000'>**string**</font> |  | 否|分享的文本内容,图文分享时不能为空
  **url** |<font color ='#808000'>**string**</font> |  | 否|分享后点击文本打开的地址
  **image** |<font color ='#808000'>**string**</font> |  | 否|分享后显示的图片，微信sdk限制网络图片是32k，纯图分享时候不能为空，仅支持本地图片data://目录
  **audio** |<font color ='#808000'>**string**</font> |  | 否|音乐文件的远程链接, 以URL的形式传入, 不支持本地音乐
  **trumb** |<font color ='#808000'>**string**</font> |  | 否|纯图分享时显示的缩略图，仅支持本地图片，为空时则自动取缩放后的image参数图片，不建议超过32k大小限制，否则为了保证能分享成功，还是会对图片进行缩放
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: true 分享成功，false 分享失败
- 说明: 微信分享
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件


