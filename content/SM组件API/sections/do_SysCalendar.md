---
title: do_SysCalendar 组件
---

### do_SysCalendar 组件

* 支持平台: iOS7,Android14
可以获取系统日历的日程以及添加日程,修改和删除日程

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <font color ='#0092db'>**getAll**</font>: 根据所有日程信息

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回所查询到的所有日程的详细信息{id:'1',title:'日程标题',description:'日程说明',startTime:'1494460800',endTime:'1494460800',location:'北京'}，iOS平台获取当前时间前后两年的日程
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**add**</font>: 添加日程

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **title** |<font color ='#808000'>**string**</font> |  | 是||
  **description** |<font color ='#808000'>**string**</font> |  | 是||
  **startTime** |<font color ='#808000'>**string**</font> |  | 是||long型时间
  **endTime** |<font color ='#808000'>**string**</font> |  | 是||long型时间
  **location** |<font color ='#808000'>**string**</font> |  | 否||
  **reminderTime** |<font color ='#808000'>**string**</font> |  | 否||提前提醒时间，单位minute比如设置为60，就是在行程开始时间前一小时提醒，不填则准时提醒
  **reminderRepeatMode** |<font color ='#808000'>**string**</font> |  | 否||day:每天提醒一次，week:每周提醒一次，month:每月提醒一次，year:每年提醒一次
  **reminderRepeatEndTime** |<font color ='#808000'>**string**</font> |  | 否||long型时间，reminderRepeatMode设置过后该参数才有效，比如设置重复模式为Day，就是每天提醒，设置该参数后就是截止该时间停止提醒
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回所添加日程的唯一ID
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**update**</font>: 根据id修改对应的日程

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **id** |<font color ='#808000'>**string**</font> |  | 是||
  **title** |<font color ='#808000'>**string**</font> |  | 否||
  **description** |<font color ='#808000'>**string**</font> |  | 否||
  **startTime** |<font color ='#808000'>**string**</font> |  | 否||long型时间
  **endTime** |<font color ='#808000'>**string**</font> |  | 否||long型时间
  **location** |<font color ='#808000'>**string**</font> |  | 否||
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: 修改成功返回true，失败则返回false
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**delete**</font>: 根据id删除对应的日程

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **id** |<font color ='#808000'>**string**</font> |  | 是||
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: 删除成功返回true，失败则返回false
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件


