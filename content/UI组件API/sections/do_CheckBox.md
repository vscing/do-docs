---
title: do_CheckBox 组件
---

### do_CheckBox 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_CheckBox)


#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#42b983'>属性</font>  |[enabled](#enabled)| 是否可点击
<font color ='#42b983'>属性</font>  |[checked](#checked)| 是否选中
<font color ='#42b983'>属性</font>  |[text](#text)| 文本显示内容
<font color ='#42b983'>属性</font>  |[fontColor](#fontColor)| 字体颜色
<font color ='#42b983'>属性</font>  |[fontStyle](#fontStyle)| 字体风格
<font color ='#42b983'>属性</font>  |[textFlag](#textFlag)| 字体标示
<font color ='#42b983'>属性</font>  |[fontSize](#fontSize)| 字体大小
<font color ='#e96900'>事件</font>  |[checkChanged](#checkChanged)| 选择切换时触发

#### <font color ='#40A977'>**1.**</font> 属性

>###### <span id=enabled><font color ='#42b983'>**enabled**</font></span>: 是否可点击

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : true
- 说明 : 缺省为true控制组件可点击，当为false时不支持点击
- 示例 ：

  ```javascript

  //对组件进行操作，需要先对组件进行实例化。（用两个组件进行属性对比）
  var do_CheckBox = ui("do_CheckBox_1"); //对do_CheckBox组件实例化，其中do_CheckBox_1为ui页面上do_CheckBox组件的id
  var do_CheckBox_1 = ui("do_CheckBox_2");

  //do_CheckBox的enabled属性设置成true
  do_CheckBox.enabled = true;

  //do_CheckBox_1的enabled属性设置成false
  do_CheckBox_1.enabled = false;

  ```

[回到顶部](#top)

>###### <span id=checked><font color ='#42b983'>**checked**</font></span>: 是否选中

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : false
- 说明 : 为true时为选中状态，false为未选中状态
- 示例 ：

  ```javascript

  //checked属性设置成true
  do_CheckBox.checked = true;
  do_CheckBox.text = "选中状态";

  //checked属性设置成false
  do_CheckBox_1.checked = false;
  do_CheckBox_1.text = "未选中状态";

  ```
  下图为示例代码id为"do_CheckBox"的checked属性设置为true选中和id为"do_CheckBox_1"的checked属性设置为false未选中的效果图。

  <img src="../../images/checkbox_checked.png" height="380" width="330" >

[回到顶部](#top)


>###### <span id=text><font color ='#42b983'>**text**</font></span>: 文本显示内容

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 :
- 说明 : 获取或设置与此控件关联的文本。
- 示例 ：

  ```javascript

  //将id为do_CheckBox的组件的text不赋值，id为do_CheckBox_1的text属性赋值为"text属性"；

  do_CheckBox_1.text = "text属性";

  ```

  下图为示例代码id为"do_CheckBox"的text属性未赋值和id为"do_CheckBox_1"的text属性赋值为"text属性"的效果图。

  <img src="../../images/checkbox_text.png" height="380" width="330" >

[回到顶部](#top)


>###### <span id=fontColor><font color ='#42b983'>**fontColor**</font></span>: 字体颜色

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 000000FF
- 说明 : 设置字体显示颜色，值格式为：8位16进制字符，前6位是RGB颜色值，后两位是透明度（Alpha），例如：000000FF
- 示例 ：

  ```javascript

  //fontColor属性设置为红色
  do_CheckBox.fontColor = "FF0000FF";

  //fontColor属性设置为后两位是透明度为50的红色
  do_CheckBox_1.fontColor = "FF000050";   //后两位是透明度（Alpha）

  ```

  下图为示例代码id为"do_CheckBox"的fontColor属性设置为"FF0000FF"红色和id为"do_CheckBox_1"的fontColor属性设置为"FF000050"后两位透明度为50的效果图。

  <img src="../../images/checkbox_fontColor.png" height="380" width="330" >

[回到顶部](#top)


>###### <span id=fontStyle><font color ='#42b983'>**fontStyle**</font></span>: 字体风格

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : normal
- 说明 :包含4种类型：
  ```
    normal：常规
    bold：粗体
    italic：斜体
    bold_italic：粗斜体（iOS平台不支持）

  ```
- 示例 ：

  ```javascript

  // fontStyle属性设置成常规
	do_CheckBox.fontStyle = "normal";

  // fontStyle属性设置成粗体
	do_CheckBox.fontStyle = "bold";

  // fontStyle属性设置成斜体
	do_CheckBox.fontStyle = "italic";

  // fontStyle属性设置成粗斜体
	do_CheckBox.fontStyle = "bold_italic";//(iOS平台不支持)

  ```
  下图为示例代码id为"do_CheckBox"的fontStyle属性分别设置为"normal","bold","italic","bold_italic"的效果图。

  <img src="../../images/checkbox_fontStyle.png" height="380" width="330" >

[回到顶部](#top)


>###### <span id=textFlag><font color ='#42b983'>**textFlag**</font></span>: 字体标示

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : normal
- 编辑类型 : 只允许设计区内修改。
- 说明 :包含3种类型：
  ```
    normal：常规
    underline ：下划线
    strikethrough ：删除线
  ```

  下图为通过设计器修改id为"do_CheckBox"的textFlag属性分别设置为"normal","underline","strikethrough"的效果图。

  <img src="../../images/checkbox_textFlag.png" height="380" width="330" >

>###### <span id=fontSize><font color ='#42b983'>**fontSize**</font></span>: 字体大小

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 17
- 说明 :
- 示例 ：

  ```javascript

  //id为"do_CheckBox"的fontSize属性设置成20
  do_CheckBox.fontSize = 20;

  //id为"do_CheckBox_1"的fontSize属性设置成30
  do_CheckBox_1.fontSize = 30;

  ```
  下图为示例代码id为"do_CheckBox"的fontSize属性设置为"20"和id为"do_CheckBox_1"的fontSize属性设置为"30"的效果图。

  <img src="../../images/checkbox_fontSize.png" height="380" width="330" >

#### <font color ='#40A977'>**2.**</font> 同步方法

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

[回到顶部](#top)


>###### <span id=checkChanged><font color ='#e96900'>**checkChanged**</font></span>: 选择切换时触发

- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: 返回当前控件状态
- 说明: 选择切换时触发
- 示例:
  ```javascript

  do_CheckBox.on("checkChanged", function(data) {
  	if (data == true) {
  		deviceone.print("选中状态");
  	} else {
  		deviceone.print("未选中状态");
  	}
  })

  ```

#### <font color ='#40A977'>**5.**</font> 常见问题
- 1.http://doc.deviceone.net/web/doc/detail_course/components/do_CheckBox.htm
