---
title: do_RichLabel1 组件
---

### do_RichLabel1 组件

 支持平台: iOS7.0,Android14 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_RichLabel1)
 富文本签框，设置字体高亮颜色、字体样式

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#42b983'>属性</font>  |[fontColor](#fontColor)| 字体颜色
<font color ='#42b983'>属性</font>  |[fontStyle](#fontStyle)| 字体风格
<font color ='#42b983'>属性</font>  |[textFlag](#textFlag)| 字体标示
<font color ='#42b983'>属性</font>  |[fontSize](#fontSize)| 字体大小
<font color ='#42b983'>属性</font>  |[textAlign](#textAlign)| 文本对齐方式
<font color ='#42b983'>属性</font>  |[maxHeight](#maxHeight)| 最大高度
<font color ='#42b983'>属性</font>  |[maxLines](#maxLines)| 最多行数
<font color ='#42b983'>属性</font>  |[maxWidth](#maxWidth)| 最大宽度
<font color ='#42b983'>属性</font>  |[text](#text)| 文本
<font color ='#42b983'>属性</font>  |[span](#span)| 设置区域内显示富文本字体样式
<font color ='#e96900'>事件</font>  |[touch](#touch)| 匹配内容点击事件

#### <font color ='#40A977'>**1.**</font> 属性

>###### <span id=fontColor><font color ='#42b983'>**fontColor**</font></span>: 字体颜色

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 000000FF
- 说明 : 设置字体显示颜色，值格式为：8位16进制字符，前6位是RGB颜色值，后两位是透明度（Alpha），例如：000000FF

>###### <span id=fontStyle><font color ='#42b983'>**fontStyle**</font></span>: 字体风格

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : normal
- 说明 : 包含4种类型：normal：常规bold：粗体italic：斜体bold_italic：粗斜体（iOS平台不支持）

>###### <span id=textFlag><font color ='#42b983'>**textFlag**</font></span>: 字体标示

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : normal
- 说明 : 包含3种类型：normal：常规underline ：下划线strikethrough ：删除线

>###### <span id=fontSize><font color ='#42b983'>**fontSize**</font></span>: 字体大小

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 17
- 说明 : 

>###### <span id=textAlign><font color ='#42b983'>**textAlign**</font></span>: 文本对齐方式

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : left
- 说明 : 对齐方式为以下3种：left 左对齐（默认）；center 居中；right 右对齐。

>###### <span id=maxHeight><font color ='#42b983'>**maxHeight**</font></span>: 最大高度

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 
- 说明 : label的height为－1的时候，label会根据text内容自动适配变高，但是不会高于maxHeight

>###### <span id=maxLines><font color ='#42b983'>**maxLines**</font></span>: 最多行数

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 1
- 说明 : 最大行数，缺省是1，如果为小于或等于0表示不限行数，说明：设置文本内容显示最大行数，如显示内容超过了最大行值则结尾用省略号...表示；iOS平台不支持

>###### <span id=maxWidth><font color ='#42b983'>**maxWidth**</font></span>: 最大宽度

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 
- 说明 : 设置文本框显示最大宽度值，只有在设置Width属性值为-1时有效，否则不起作用;

>###### <span id=text><font color ='#42b983'>**text**</font></span>: 文本

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 : 文本显示内容

>###### <span id=span><font color ='#42b983'>**span**</font></span>: 设置区域内显示富文本字体样式

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 : 值格式为：[{},{}]，{}中的内容为1.strMatch，如a，匹配字符串；2.substring，如0,10（开始字符位置，结束字符位置），截取字符串；3.spanStyle，如{fontColor:'FF3030FF',fontStyle:'bold'}，区域内字体显示样式；4.allowTouch，bool型，是否允许点击事件；5.tag，自定义数据

#### <font color ='#40A977'>**2.**</font> 同步方法

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=touch><font color ='#e96900'>**touch**</font></span>: 匹配内容点击事件

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回匹配到的内容content和tag数据
- 说明: 匹配内容点击事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


