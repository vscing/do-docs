---
title: do_UMengAnalytics 组件
---

### do_UMengAnalytics 组件

* 支持平台: iOS7.0,Android4.0
关于计数事件与计算事件的详细文档http://dev.umeng.com/analytics/functions/numekv#1_1_1

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**beginPageLog**</font>: 进入页面的统计

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **pageName** |<font color ='#808000'>**string**</font> |  | 是||
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 建议放在page的resume事件中
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**endPageLog**</font>: 离开页面的统计

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **pageName** |<font color ='#808000'>**string**</font> |  | 是||
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 建议放在page的pause事件中
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**eventLog**</font>: 单次事件统计

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **id** |<font color ='#808000'>**string**</font> |  | 是||
  **data** |<font color ='#808000'>**object**</font> |  | 否||
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**eventValueLog**</font>: 单次事件计算

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **id** |<font color ='#808000'>**string**</font> |  | 是||
  **data** |<font color ='#808000'>**object**</font> |  | 否||
  **counter** |<font color ='#808000'>**number**</font> |  | 否||
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**readConfig**</font>: 读取在线参数

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **configID** |<font color ='#808000'>**string**</font> |  | 是||
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: iOS平台不支持
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**setEncryptLog**</font>: 是否加密传输日志

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **value** |<font color ='#808000'>**Boolean**</font> |  | 是||
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**setBackgroundTask**</font>: 是否支持后台模式

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **value** |<font color ='#808000'>**Boolean**</font> |  | 是||
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 只支持iOS
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**setCrashReportEnabled**</font>: 是否统计后异常信息

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **value** |<font color ='#808000'>**Boolean**</font> |  | 是||
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件


