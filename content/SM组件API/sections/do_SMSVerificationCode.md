---
title: do_SMSVerificationCode 组件
---

### do_SMSVerificationCode 组件

 支持平台: iOS8.0,Android 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_SMSVerificationCode)
 短信验证码组件,给用户手机号码发送验证码并验证

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#0092db'>异步方法</font>  |[getSMSVerificationCode](#getSMSVerificationCode)| 根据手机号获取短信验证码
<font color ='#0092db'>异步方法</font>  |[verifySMSVerificationCode](#verifySMSVerificationCode)| 验证短信验证码

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <span id=getSMSVerificationCode><font color ='#0092db'>**getSMSVerificationCode**</font></span>: 根据手机号获取短信验证码

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **phoneNumber** |<font color ='#808000'>**string**</font> | 是 | |对该号码发送验证码
- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: 成功返回true,失败返回false
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=verifySMSVerificationCode><font color ='#0092db'>**verifySMSVerificationCode**</font></span>: 验证短信验证码

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **code** |<font color ='#808000'>**string**</font> | 是 | |收到的验证码
  **phoneNumber** |<font color ='#808000'>**string**</font> | 是 | |手机号码
- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: 验证成功返回true,失败返回false
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件


