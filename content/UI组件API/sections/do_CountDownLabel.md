---
title: do_CountDownLabel 组件
---

### do_CountDownLabel 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_CountDownLabel)
 显示倒计时的文本标签框，支持设置字体颜色、大小、内容对齐方式，倒计时内容样式：23:59:59.99(时间长度小于一天时间)。

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#42b983'>属性</font>  |[countDown](#countDown)| 时间长度
<font color ='#42b983'>属性</font>  |[fontColor](#fontColor)| 字体颜色
<font color ='#42b983'>属性</font>  |[fontSize](#fontSize)| 字体大小
<font color ='#42b983'>属性</font>  |[textAlign](#textAlign)| 文本对齐方式
<font color ='#e96900'>事件</font>  |[finish](#finish)| 倒计时完成触发

#### <font color ='#40A977'>**1.**</font> 属性

>###### <span id=countDown><font color ='#42b983'>**countDown**</font></span>: 时间长度

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 :无
- 说明 : 设置倒计时时间长度，毫秒值
- 示例:

  ```javascript

  var do_CountDownLabel = ui("do_CountDownLabel_1");

  //设置do_CountDownLabel的时间长度为10000毫秒
  //对do_CountDownLabel设置完时间长度之后立马开始倒计时，直到倒计时完成
	do_CountDownLabel.countDown = 10000;

  ```

>###### <span id=fontColor><font color ='#42b983'>**fontColor**</font></span>: 字体颜色

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 000000FF
- 说明 : 设置字体显示颜色，值格式为：8位16进制字符，前6位是RGB颜色值，后两位是透明度（Alpha），例如：000000FF
- 示例:

  ```javascript

  //设置do_CountDownLabel的字体颜色为白色
	do_CountDownLabel.fontColor = "FFFFFFFF";

  ```

>###### <span id=fontSize><font color ='#42b983'>**fontSize**</font></span>: 字体大小

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 17
- 说明 :
- 示例:

  ```javascript

  //设置do_CountDownLabel的字体大小为35
	do_CountDownLabel.fontSize = 35;

  ```
  效果图如下：
  <img src="../../images/countdownlabel_base.png" width="330" height="380" />

[回到顶部](#top)

>###### <span id=textAlign><font color ='#42b983'>**textAlign**</font></span>: 文本对齐方式

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : left
- 编辑类型 : 只允许设计区内修改
- 说明 : 对齐方式为以下3种：left 左对齐（默认）；center 居中；right 右对齐。

#### <font color ='#40A977'>**2.**</font> 同步方法

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=finish><font color ='#e96900'>**finish**</font></span>: 倒计时完成触发

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 倒计时完成触发
- 示例:

  ```javascript

  //倒计时完成时触发该事件
  do_CountDownLabel.on("finish",function(data){
  	 deviceone.print("触发倒计时完成事件")
  })

  ```

#### <font color ='#40A977'>**5.**</font> 常见问题

#### <font color ='#40A977'>**6.**</font> 基本配置

[回到顶部](#top)
