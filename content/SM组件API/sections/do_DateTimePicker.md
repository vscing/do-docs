---
title: do_DateTimePicker 组件
---

### do_DateTimePicker 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_DateTimePicker)
 弹出时间，日期选择窗口来选择时间，时间格式都是long型时间戳格式，windows平台不支持long型

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#0092db'>异步方法</font>  |[show](#show)| 弹出选择日期，时间，或日期时间窗口

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <span id=show><font color ='#0092db'>**show**</font></span>: 弹出选择日期，时间，或日期时间窗口

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **type** |<font color ='#808000'>**number**</font> | 是 | |0表示日期及时间，1表示只有日期，2表示只有时间，3表示日期、星期及时间
  **data** |<font color ='#808000'>**string**</font> | 否 | |long型时间，缺失值是当前日期时间long型
  **maxDate** |<font color ='#808000'>**string**</font> | 否 | 4102329600000|long型时间，缺省值是2099年对应的long型
  **minDate** |<font color ='#808000'>**string**</font> | 否 | 0|long型时间，最小日期不能大于最大日期，缺省值是1970年对应的long型
  **title** |<font color ='#808000'>**string**</font> | 否 | 日期时间选择|缺省值是‘时间选择’或者‘日期选择’或者‘日期时间选择’，根据type来区分
  **buttons** |<font color ='#808000'>**object**</font> | 否 | ["取消","确定"]|为空或不设值不显示按钮，显示缺省值，如果设值为[]，则不显示按钮
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {"flag":0,"time":"2312412343"}，flag =0 表示点击了第一个按钮，flag = 1 表示点击了第二个按钮...，time表示long型时间
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件


