---
title: do_SegmentView 组件
---

### do_SegmentView 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_SegmentView)
 分段选择视图，支持手势滑动和点击选中一个index，通常和do_SlideView结合在一起使用，互相联动；当height=-1时，表示自动宽度

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#42b983'>属性</font>  |[index](#index)| 当前滑动cell索引
<font color ='#42b983'>属性</font>  |[templates](#templates)| cell对应的模板UI文件组
<font color ='#0092db'>同步方法</font>  |[bindItems](#bindItems)| 绑定item的数据
<font color ='#0092db'>同步方法</font>  |[refreshItems](#refreshItems)| 刷新item数据
<font color ='#e96900'>事件</font>  |[indexChanged](#indexChanged)| 点击cell加载完成后触发

#### <font color ='#40A977'>**1.**</font> 属性

>###### <span id=index><font color ='#42b983'>**index**</font></span>: 当前滑动cell索引

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 0
- 说明 : 设置当前滑动cell索引值，默认为0

>###### <span id=templates><font color ='#42b983'>**templates**</font></span>: cell对应的模板UI文件组

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 :
- 说明 : 一个SegmentView可以有多个cell模板，这个属性是一个json array，每一个元素都是一个source ui文件。这个属性的格式类似如下： source://view/cell1.ui,source://view/cell2.ui,source://view/cell3.ui

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=bindItems><font color ='#0092db'>**bindItems**</font></span>: 绑定item的数据

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **data** |<font color ='#808000'>**object**</font> | 否 | |
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 可绑定listData实例
- 示例:

  ```javascript
  var listData0 = mm("do_ListData");
   do_SegmentView.bindItems({
  		data : listData0
  		});
   //通过template属性来选定模板
   var data0 = [
  	                 	{template:0,"$text":"index 0"},
  	                 	{template:0,"$text":"index 1"},
  	                 	{template:1,"$text":"index 2"},
  	                 	{template:0,"$text":"index 3"},
  	                 	{template:1,"$text":"index 4"},
  	                 	{template:1,"$text":"index 5"},
  	                 	{template:0,"$text":"index 6"},
  	                 	{template:1,"$text":"index 7"},
  	                 	{template:1,"$text":"index 8"}
  	           ];
  	listData0.addData(data0);


  ```

[回到顶部](#top)

>##### <span id=refreshItems><font color ='#0092db'>**refreshItems**</font></span>: 刷新item数据

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明:
- 示例:

  ```javascript
  do_SegmentView.refreshItems()

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=indexChanged><font color ='#e96900'>**indexChanged**</font></span>: 点击cell加载完成后触发

- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 返回当前cell的index
- 说明: 点击cell加载完成后触发
- 示例:

  ```javascript
  do_SegmentView.on("indexChanged",function(data){
	deviceone.print(data,"切换view触发")
  })

  ```

[回到顶部](#top)
