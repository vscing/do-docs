---
title: do_Label 组件
---

### do_Label 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_Label)
 文本标签框，用于显示文本文字，设置字体样式、大小、内容对齐

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#42b983'>属性</font>  |[text](#text)| 文本显示内容
<font color ='#42b983'>属性</font>  |[fontColor](#fontColor)| 字体颜色
<font color ='#42b983'>属性</font>  |[fontStyle](#fontStyle)| 字体风格
<font color ='#42b983'>属性</font>  |[textFlag](#textFlag)| 字体标示
<font color ='#42b983'>属性</font>  |[fontSize](#fontSize)| 字体大小
<font color ='#42b983'>属性</font>  |[textAlign](#textAlign)| 文本对齐方式
<font color ='#42b983'>属性</font>  |[maxWidth](#maxWidth)| 最大宽度
<font color ='#42b983'>属性</font>  |[maxHeight](#maxHeight)| 最大高度
<font color ='#42b983'>属性</font>  |[maxLines](#maxLines)| 最大行数
<font color ='#42b983'>属性</font>  |[linesSpace](#linesSpace)| 行间距
<font color ='#42b983'>属性</font>  |[shadow](#shadow)| 阴影效果

#### <font color ='#40A977'>**1.**</font> 属性

>###### <span id=text><font color ='#42b983'>**text**</font></span>: 文本显示内容

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 :
- 说明 : 获取或设置与此控件关联的文本。
- 示例:

  ```javascript

  var do_Label = ui("do_Label_3");  //实例化
  do_Label.text = "文本标签框，用于显示文本文字，设置字体样式、大小、内容对齐"

  ```

>###### <span id=fontColor><font color ='#42b983'>**fontColor**</font></span>: 字体颜色

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 000000FF
- 说明 : 设置字体显示颜色，值格式为：8位16进制字符，前6位是RGB颜色值，后两位是透明度（Alpha），例如：000000FF
- 示例:

  ```javascript

  do_Label.fontColor = "FF0000FF";

  ```

>###### <span id=fontStyle><font color ='#42b983'>**fontStyle**</font></span>: 字体风格

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : normal
- 说明 : 包含4种类型：normal：常规bold：粗体italic：斜体bold_italic：粗斜体（iOS平台不支持）
- 示例:

  ```javascript

  do_Label.fontStyle = "italic";

  ```

>###### <span id=textFlag><font color ='#42b983'>**textFlag**</font></span>: 字体标示

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : normal
- 说明 : 包含3种类型：normal：常规underline ：下划线strikethrough ：删除线
- 示例:

  ```javascript

  do_Label.textFlag = "underline";

  ```

>###### <span id=fontSize><font color ='#42b983'>**fontSize**</font></span>: 字体大小

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 17
- 说明 :
- 示例:

  ```javascript

  do_Label.fontSize = 30;

  ```

>###### <span id=textAlign><font color ='#42b983'>**textAlign**</font></span>: 文本对齐方式

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : left
- 编辑类型 : 只允许设计区内修改。
- 说明 : 对齐方式为以下3种：left 左对齐（默认）；center 居中；right 右对齐。

>###### <span id=maxWidth><font color ='#42b983'>**maxWidth**</font></span>: 最大宽度

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 :
- 编辑类型 : 只允许设计区内修改。
- 说明 : label的width为－1的时候，label会根据text内容自动适配变宽，但是不会宽于maxWidth

>###### <span id=maxHeight><font color ='#42b983'>**maxHeight**</font></span>: 最大高度

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 :
- 编辑类型 : 只允许设计区内修改。
- 说明 : 设置文本框显示最大高度值，只有在设置Height属性值为-1时有效，否则不起作用

>###### <span id=maxLines><font color ='#42b983'>**maxLines**</font></span>: 最大行数

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 1
- 编辑类型 : 只允许设计区内修改。
- 说明 : 最大行数，说明：设置文本内容显示最大行数，如显示内容超过了最大行值则结尾用省略号...表示（iOS只有设置成1时才会显示...）；缺省为1行，如果为小于或等于0表示不限行数

>###### <span id=linesSpace><font color ='#42b983'>**linesSpace**</font></span>: 行间距

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 :
- 说明 : 设置每行字之间的间距，windows平台不支持
- 示例:

  ```javascript

  do_Label.linesSpace = 40;

  ```
  下图为间距为10和间距为40的效果图。
  <div align="center">

  <img src="../../images/label_linesSpace_0.png" height="310" width="310" >

  <img src="../../images/label_linesSpace_1.png" height="310" width="310" >

  </div>

>###### <span id=shadow><font color ='#42b983'>**shadow**</font></span>: 阴影效果

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 :
- 说明 : 添加阴影效果，属性值格式是：“颜色，x位置，y位置，圆角”，如'FF9999FF,30,30,20'，默认值为'000000FF,0,0,0'，若其中某个值不填，需保留逗号，如不填颜色，',0,0,0'，当圆角为0时为没有阴影效果
- 示例:

  ```javascript

  do_Label.shadow = "FF0000FF,5,5,5";

  ```

  下图为分别设置不同的阴影的效果图。

  <div align="center">

  <img src="../../images/label_shadow_0.png" height="310" width="310" >

  <img src="../../images/label_shadow_1.png" height="310" width="310" >

  <img src="../../images/label_shadow_2.png" height="310" width="310" >

  </div>

#### <font color ='#40A977'>**2.**</font> 同步方法

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件  

[回到顶部](#top)   

#### <font color ='#40A977'>**5.**</font> 常见问题
  - 一.iOS

    - 1.height=-1，maxHeight=200，宽度具体数，maxLines=1，最大行数无效（高为-1时maxLines无效，靠maxHeight来控制）
    - 2.与安卓不一样的地方:
      - 1).ios的高度是固定值，text超过label的宽，text每行数据特别多，最大行数设置固定值（1、2）等，都有省略号；区别：android的text显示不全都有省略号
      - 2).label宽度固定，最大行间距与（字体大小*行数）超过label宽度，最后2行数据之间没有行间距，区别：android的，最大行间距与（字体大小*行数）超过label宽度，不显示最后几行数据
      - 3).ios动态改变textflag=normal，text数据会往下移动，区别：android的不会下移
      - 4).label的高度是固定值或者-1，设置最大行数（除-1和0）以外的数，数据是在中间显示的，不是从头显示，区别：android从头显示
      - 5).ios的label的border不支持4个角，区别：android的支持4个角不同
  - 二.Android

    - 1.最大高度与最大行数冲突，Android永远都是最大行数优先级高，如果maxLines=1，就是默认值（空），最大高度才起作用。

#### <font color ='#40A977'>**6.**</font> 基本配置
  - 1

[回到顶部](#top)     
