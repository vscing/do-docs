---
title: do_ProgressBar2 组件
---

### do_ProgressBar2 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_ProgressBar2)
 环行进度条，进度条大小为组件最大内接圆，居中显示在组件范围内

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#42b983'>属性</font>  |[style](#style)| 进度条样式
<font color ='#42b983'>属性</font>  |[progress](#progress)| 进度值
<font color ='#42b983'>属性</font>  |[progressColor](#progressColor)| 进度颜色
<font color ='#42b983'>属性</font>  |[progressBgColor](#progressBgColor)| 进度条背景颜色
<font color ='#42b983'>属性</font>  |[progressWidth](#progressWidth)| 进度宽度
<font color ='#42b983'>属性</font>  |[text](#text)| 文本
<font color ='#42b983'>属性</font>  |[fontColor](#fontColor)| 字体颜色
<font color ='#42b983'>属性</font>  |[fontSize](#fontSize)| 字体大小

#### <font color ='#40A977'>**1.**</font> 属性

>###### <span id=style><font color ='#42b983'>**style**</font></span>: 进度条样式

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : normal
- 说明 : 进度条样式可以是以下几种类型：normal,cycle

>###### <span id=progress><font color ='#42b983'>**progress**</font></span>: 进度值

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 0
- 说明 : 设置进度值，取值范围是0-100的浮点值,进度条样式是普通样式时有效

>###### <span id=progressColor><font color ='#42b983'>**progressColor**</font></span>: 进度颜色

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 000000FF
- 说明 : 8位16进制整数，前6位为rgb颜色值，后两位为透明度

>###### <span id=progressBgColor><font color ='#42b983'>**progressBgColor**</font></span>: 进度条背景颜色

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : FFFFFFFF
- 说明 : 8位16进制整数，前6位为rgb颜色值，后两位为透明度

>###### <span id=progressWidth><font color ='#42b983'>**progressWidth**</font></span>: 进度宽度

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 1
- 说明 : 进度宽度，范围 为1-100，表示占环形进度条最外圈半径的百分比，如20表示占环形进度条半径的20%宽度

>###### <span id=text><font color ='#42b983'>**text**</font></span>: 文本

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 : 环形进度条中间文本,进度条样式为normal时有效

>###### <span id=fontColor><font color ='#42b983'>**fontColor**</font></span>: 字体颜色

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 000000FF
- 说明 : 字体颜色，为8位16进制整数，前6位为rgb颜色值，后两位为透明度

>###### <span id=fontSize><font color ='#42b983'>**fontSize**</font></span>: 字体大小

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 17
- 说明 : 

#### <font color ='#40A977'>**2.**</font> 同步方法

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件


