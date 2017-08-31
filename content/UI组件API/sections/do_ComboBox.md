---
title: do_ComboBox 组件
---

### do_ComboBox 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_ComboBox)
 点击控件会弹出一个选择列表，单击选项即可选中

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#42b983'>属性</font>  |[fontColor](#fontColor)| 字体前景色
<font color ='#42b983'>属性</font>  |[fontSize](#fontSize)| 字体大小
<font color ='#42b983'>属性</font>  |[fontStyle](#fontStyle)| 字体风格
<font color ='#42b983'>属性</font>  |[textFlag](#textFlag)| 字体标示
<font color ='#42b983'>属性</font>  |[index](#index)| 当前选中的数据索引
<font color ='#42b983'>属性</font>  |[items](#items)| 数据集合
<font color ='#42b983'>属性</font>  |[textAlign](#textAlign)| 文本对齐方式
<font color ='#0092db'>同步方法</font>  |[bindItems](#bindItems)| 绑定item的数据
<font color ='#0092db'>同步方法</font>  |[refreshItems](#refreshItems)| 刷新item数据
<font color ='#e96900'>事件</font>  |[selectChanged](#selectChanged)| 当数据变化或数据索引变化触发

#### <font color ='#40A977'>**1.**</font> 属性

>###### <span id=fontColor><font color ='#42b983'>**fontColor**</font></span>: 字体前景色

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 000000FF
- 说明 : 设置字体显示颜色，值格式为：8位16进制字符，前6位是RGB颜色值，后两位是透明度（Alpha），例如：000000FF
- 示例 ：

  ```javascript

  //fontColor属性设置为FF0000FF
  do_ComboBox.fontColor = "FF00FFFF";

  //fontColor属性设置为后两位是透明度为50
  do_ComboBox_1.fontColor = "FF00FF50";   //后两位是透明度（Alpha）

  ```

  下图分别为示例代码id为"do_ComboBox"的fontColor属性设置为"FF00FFFF"和id为"do_ComboBox_1"的fontColor属性设置为"FF00FF50"后两位透明度为50的效果图。

  <div align="center">

  <img src="../../images/combobox_fontColor.png" height="380" width="310" >

  <img src="../../images/combobox_fontColor_1.png" height="380" width="310" >

   </div>


[回到顶部](#top)

>###### <span id=fontSize><font color ='#42b983'>**fontSize**</font></span>: 字体大小

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 17
- 说明 :
- 示例 ：

  ```javascript

  //id为"do_ComboBox"的fontSize属性设置成40
  do_ComboBox.fontSize = 40;

  //id为"do_ComboBox_1"的fontSize属性设置成30
  do_ComboBox_1.fontSize = 30;

  ```

  下图分别为示例代码id为"do_ComboBox"的fontSize属性设置为40和id为"do_ComboBox_1"的fontSize属性设置为30的效果图。

  <div align="center">

  <img src="../../images/combobox_fontSize.png" height="380" width="310" >

  <img src="../../images/combobox_fontSize_1.png" height="380" width="310" >

  </div>

[回到顶部](#top)

>###### <span id=fontStyle><font color ='#42b983'>**fontStyle**</font></span>: 字体风格

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : normal
- 说明 : 包含4种类型：normal：常规bold：粗体italic：斜体bold_italic：粗斜体（iOS平台不支持）
- 示例 ：

  ```javascript

  // fontStyle属性设置成常规
	do_ComboBox.fontStyle = "normal";

  // fontStyle属性设置成粗体
	do_ComboBox.fontStyle = "bold";

  // fontStyle属性设置成斜体
	do_ComboBox.fontStyle = "italic";

  // fontStyle属性设置成粗斜体
	do_ComboBox.fontStyle = "bold_italic";//(iOS平台不支持)

  ```

  下图为示例代码id为"do_ComboBox"的fontStyle属性分别设置为"normal","bold","italic","bold_italic"的效果图。

  <div align="center">

  <img src="../../images/combobox_fontStyle_normal.png" height="380" width="310" >

  <img src="../../images/combobox_fontStyle_bold.png" height="380" width="310" >

  <img src="../../images/combobox_fontStyle_italic.png" height="380" width="310" >

  <img src="../../images/combobox_fontStyle_bold_italic.png" height="380" width="310" >

   </div>


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

  下图为通过设计器修改id为"do_ComboBox"的textFlag属性分别设置为"normal","underline","strikethrough"的效果图。

  <div align="center">

  <img src="../../images/combobox_textFlag_normal.png" height="380" width="310" >

  <img src="../../images/combobox_textFlag_underline.png" height="380" width="310" >

  <img src="../../images/combobox_textFlag_strikethrough.png" height="380" width="310" >

  </div>

[回到顶部](#top)

>###### <span id=index><font color ='#42b983'>**index**</font></span>: 当前选中的数据索引

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 :
- 说明 : 数据的索引值，设置时会切换数据选择，索引小于0时指向数组第一个数据，越界时指向数组最后一个数据
- 示例 ：

  ```javascript

  do_ComboBox.index = 0; // 索引0
  do_ComboBox_1.index = 1; // 索引1

  ```

  下图是示例代码id为"do_ComboBox"的index属性等于0和id为"do_ComboBox_1"的index属性等于1的效果图。

  <div align="center">

  <img src="../../images/combobox_index.png" height="380" width="310" >

  <img src="../../images/combobox_index_1.png" height="380" width="310" >

  </div>

[回到顶部](#top)
>###### <span id=items><font color ='#42b983'>**items**</font></span>: 数据集合

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 :
- 说明 : 可供选择的数据集合，中间用逗号隔开多个文本，如'北京,上海,广州...'
- 示例 ：

  ```javascript

  do_ComboBox.items = "index0,index1,index2,index3";

  ```
  下图是示例代码id为"do_ComboBox"的items属性赋值的效果图。

  <img src="../../images/combobox_items.png" height="380" width="330" >

[回到顶部](#top)
>###### <span id=textAlign><font color ='#42b983'>**textAlign**</font></span>: 文本对齐方式

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : left
- 编辑类型 : 只允许设计区内修改。
- 说明 : 对齐方式为以下3种：
  ```

  left ：左对齐（默认）
  center ：居中
  right ：右对齐     

  ```
  <!-- 下图为通过设计器修改id为"do_ComboBox"的textAlign属性分别设置为"left","center","right"的效果图。 -->

  <!-- <img src="../../images/combobox_textAlign.png" height="380" width="330" > -->

[回到顶部](#top)
#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=bindItems><font color ='#0092db'>**bindItems**</font></span>: 绑定item的数据

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **data** |<font color ='#808000'>**object**</font> | 否 | |可绑定listData实例
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明:
```
  [
    {'text':'a1','id':'1'},
    {'text':'a2','id':'2'}
  ]
  其中text字段是必须的，用于显示文本内容，这里显示的就是a1，a2，其他字段可任意增加，根据选择的item索引获取内容

  ```

- 示例:

  ```javascript

  //--bindItems方法给组件赋值
  var listdata = mm("do_ListData");
  do_ComboBox_1.bindItems(listdata);    // 绑定item的数据
  listdata.addData([ {
  	text : "索引0"
  }, {
  	text : "索引1"
  }, {
  	text : "索引2"
  }, {
  	text : "索引3"
  } ])
  do_ComboBox_1.refreshItems();    //给combobox绑定数据后，需要刷新item数据

  ```
  下图是示例代码id为"do_ComboBox_1"绑定item的数据的效果图。

  <img src="../../images/combobox_bindItems.png" height="380" width="330" >

[回到顶部](#top)

>##### <span id=refreshItems><font color ='#0092db'>**refreshItems**</font></span>: 刷新item数据

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明:
- 示例: 参考bindItems方法的示例代码

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=selectChanged><font color ='#e96900'>**selectChanged**</font></span>: 当数据变化或数据索引变化触发

- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 返回选中数据的索引
- 说明: 当数据变化或数据索引变化触发。（点击控件会弹出一个选择列表，单击选项即可修改其索引）
- 示例:

  ```javascript

  do_ComboBox.on("selectChanged", function(data) {
  	deviceone.print(data);
  })

  ```

[回到顶部](#top)
