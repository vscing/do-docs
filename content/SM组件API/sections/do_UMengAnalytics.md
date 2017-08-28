---
title: do_UMengAnalytics 组件
---

### do_UMengAnalytics 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_UMengAnalytics)
 关于计数事件与计算事件的详细文档http://dev.umeng.com/analytics/functions/numekv#1_1_1

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#0092db'>同步方法</font>  |[beginPageLog](#beginPageLog)| 进入页面的统计
<font color ='#0092db'>同步方法</font>  |[endPageLog](#endPageLog)| 离开页面的统计
<font color ='#0092db'>同步方法</font>  |[eventLog](#eventLog)| 单次事件统计
<font color ='#0092db'>同步方法</font>  |[eventValueLog](#eventValueLog)| 单次事件计算
<font color ='#0092db'>同步方法</font>  |[readConfig](#readConfig)| 读取在线参数
<font color ='#0092db'>同步方法</font>  |[setEncryptLog](#setEncryptLog)| 是否加密传输日志
<font color ='#0092db'>同步方法</font>  |[setBackgroundTask](#setBackgroundTask)| 是否支持后台模式
<font color ='#0092db'>同步方法</font>  |[setCrashReportEnabled](#setCrashReportEnabled)| 是否统计后异常信息

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=beginPageLog><font color ='#0092db'>**beginPageLog**</font></span>: 进入页面的统计

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **pageName** |<font color ='#808000'>**string**</font> | 是 | |
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 建议放在page的resume事件中
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=endPageLog><font color ='#0092db'>**endPageLog**</font></span>: 离开页面的统计

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **pageName** |<font color ='#808000'>**string**</font> | 是 | |
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 建议放在page的pause事件中
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=eventLog><font color ='#0092db'>**eventLog**</font></span>: 单次事件统计

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **id** |<font color ='#808000'>**string**</font> | 是 | |
  **data** |<font color ='#808000'>**object**</font> | 否 | |
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=eventValueLog><font color ='#0092db'>**eventValueLog**</font></span>: 单次事件计算

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **id** |<font color ='#808000'>**string**</font> | 是 | |
  **data** |<font color ='#808000'>**object**</font> | 否 | |
  **counter** |<font color ='#808000'>**number**</font> | 否 | |
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=readConfig><font color ='#0092db'>**readConfig**</font></span>: 读取在线参数

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **configID** |<font color ='#808000'>**string**</font> | 是 | |
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: iOS平台不支持
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=setEncryptLog><font color ='#0092db'>**setEncryptLog**</font></span>: 是否加密传输日志

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **value** |<font color ='#808000'>**Boolean**</font> | 是 | |
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=setBackgroundTask><font color ='#0092db'>**setBackgroundTask**</font></span>: 是否支持后台模式

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **value** |<font color ='#808000'>**Boolean**</font> | 是 | |
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 只支持iOS
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=setCrashReportEnabled><font color ='#0092db'>**setCrashReportEnabled**</font></span>: 是否统计后异常信息

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **value** |<font color ='#808000'>**Boolean**</font> | 是 | |
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


