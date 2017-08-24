---
title: do_SangforVPN 组件
---

### do_SangforVPN 组件

 支持平台: iOS7.0,Android4.0
 使用深信服科技公司提供的VPN服务访问服务器资源，提供VPN登录，VPN注销登录的功能，仅支持android平台

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <font color ='#0092db'>**login**</font>: 登录VPN

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **host** |<font color ='#808000'>**string**</font> | 是 | |连接VPN地址
  **username** |<font color ='#808000'>**string**</font> | 是 | |登录VPN的用户名
  **password** |<font color ='#808000'>**string**</font> | 是 | |登录VPN的密码
  **port** |<font color ='#808000'>**number**</font> | 否 | 443|连接VPN端口
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {"result":"true 登录成功，false 登录失败","code":"0","msg":""}
- 说明: 登录VPN
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**logout**</font>: 注销VPN

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {"result":"true 注销成功，false 注销失败","code":"0","msg":""}
- 说明: 注销退出VPN
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件


