---
title: do_VerticalSlideView 组件
---

### do_VerticalSlideView 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_VerticalSlideView)
 这个UI组件包含多个子视图(UI文件），实现多个子视图之间上下平缓滑动效果，该组件还支持设置多个不同模板视图

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#42b983'>属性</font>  |[allowGesture](#allowGesture)| 是否支持手势滑动
<font color ='#42b983'>属性</font>  |[index](#index)| 当前滑动UIView索引
<font color ='#42b983'>属性</font>  |[templates](#templates)| 显示视图对应UI模板文件
<font color ='#0092db'>同步方法</font>  |[bindItems](#bindItems)| 绑定视图模板数据
<font color ='#0092db'>同步方法</font>  |[refreshItems](#refreshItems)| 刷新数据
<font color ='#e96900'>事件</font>  |[indexChanged](#indexChanged)| 滑动显示当前视图后触发该事件

#### <font color ='#40A977'>**1.**</font> 属性

>###### <span id=allowGesture><font color ='#42b983'>**allowGesture**</font></span>: 是否支持手势滑动

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : true
- 说明 : 当属性值为true时，组件可通过手势上下滑动来切换页面；为false时，手势无法滑动，只能通过修改index来切换页面，windowsPC平台不支持

>###### <span id=index><font color ='#42b983'>**index**</font></span>: 当前滑动UIView索引

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 0
- 说明 : 设置滑动视图索引值，默认为0

>###### <span id=templates><font color ='#42b983'>**templates**</font></span>: 显示视图对应UI模板文件

- 数据类型 : <font color ='#808000'>**object**</font>
- 默认值 :
- 说明 : 可以设置一个或多个UI模板文件，值为String类型，多个模板之间分别用“,”分隔，例如：“source://view/temp/t0.ui, source://view/temp/t1.ui”

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=bindItems><font color ='#0092db'>**bindItems**</font></span>: 绑定视图模板数据

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **data** |<font color ='#808000'>**object**</font> | 否 | |
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 绑定数据类型为do_ListData实例
- 示例:

  ```javascript
  var listData1 = mm("do_ListData");
  var do_VerticalSlideView = ui("do_VerticalSlideView")
	var data1 = [
		          	{template:0,"$text":"5"},
		          	{template:1,"$text":"6"},
		          	{template:2,"$text":"7"},
		          	{template:3,"$text":"8"},
		          	{template:4,"$text":"9"}
		          ];
		do_VerticalSlideView.bindItems({data:listData1});

  ```

[回到顶部](#top)

>##### <span id=refreshItems><font color ='#0092db'>**refreshItems**</font></span>: 刷新数据

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 支持动态刷新当前视图显示数据
- 示例:

  ```javascript
  do_VerticalSlideView.refreshItems()

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=indexChanged><font color ='#e96900'>**indexChanged**</font></span>: 滑动显示当前视图后触发该事件

- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 返回当前index
- 说明: 滑动显示当前视图后触发该事件
- 示例:

  ```javascript
  do_VerticalSlideView.on("indexChanged",function(data){
    deviceone.print(data,"切换后的index")
  })

  ```

[回到顶部](#top)
