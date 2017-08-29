---
title: do_Button 组件
---

### do_Button 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_Button)
 按钮控件，支持通常按钮的属性，方法和事件，缺省是透明无边框。
 下图为设置了背景色、字体颜色、边框、字体风格、字体标示的效果图：
 <img src="../../images/button.png" width="330" height="380" />

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
- 编辑类型 : 只允许设计区内修改
- 说明 : 包含3种类型：normal：常规underline ：下划线strikethrough ：删除线

>###### <span id=radius><font color ='#42b983'>**radius**</font></span>: 圆角半径

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 0
- 编辑类型 : 只允许设计区内修改
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
  var do_Button = ui("do_Button_1");

  // 触发touch事件，按下并在按钮范围抬起，触发该事件
  do_Button.on("touch", function() {
    	// 设置bgImage属性
    	do_Button.bgImage = "source://view/do_Button/backgroud.png";
    	// 设置fontColor属性值格式为：8位16进制字符，前6位是RGB颜色值，后两位是透明度(Alpha)
    	do_Button.fontColor = "FF0000FF";
    	// 设置fontSize属性
    	do_Button.fontSize = 35;
    	// 设置fontStyle属性,包含4种类型：normal：常规; bold：粗体; italic：斜体; bold_italic：粗斜体（iOS平台不支持）
    	do_Button.fontStyle = "italic";
  })
  ```

[回到顶部](#top)

>###### <span id=touchDown><font color ='#e96900'>**touchDown**</font></span>: 按钮范围内按下即可触发

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述:
- 说明: 按钮范围内按下即可触发
- 示例:

  ```javascript
  //触发touchDown事件，按钮范围内按下即可触发
  do_Button.on("touchDown",function(){
  	 do_Button.text = "触发touchDown事件";   //设置按钮的text属性
     do_Button.border = "FF0000FF,1,[20,20,20,20]";   //设置按钮的border属性,border值格式为"颜色值，宽度，圆角"
  })

  ```

[回到顶部](#top)

>###### <span id=touchUp><font color ='#e96900'>**touchUp**</font></span>: 一旦按下，手指离开即触发，不论是否在按钮范围内

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述:
- 说明: 一旦按下，手指离开即触发，不论是否在按钮范围内
- 示例:

  ```javascript
  //触发touchDown事件，按钮范围内按下即可触发
  do_Button.on("touchUp",function(){
  	 do_Button.text = "触发touchUp事件";   //设置按钮的text属性
  })

  ```

#### <font color ='#40A977'>**5.**</font> 常见问题

- 1. 苹果不建议在touch的时候修改按钮的透明度。  
     原因：由于iOS的机制问题，不建议在touch的时候修改按钮的透明度。如果想要修改的话，可以使用不同的do_Button，控制组件的显示和隐藏。
- 2. 安卓给button设置有背景图片时，给组件设置圆角没有效果。
    原因：因为所有组件border的圆角都是假的，相当于给了一个圆角的背景图片。

#### <font color ='#40A977'>**6.**</font> 基本配置

[回到顶部](#top)
