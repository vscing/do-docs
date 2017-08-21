---
title: do_CountDownLabel 组件
---

### do_CountDownLabel 组件

 支持平台: iOS7.0,Android4.0
 显示倒计时的文本标签框，支持设置字体颜色、大小、内容对齐,倒计时内容样式:23:59:59.99(时间长度小于一天时间)

#### <font color ='#40A977'>**1.**</font> 属性

>###### <font color ='#42b983'>**countDown**</font>: 时间长度

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 
- 说明 : 设置倒计时时间长度，毫秒值

>###### <font color ='#42b983'>**fontColor**</font>: 字体颜色

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 000000FF
- 说明 : 设置字体显示颜色，值格式为：8位16进制字符，前6位是RGB颜色值，后两位是透明度（Alpha），例如：000000FF

>###### <font color ='#42b983'>**fontSize**</font>: 字体大小

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 17
- 说明 : 

>###### <font color ='#42b983'>**textAlign**</font>: 文本对齐方式

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : left
- 说明 : 对齐方式为以下3种：left 左对齐（默认）；center 居中；right 右对齐。

#### <font color ='#40A977'>**2.**</font> 同步方法

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <font color ='#e96900'>**finish**</font>: 倒计时完成触发

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 
- 说明: 倒计时完成触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


