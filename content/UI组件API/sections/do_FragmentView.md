---
title: do_FragmentView 组件
---

### do_FragmentView 组件

 支持平台: iOS7.0,Android14 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_FragmentView)
 多页面滑动视图，支持从最左侧或右侧边缘滑出视图，整体侧滑视图带有缩放和渐变效果；

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#42b983'>属性</font>  |[supportGesture](#supportGesture)| 支持手势滑动
<font color ='#42b983'>属性</font>  |[templates](#templates)| 显示视图对应UI模板文件
<font color ='#42b983'>属性</font>  |[allowAnimation](#allowAnimation)| 动画缩放效果
<font color ='#0092db'>同步方法</font>  |[reset](#reset)| 重置为初始视图
<font color ='#0092db'>同步方法</font>  |[showLeft](#showLeft)| 显示左侧视图
<font color ='#0092db'>同步方法</font>  |[showRight](#showRight)| 显示右侧视图
<font color ='#0092db'>同步方法</font>  |[bindItems](#bindItems)| 绑定视图模板数据
<font color ='#0092db'>同步方法</font>  |[refreshItems](#refreshItems)| 刷新数据

#### <font color ='#40A977'>**1.**</font> 属性

>###### <span id=supportGesture><font color ='#42b983'>**supportGesture**</font></span>: 支持手势滑动

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : both
- 说明 : 包含both、left和right三种类型，缺省both表示同时支持左右滑动

>###### <span id=templates><font color ='#42b983'>**templates**</font></span>: 显示视图对应UI模板文件

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 :
- 编辑类型 : 只允许设计区内修改
- 说明 : 可以设置一个或多个UI模板文件，值为String类型，多个模板之间分别用“,”分隔，例如：“source://view/temp/left.ui,source://view/temp/middle.ui,source://view/temp/right.ui”

>###### <span id=allowAnimation><font color ='#42b983'>**allowAnimation**</font></span>: 动画缩放效果

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : false
- 编辑类型 : 只允许设计区内修改
- 说明 : 允许滑动或显示时有动画缩放效果,false表示不允许

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=reset><font color ='#0092db'>**reset**</font></span>: 重置为初始视图

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明:如果组件当前显示的是左侧视图或右侧视图，调用该方法会回到主视图页面
- 示例:

  ```javascript

  var do_FragmentView = ui("do_FragmentView_1"); // 实例化do_FragmentView组件
  do_FragmentView.reset();  //重置为初始视图，回到主视图页面

  ```

[回到顶部](#top)

>##### <span id=showLeft><font color ='#0092db'>**showLeft**</font></span>: 显示左侧视图

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明:
- 示例:
  ```javascript

  do_FragmentView.showLeft();   //显示左侧视图

  ```
  显示左侧视图，效果图如下：          
  <img src="../../images/fragmentview_left.png" height="350" width="330" >


[回到顶部](#top)

>##### <span id=showRight><font color ='#0092db'>**showRight**</font></span>: 显示右侧视图

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明:
- 示例:
  ```javascript

  do_FragmentView.showRight();   //显示右侧视图

  ```
  显示右侧视图，效果图如下：          
  <img src="../../images/fragmentview_right.png" height="350" width="330" >

[回到顶部](#top)

>##### <span id=bindItems><font color ='#0092db'>**bindItems**</font></span>: 绑定视图模板数据

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **data** |<font color ='#808000'>**object**</font> | 否 | |
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 可绑定listData实例，addData数据内容为JSON字符串，key值分别为：template（主视图），leftTemplate（左侧视图，可选），rightTemplate（右侧视图，可选），value对应templates属性对应UI模板索引值；例如：[{ template:0 ,leftTemplate:1}]表示主视图是templates属性的第一个UI页面，左侧视图是templates属性的第二个UI页面
- 示例:
  ```javascript

  var listdata = mm("do_ListData"); // 实例化do_ListData对象

  // 给listdata添加数据，左中右三个页面及页面上绑定的数据
  listdata.addData([ {
  	leftTemplate : 0,     //左侧视图是templates属性的第一个UI页面
  	template : 1,         //主视图是templates属性的第二个UI页面
  	rightTemplate : 2,    //右侧视图是templates属性的第三个UI页面
  	$leftImage : "source://view/do_FragmentView/image/default.png",
  	middle_title : "多页面滑动视图",
  	$rightImage : "source://view/do_FragmentView/image/right.png"
  } ]);

  do_FragmentView.bindItems(listdata); // do_FragmentView绑定do_ListData实例


  ```
  绑定数据之后的效果图如下：     
  <div align="center">

  <img src="../../images/fragmentview_left.png" height="350" width="310" >

  <img src="../../images/fragmentview_middle.png" height="350" width="310" >

  <img src="../../images/fragmentview_right.png" height="350" width="310" >

  </div>

[回到顶部](#top)

>##### <span id=refreshItems><font color ='#0092db'>**refreshItems**</font></span>: 刷新数据

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 支持动态刷新当前视图显示数据
- 说明:
- 示例:

  ```javascript

  //重新绑定数据
  listdata.removeAll();
	listdata.addData([ {
		leftTemplate : 0,
		template : 1,
		rightTemplate : 2,
		$leftImage : "source://view/do_FragmentView/image/right.png",
		middle_title : "刷新数据",
		$rightImage : "source://view/do_FragmentView/image/default.png"
	} ]);
	do_FragmentView.refreshItems(); //刷新当前视图显示数据

  ```
  刷新之后的效果图如下：     
  <div align="center">

  <img src="../../images/fragmentview_left1.png" height="350" width="310" >

  <img src="../../images/fragmentview_middle1.png" height="350" width="310" >

  <img src="../../images/fragmentview_right1.png" height="350" width="310" >

  </div>

#### <font color ='#40A977'>**3.**</font> 异步方法

#### <font color ='#40A977'>**4.**</font> 事件

#### <font color ='#40A977'>**5.**</font> 常见问题

#### <font color ='#40A977'>**6.**</font> 基本配置


[回到顶部](#top)
