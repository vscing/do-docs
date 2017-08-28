---
title: do_Button 组件
---

### do_Button 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_Button)
 按钮控件，支持通常按钮的属性，方法和事件，缺省是透明无边框。abc

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#42b983'>属性</font>  |[enabled](#enabled)| 是否有效
<font color ='#42b983'>属性</font>  |[text](#text)| 标题
<font color ='#42b983'>属性</font>  |[fontColor](#fontColor)| 字体颜色
<font color ='#42b983'>属性</font>  |[fontSize](#fontSize)| 字体大小
<font color ='#42b983'>属性</font>  |[fontStyle](#fontStyle)| 字体风格
<font color ='#42b983'>属性</font>  |[textFlag](#textFlag)| 字体标示
<font color ='#42b983'>属性</font>  |[radius](#radius)| 圆角半径
<font color ='#42b983'>属性</font>  |[bgImage](#bgImage)| 背景图片
<font color ='#e96900'>事件</font>  |[touch](#touch)| 按下并在按钮范围抬起，触发该事件
<font color ='#e96900'>事件</font>  |[touchDown](#touchDown)| 按钮范围内按下即可触发
<font color ='#e96900'>事件</font>  |[touchUp](#touchUp)| 一旦按下，手指离开即触发，不论是否在按钮范围内

#### <font color ='#40A977'>**1.**</font> 属性

>###### <span id=enabled><font color ='#42b983'>**enabled**</font></span>: 是否有效

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : true
- 说明 : 控制button的点击事件，缺省为true，表示用户如果点击按钮会触发button的三种touch事件

>###### <span id=text><font color ='#42b983'>**text**</font></span>: 标题

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 : 获取或设置与此控件关联的文本

>###### <span id=fontColor><font color ='#42b983'>**fontColor**</font></span>: 字体颜色

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 000000FF
- 说明 : 设置字体显示颜色，值格式为：8位16进制字符，前6位是RGB颜色值，后两位是透明度（Alpha），例如：000000FF

>###### <span id=fontSize><font color ='#42b983'>**fontSize**</font></span>: 字体大小

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 17
- 说明 : 

>###### <span id=fontStyle><font color ='#42b983'>**fontStyle**</font></span>: 字体风格

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : normal
- 说明 : 包含4种类型：normal：常规bold：粗体italic：斜体bold_italic：粗斜体（iOS平台不支持）

>###### <span id=textFlag><font color ='#42b983'>**textFlag**</font></span>: 字体标示

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : normal
- 说明 : 包含3种类型：normal：常规underline ：下划线strikethrough ：删除线

>###### <span id=radius><font color ='#42b983'>**radius**</font></span>: 圆角半径

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 0
- 说明 : 像素值，为0时表示不是圆角按钮；@deprecated，该属性为不建议使用，建议使用UI的基础属性border来替代

>###### <span id=bgImage><font color ='#42b983'>**bgImage**</font></span>: 背景图片

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 : 可设置本地文件：支持data://和source://两种方式。文件格式说明参考Storage类

#### <font color ='#40A977'>**2.**</font> 同步方法

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=touch><font color ='#e96900'>**touch**</font></span>: 按下并在按钮范围抬起，触发该事件

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 
- 说明: 按下并在按钮范围抬起，触发该事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <span id=touchDown><font color ='#e96900'>**touchDown**</font></span>: 按钮范围内按下即可触发

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 
- 说明: 按钮范围内按下即可触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <span id=touchUp><font color ='#e96900'>**touchUp**</font></span>: 一旦按下，手指离开即触发，不论是否在按钮范围内

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 
- 说明: 一旦按下，手指离开即触发，不论是否在按钮范围内
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


