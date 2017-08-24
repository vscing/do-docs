---
title: do_Pedometer 组件
---

### do_Pedometer 组件

 支持平台: iOS7.0,Android4.0
 可获取并记录步数；iOS平台仅支持iPhone5S及以后产品

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**start**</font>: 启动记步

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**stop**</font>: 停止记步

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <font color ='#0092db'>**getInfo**</font>: 获取记步信息

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **date** |<font color ='#808000'>**string**</font> | 否 | |日期格式为yyyy-mm-dd，不设置时默认值为当天0点起截止到当前时间
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: [{'count':'步数']，返回当天或指定日期记录的步数，若指定日期没有启动记步则返回0
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件


