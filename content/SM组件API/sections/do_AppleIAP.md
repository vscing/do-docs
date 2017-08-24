---
title: do_AppleIAP 组件
---

### do_AppleIAP 组件

 支持平台: iOS,Android
 用户通过传入商品ID，数量可以调起Apple支付界面，同时支持商品重复购买更新

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**restoreProduct**</font>: 恢复购买

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 刷新产品购买状态，在不同设备上用同一账户购买过，调用该方法可以恢复成已购买状态；或购买后将应用卸载，重新安装后可恢复已购买状态
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <font color ='#0092db'>**purchase**</font>: 购买商品

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **productID** |<font color ='#808000'>**string**</font> | 是 | |对应iTunes Connect中配置的“产品ID“
  **verifyURL** |<font color ='#808000'>**string**</font> | 否 | |App Store上实际购买验证URL，是一个枚举值，开发测试用https://sandbox.itunes.apple.com/verifyReceipt。发布版用https://buy.itunes.apple.com/verifyReceipt,实际的项目中使用发布版，开发测试是用于调试测试。如果不填，就需要自己搭建server端去验证；苹果官方建议自己搭建service
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 得到苹果返回的一个收据(receipt)，如果用verifyURL中两个枚举值之一作为验证，购买成功后会返回收据；若自己搭建service需将得到的receipt用http的post去请求https://buy.itunes.apple.com/verifyReceipt以校验是否购买成功
- 说明: 用户
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件


