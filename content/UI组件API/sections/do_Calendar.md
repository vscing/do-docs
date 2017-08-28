---
title: do_Calendar 组件
---

### do_Calendar 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_Calendar)
 日历控件

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#0092db'>同步方法</font>  |[getSelectedDate](#getSelectedDate)| 当前选中日期
<font color ='#0092db'>同步方法</font>  |[jump](#jump)| 跳转到指定日期
<font color ='#e96900'>事件</font>  |[selectedDate](#selectedDate)| 点击日历上的日期触发事件

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=getSelectedDate><font color ='#0092db'>**getSelectedDate**</font></span>: 当前选中日期

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回当前选中的日期{'year':,'mouth':,'day':,'week':}，年、月、日、星期
- 说明: 获取当前选中日期
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=jump><font color ='#0092db'>**jump**</font></span>: 跳转到指定日期

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **data** |<font color ='#808000'>**string**</font> | 是 | |data数据格式为：2016-03-05(yyyy-mm-dd)
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 跳转到指定日期
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=selectedDate><font color ='#e96900'>**selectedDate**</font></span>: 点击日历上的日期触发事件

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回当前选中的日期{'year':,'mouth':,'day':,'week':}，年、月、日、星期
- 说明: 点击日历上的日期触发事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


