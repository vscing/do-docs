---
title: do_Picker 组件
---

### do_Picker 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_Picker)
 可上下滑动选择的单选控件，停留在中间即为选中项

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#42b983'>属性</font>  |[index](#index)| 当前选中的数据索引
<font color ='#42b983'>属性</font>  |[fontSize](#fontSize)| 字体大小
<font color ='#42b983'>属性</font>  |[fontColor](#fontColor)| 字体颜色
<font color ='#42b983'>属性</font>  |[fontStyle](#fontStyle)| 字体风格
<font color ='#42b983'>属性</font>  |[selectedFontColor](#selectedFontColor)| 被选中字体颜色
<font color ='#42b983'>属性</font>  |[selectedFontStyle](#selectedFontStyle)| 被选中字体风格
<font color ='#0092db'>同步方法</font>  |[bindItems](#bindItems)| 绑定item的数据
<font color ='#0092db'>同步方法</font>  |[refreshItems](#refreshItems)| 刷新item数据
<font color ='#e96900'>事件</font>  |[selectChanged](#selectChanged)| 当数据变化或数据索引变化触发

#### <font color ='#40A977'>**1.**</font> 属性

>###### <span id=index><font color ='#42b983'>**index**</font></span>: 当前选中的数据索引

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 :
- 说明 : 数据的索引值，设置时会切换数据选择，索引小于0时指向数组第一个数据，越界时指向数组最后一个数据
- 示例:

  ```javascript

  var do_Picker = ui("do_Picker_1");  //实例化
  do_Picker.index = 1;

  ```

>###### <span id=fontSize><font color ='#42b983'>**fontSize**</font></span>: 字体大小

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 20
- 说明 : 字体大小
- 示例:

  ```javascript

  do_Picker.fontSize = 30;

  ```

>###### <span id=fontColor><font color ='#42b983'>**fontColor**</font></span>: 字体颜色

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 000000FF
- 说明 : 设置字体显示颜色，值格式为：8位16进制字符，前6位是RGB颜色值，后两位是透明度（Alpha），例如：000000FF
- 示例:

  ```javascript

  do_Picker.fontColor = "000000FF";

  ```

>###### <span id=fontStyle><font color ='#42b983'>**fontStyle**</font></span>: 字体风格

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : normal
- 说明 : 包含4种类型：normal：常规bold：粗体italic：斜体bold_italic：粗斜体（iOS平台不支持）
- 示例:

  ```javascript

  do_Picker.fontStyle = "bold";

  ```

>###### <span id=selectedFontColor><font color ='#42b983'>**selectedFontColor**</font></span>: 被选中字体颜色

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 000000FF
- 说明 : 设置选中项字体颜色，值格式为：8位16进制字符，前6位是RGB颜色值，后两位是透明度（Alpha），例如：000000FF
- 示例:

  ```javascript

  do_Picker.selectedFontColor = "FF0000FF"; //选中的字体设置为红色

  ```

>###### <span id=selectedFontStyle><font color ='#42b983'>**selectedFontStyle**</font></span>: 被选中字体风格

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : normal
- 说明 : 设置选中项字体样式,包含4种类型：normal：常规bold：粗体italic：斜体bold_italic：粗斜体（iOS平台不支持）
- 示例:

  ```javascript

  do_Picker.selectedFontStyle = "italic";

  ```

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=bindItems><font color ='#0092db'>**bindItems**</font></span>: 绑定item的数据

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **data** |<font color ='#808000'>**object**</font> | 否 | |需有一项为text用于显示文字，比如['a''b'...]
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 可绑定listData实例
- 示例:

  ```javascript

  var listdata = mm("do_ListData");
  do_Picker.bindItems(listdata);
  var datas = [ "那年花开月正圆-孙俪", "三生三世十里桃花-杨幂", "秦时丽人明月心-迪丽热巴", "楚乔传-赵丽颖" ];
  listdata.addData(datas);
  do_Picker.refreshItems();

  ```
  下图为示例代码效果图。

  <div>

  <img src="../../images/picker_bindItems.png" height="400" width="330" >

  </div>

[回到顶部](#top)

>##### <span id=refreshItems><font color ='#0092db'>**refreshItems**</font></span>: 刷新item数据

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明:
- 示例:参考bindItems方法，绑定完需要refreshItems刷新下

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=selectChanged><font color ='#e96900'>**selectChanged**</font></span>: 当数据变化或数据索引变化触发

- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 返回选中数据的索引
- 说明: 当数据变化或数据索引变化触发
- 示例:

  ```javascript

  do_Picker.on("selectChanged", function(data) {
  	deviceone.print(JSON.stringify(data));
  })

  ```

  ```
  
  以上代码滑动到索引2的位置daya的返回值为:2

  ```

[回到顶部](#top)
