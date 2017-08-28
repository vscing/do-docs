---
title: do_FingerPrintRecognition 组件
---

### do_FingerPrintRecognition 组件

 支持平台: iOS8.0,Android6.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_FingerPrintRecognition)
 指纹识别组件,iOS为基于系统touchID和密码识别验证,需要iPhone5s设备搭载iOS8以上系统,IOS touchID识别策略(系统原生框架识别策略,不可修改,可以对照支付宝查看。警告！：touchID验证为设备公用功能(设备解锁和所有app)，不要随意故意错误验证，多次错误验证失败后，设备将会被锁，而且锁定时间越来越长，最终可能导致设备永久锁定!!!。): Android系统要求大于6.0. Android是连续验证失败5次之后30秒内不能继续验证.

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#0092db'>同步方法</font>  |[startRecognize](#startRecognize)| 启动识别
<font color ='#e96900'>事件</font>  |[localizedFallbackButtonClick](#localizedFallbackButtonClick)| 验证过程中，验证弹框自定义验证按钮点击事件(仅iOS有效，订阅该事件，用户处理自定义验证逻辑步骤)
<font color ='#e96900'>事件</font>  |[recognizeResult](#recognizeResult)| 验证事件(startRecognize方法的识别结果从该事件返回值取)

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=startRecognize><font color ='#0092db'>**startRecognize**</font></span>: 启动识别

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **localizedReason** |<font color ='#808000'>**string**</font> | 是 | 通过Home键验证已有手机指纹|应用程序提供的请求身份验证的原因，显示在向用户呈现的身份验证对话框中。在iOS中会显示在副标题中。该字符串应以用户当前的语言提供，应该简短明了。它不应该包含应用程序名称，因为它出现在身份验证对话框的其他位置。（仅iOS有效）
  **localizedCancelTitle** |<font color ='#808000'>**string**</font> | 否 | 取消|验证期间向用户呈现的对话框中的取消验证按钮的标题名称。该字符串应以用户当前的语言提供，应该简短明了。（仅iOS有效）
  **localizedFallbackTitle** |<font color ='#808000'>**string**</font> | 否 | 前往自定义验证|验证期间向用户呈现的对话框中的自定义操作按钮标题名称。该字符串应以用户当前的语言提供，应该简短明了。（仅iOS有效）
- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: 启动成功返回true,失败返回false(iOS验证弹框为系统自带,不支持设备的不会弹出验证框;Android端默认无验证弹框,用户可以拿到true返回值时弹出自定义验证框)
- 说明: 启动识别
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=localizedFallbackButtonClick><font color ='#e96900'>**localizedFallbackButtonClick**</font></span>: 验证过程中，验证弹框自定义验证按钮点击事件(仅iOS有效，订阅该事件，用户处理自定义验证逻辑步骤)

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 
- 说明: 验证过程中，验证弹框自定义验证按钮点击事件(仅iOS有效，订阅该事件，用户处理自定义验证逻辑步骤)
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <span id=recognizeResult><font color ='#e96900'>**recognizeResult**</font></span>: 验证事件(startRecognize方法的识别结果从该事件返回值取)

- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: 
- 说明: 验证事件(startRecognize方法的识别结果从该事件返回值取)
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


