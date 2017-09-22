---
title: do_MarqueeLabel 组件
---

### do_MarqueeLabel 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_MarqueeLabel)
 文字能滚动播出的文本标签框

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#42b983'>属性</font>  |[direction](#direction)| 文字滚动方向
<font color ='#42b983'>属性</font>  |[text](#text)| 文本显示内容
<font color ='#42b983'>属性</font>  |[fontColor](#fontColor)| 字体颜色
<font color ='#42b983'>属性</font>  |[fontStyle](#fontStyle)| 字体风格
<font color ='#42b983'>属性</font>  |[textFlag](#textFlag)| 字体标示
<font color ='#42b983'>属性</font>  |[fontSize](#fontSize)| 字体大小

#### <font color ='#40A977'>**1.**</font> 属性

>###### <span id=direction><font color ='#42b983'>**direction**</font></span>: 文字滚动方向

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : left
- 编辑类型 : 只允许设计区内修改。
- 说明 : 修改文字滚动方向，支持向左与向右

>###### <span id=text><font color ='#42b983'>**text**</font></span>: 文本显示内容

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 :
- 说明 : 获取或设置与此控件关联的文本。
- 示例:

  ```javascript

  var do_MarqueeLabel = ui("do_MarqueeLabel_1");  //实例化
  do_MarqueeLabel.text = "文字能滚动播出的文本标签框";

  ```

>###### <span id=fontColor><font color ='#42b983'>**fontColor**</font></span>: 字体颜色

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 000000FF
- 说明 : 设置字体显示颜色，值格式为：8位16进制字符，前6位是RGB颜色值，后两位是透明度（Alpha），例如：000000FF
- 示例:

  ```javascript

  do_MarqueeLabel.fontColor = "FF0000FF";

  ```

>###### <span id=fontStyle><font color ='#42b983'>**fontStyle**</font></span>: 字体风格

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : normal
- 说明 : 包含4种类型：normal：常规bold：粗体italic：斜体bold_italic：粗斜体
- 示例:

  ```javascript

  do_MarqueeLabel.fontStyle = "bold";

  ```

>###### <span id=textFlag><font color ='#42b983'>**textFlag**</font></span>: 字体标示

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : normal
- 编辑类型 : 只允许设计区内修改。
- 说明 : 包含3种类型：normal：常规underline ：下划线strikethrough ：删除线

>###### <span id=fontSize><font color ='#42b983'>**fontSize**</font></span>: 字体大小

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 17
- 说明 :
- 示例:

  ```javascript

  do_MarqueeLabel.fontSize = 30;

  ```

#### <font color ='#40A977'>**2.**</font> 同步方法

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件
