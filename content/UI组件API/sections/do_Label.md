---
title: do_Label 组件
---

### do_Label 组件

* 支持平台: iOS7.0,Android4.0
文本标签框，用于显示文本文字，设置字体样式、大小、内容对齐

#### <font color ='#40A977'>**1.**</font> 属性

>###### <font color ='#42b983'>**text**</font>: 文本显示内容

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 : 获取或设置与此控件关联的文本。

>###### <font color ='#42b983'>**fontColor**</font>: 字体颜色

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 000000FF
- 说明 : 设置字体显示颜色，值格式为：8位16进制字符，前6位是RGB颜色值，后两位是透明度（Alpha），例如：000000FF

>###### <font color ='#42b983'>**fontStyle**</font>: 字体风格

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : normal
- 说明 : 包含4种类型：normal：常规bold：粗体italic：斜体bold_italic：粗斜体（iOS平台不支持）

>###### <font color ='#42b983'>**textFlag**</font>: 字体标示

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : normal
- 说明 : 包含3种类型：normal：常规underline ：下划线strikethrough ：删除线

>###### <font color ='#42b983'>**fontSize**</font>: 字体大小

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 17
- 说明 : 

>###### <font color ='#42b983'>**textAlign**</font>: 文本对齐方式

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : left
- 说明 : 对齐方式为以下3种：left 左对齐（默认）；center 居中；right 右对齐。

>###### <font color ='#42b983'>**maxWidth**</font>: 最大宽度

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 
- 说明 : label的width为－1的时候，label会根据text内容自动适配变宽，但是不会宽于maxWidth

>###### <font color ='#42b983'>**maxHeight**</font>: 最大高度

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 
- 说明 : 设置文本框显示最大高度值，只有在设置Height属性值为-1时有效，否则不起作用

>###### <font color ='#42b983'>**maxLines**</font>: 最大行数

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 1
- 说明 : 最大行数，说明：设置文本内容显示最大行数，如显示内容超过了最大行值则结尾用省略号...表示（iOS只有设置成1时才会显示...）；缺省为1行，如果为小于或等于0表示不限行数

>###### <font color ='#42b983'>**linesSpace**</font>: 行间距

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 
- 说明 : 设置每行字之间的间距，windows平台不支持

>###### <font color ='#42b983'>**shadow**</font>: 阴影效果

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 : 添加阴影效果，属性值格式是：“颜色，x位置，y位置，圆角”，如'FF9999FF,30,30,20'，默认值为'000000FF,0,0,0'，若其中某个值不填，需保留逗号，如不填颜色，',0,0,0'，当圆角为0时为没有阴影效果

#### <font color ='#40A977'>**2.**</font> 同步方法

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件


