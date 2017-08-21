---
title: do_VerticalMarqueeLabel 组件
---

### do_VerticalMarqueeLabel 组件

* 支持平台: iOS7.0,Android4.0
多条文字垂直滚动

#### <font color ='#40A977'>**1.**</font> 属性

>###### <font color ='#42b983'>**direction**</font>: 文字滚动方向

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : up
- 说明 : 修改文字滚动方向，支持向上与向下

>###### <font color ='#42b983'>**style**</font>: 文字滚动类型

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 0
- 说明 : 有两种滚动类型,一种是只有一条数据同时出现,中间位置停止一下,然后继续滚动,另一种是多条数据同时轮播,匀速移动

>###### <font color ='#42b983'>**text**</font>: 文本显示内容

- 数据类型 : <font color ='#808000'>**object**</font>
- 默认值 : 
- 说明 : 支持显示多条内容,格式为['aaa','bbb','ccc'...]

>###### <font color ='#42b983'>**fontColor**</font>: 字体颜色

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 000000FF
- 说明 : 设置字体显示颜色，值格式为：8位16进制字符，前6位是RGB颜色值，后两位是透明度（Alpha），例如：000000FF

>###### <font color ='#42b983'>**fontStyle**</font>: 字体风格

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : normal
- 说明 : 包含4种类型：normal：常规bold：粗体italic：斜体bold_italic：粗斜体

>###### <font color ='#42b983'>**textFlag**</font>: 字体标示

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : normal
- 说明 : 包含3种类型：normal：常规underline ：下划线strikethrough ：删除线

>###### <font color ='#42b983'>**fontSize**</font>: 字体大小

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 17
- 说明 : 

>###### <font color ='#42b983'>**duration**</font>: 动画间隔

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 2000
- 说明 : 文字跑完全程的时间，当style为0的时候，不包含中间停顿时间，单位毫秒

#### <font color ='#40A977'>**2.**</font> 同步方法

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件


