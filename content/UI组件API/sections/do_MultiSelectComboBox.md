---
title: do_MultiSelectComboBox 组件
---

### do_MultiSelectComboBox 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_MultiSelectComboBox)
 多选择框列表，支持选一个或多项功能

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#42b983'>属性</font>  |[text](#text)| 文本显示内容
<font color ='#42b983'>属性</font>  |[fontColor](#fontColor)| 字体颜色
<font color ='#42b983'>属性</font>  |[fontSize](#fontSize)| 字体大小
<font color ='#42b983'>属性</font>  |[fontStyle](#fontStyle)| 字体风格
<font color ='#42b983'>属性</font>  |[textFlag](#textFlag)| 字体标示
<font color ='#42b983'>属性</font>  |[indexs](#indexs)| 当前选中的数据索引数组
<font color ='#42b983'>属性</font>  |[items](#items)| 数据集合
<font color ='#42b983'>属性</font>  |[textAlign](#textAlign)| 文本对齐方式
<font color ='#0092db'>同步方法</font>  |[bindItems](#bindItems)| 绑定item的数据
<font color ='#0092db'>同步方法</font>  |[refreshItems](#refreshItems)| 刷新item数据
<font color ='#e96900'>事件</font>  |[selectChanged](#selectChanged)| 选中列表项触发事件

#### <font color ='#40A977'>**1.**</font> 属性

>###### <span id=text><font color ='#42b983'>**text**</font></span>: 文本显示内容

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 :
- 说明 : 获取或设置与此控件关联的文本。
- 示例:

  ```javascript

  var do_MultiSelectComboBox = ui("do_MultiSelectComboBox_1");  //实例化
  do_MultiSelectComboBox.text = "------点击请选择------";

  ```

>###### <span id=fontColor><font color ='#42b983'>**fontColor**</font></span>: 字体颜色

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 000000FF
- 说明 : 设置字体显示颜色，值格式为：8位16进制字符，前6位是RGB颜色值，后两位是透明度（Alpha），例如：000000FF
- 示例:

  ```javascript

  do_MultiSelectComboBox.fontColor = "FF0000FF";

  ```

>###### <span id=fontSize><font color ='#42b983'>**fontSize**</font></span>: 字体大小

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 17
- 说明 :
- 示例:

  ```javascript

  do_MultiSelectComboBox.fontSize = 30;

  ```

>###### <span id=fontStyle><font color ='#42b983'>**fontStyle**</font></span>: 字体风格

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : normal
- 说明 : 包含4种类型：normal：常规bold：粗体italic：斜体bold_italic：粗斜体
- 示例:

  ```javascript

  do_MultiSelectComboBox.fontStyle = "bold";

  ```

>###### <span id=textFlag><font color ='#42b983'>**textFlag**</font></span>: 字体标示

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : normal
- 编辑类型 : 只允许设计区内修改。
- 说明 : 包含3种类型：normal：常规underline ：下划线strikethrough ：删除线；windows平台不支持

>###### <span id=indexs><font color ='#42b983'>**indexs**</font></span>: 当前选中的数据索引数组

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 0
- 说明 : 数据的索引值，设置时会切换数据选择
- 示例:

  ```javascript

  do_MultiSelectComboBox.indexs = 1;

  ```

>###### <span id=items><font color ='#42b983'>**items**</font></span>: 数据集合

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 :
- 说明 : 可供选择的数据集合，中间用逗号隔开多个文本，如'北京,上海,广州...'
- 示例:

  ```javascript

  do_MultiSelectComboBox.items = "北京,上海,广州,三亚";

  ```

>###### <span id=textAlign><font color ='#42b983'>**textAlign**</font></span>: 文本对齐方式

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : left
- 编辑类型 : 只允许设计区内修改。
- 说明 : 对齐方式为以下3种：left 左对齐（默认）；center 居中；right 右对齐

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=bindItems><font color ='#0092db'>**bindItems**</font></span>: 绑定item的数据

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **data** |<font color ='#808000'>**object**</font> | 否 | |比如[{'text':'a1','id':'1'},{'text':'a2','id':'2'}]，其中text字段是必须的，用于显示文本内容，这里显示的就是a1，a2，其他字段可任意增加，根据选择的item索引获取内容
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 可绑定listData实例
- 示例:

  ```javascript

  var listdata = mm("do_ListData");
  do_MultiSelectComboBox.bindItems(listdata);

  var datas = [ {
  	   text : "那年花开月正圆-孙俪"
    }, {
    	text : "三生三世十里桃花-杨幂"
    }, {
    	text : "秦时丽人明月心-迪丽热巴"
    }, {
    	text : "楚乔传-赵丽颖"
    } ];

  listdata.addData(datas);
  do_MultiSelectComboBox.refreshItems();

  ```

  下图为以上代码的效果图。

  <div>

  <img src="../../images/multiselectcombobox_bindItems.png" height="400" width="330" >

  </div>


[回到顶部](#top)

>##### <span id=refreshItems><font color ='#0092db'>**refreshItems**</font></span>: 刷新item数据

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明:
- 示例:  参考bindItems方法，绑定完需要refreshItems刷新下

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=selectChanged><font color ='#e96900'>**selectChanged**</font></span>: 选中列表项触发事件

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回选中数据的索引数组
- 说明: 选中列表项触发事件
- 示例:

  ```javascript

  do_MultiSelectComboBox.on("selectChanged", function(data) {
  	deviceone.print(JSON.stringify(data));
  })

  ```

  ```
  分别点击索引1,2,0时返回的data值为：
  ["1","2","0"]

  ```

[回到顶部](#top)
