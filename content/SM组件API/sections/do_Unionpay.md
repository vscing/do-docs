---
title: do_Unionpay 组件
---

### do_Unionpay 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_Unionpay)
 接入银联SDK，完成支付功能

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#0092db'>异步方法</font>  |[startPay](#startPay)| 支付

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <span id=startPay><font color ='#0092db'>**startPay**</font></span>: 支付

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **orderInfo** |<font color ='#808000'>**string**</font> | 是 | |交易流水号，是商户后台通过调用银联后台获取的
  **mode** |<font color ='#808000'>**string**</font> | 是 | |测试类型，取值为”00”、”01”。”00”表示银联正式环境，若开发者已经接入网银联支付，可用正式环境测试；”01”表示银联测试环境，测试环境仅用于测试插件功能是否正常
  **verifyUrl** |<font color ='#808000'>**string**</font> | 否 | |根据银联支付开发者网站提供的网站API文档搭建的商户验证支付结果的接口，如不填写则不进行二次校验，以银联控件支付结果为准，建议填写
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {'code':'0','msg':'success'}，其中pay_result的返回值为0表示订单支付成功,1为支付失败,-1为用户取消了支付,-2支付发生未知错误
- 说明: 调用银联支付
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件


