---
title: do_CoverFlowView 组件
---

### do_CoverFlowView 组件

 支持平台: iOS7.0,Android4.0以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_CoverFlowView)
 画廊视图，这个UI组件包含多个子视图，实现多个子视图之间左右平缓滑动效果；该组件支持设置多个模板视图，要求多个模板大小相同。

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#42b983'>属性</font>  |[looping](#looping)| 左右无限滑动
<font color ='#42b983'>属性</font>  |[spacing](#spacing)| 间距
<font color ='#42b983'>属性</font>  |[index](#index)| 当前滑动View索引
<font color ='#42b983'>属性</font>  |[templates](#templates)| 显示视图对应UI模板文件
<font color ='#0092db'>同步方法</font>  |[bindItems](#bindItems)| 绑定视图模板数据
<font color ='#0092db'>同步方法</font>  |[refreshItems](#refreshItems)| 刷新数据
<font color ='#e96900'>事件</font>  |[indexChanged](#indexChanged)| 滑动显示当前视图后触发该事件
<font color ='#e96900'>事件</font>  |[touch](#touch)| 点击cell触发

#### <font color ='#40A977'>**1.**</font> 属性

>###### <span id=looping><font color ='#42b983'>**looping**</font></span>: 左右无限滑动

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : false
- 编辑类型 : 只允许设计区内修改
- 说明 : 左右无限循环滑动视图，设置值为true表示支持无限循环滑动，默认为false，windows平台不支持

>###### <span id=spacing><font color ='#42b983'>**spacing**</font></span>: 间距

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 30
- 编辑类型 : 只允许设计区内修改
- 说明 : 页间距，控制两个页面之间的距离
  左图为spacing是10的效果图，右图为spacing是50的效果图：
  <div>
  <img src="../../images/coverflowview_spacsmall.png" height="380" width="320" >

  <img src="../../images/coverflowview_spacbig.png" height="380" width="320" >

  </div>

>###### <span id=index><font color ='#42b983'>**index**</font></span>: 当前滑动View索引

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 0
- 说明 : 设置滑动视图索引值，默认为0，显示数据的第一个页面

  ```javascript

  var do_CoverFlowView = ui("do_CoverFlowView_1");
  //设置滑动索引为1，即展示第二个页面
  do_CoverFlowView.index = 1;

  ```

>###### <span id=templates><font color ='#42b983'>**templates**</font></span>: 显示视图对应UI模板文件

- 数据类型 : <font color ='#808000'>**object**</font>
- 默认值 :
- 编辑类型 : 只允许设计区内修改
- 说明 : 一个CoverFlowView可以有多个cell模板，这个属性是一个json array，每一个元素都是一个ui文件，这些ui文件没有自己的逻辑代码，和CoverFlowView所在的page共用一个脚本环境，多模版时每个模板页面大小需要一致。
这个属性的格式类似如下：

  ```

  [
      "source://view/cell1.ui",
      "source://view/cell2.ui",
      "source://view/cell3.ui"
  ]

  ```

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

  var listdata = mm("do_ListData");           //实例化do_ListData对象
  do_CoverFlowView.bindItems(listdata);       //do_CoverFlowView绑定do_ListData实例

  ```

[回到顶部](#top)

>##### <span id=refreshItems><font color ='#0092db'>**refreshItems**</font></span>: 刷新数据

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 支持动态刷新当前视图显示数据
- 示例:

  ```javascript

  //给listdata添加数据
  listdata.addData([ {
  	template : 0,
  	text : "第一步 打开冰箱门",
  	bg_image : "source://view/do_CoverFlowView/image/bgimg.png",
  	text_fontcolor : "FFFFFFFF"
  }, {
  	template : 0,
  	text : "第二步 把大象塞冰箱里",
  	bg_image : "source://view/do_CoverFlowView/image/bgimg1.png",
  	text_fontcolor : "FF00FFFF"
  }, {
  	template : 1,
  	text : "第三步 把冰箱门关上",
  	bg_image : "source://view/do_CoverFlowView/image/bgimg.png",
  	_image:"source://view/do_CoverFlowView/image/img3.jpg"
  } ]);
  do_CoverFlowView.refreshItems();   //刷新数据

  ```
  绑定数据刷新之后效果图如下：
  <div align="center">

  <img src="../../images/coverflowview_picture1.png" height="380" width="310" >

  <img src="../../images/coverflowview_picture2.png" height="380" width="310" >

  <img src="../../images/coverflowview_picture3.png" height="380" width="310" >

  </div>

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=indexChanged><font color ='#e96900'>**indexChanged**</font></span>: 滑动显示当前视图后触发该事件

- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回当前index
- 说明: 滑动显示当前视图后触发该事件
- 示例:

  ```javascript

  //滑动显示当前视图后触发该事件
  do_CoverFlowView.on("indexChanged",function(_index){
  	  deviceone.print(_index,"当前index");
  })

  ```

[回到顶部](#top)

>###### <span id=touch><font color ='#e96900'>**touch**</font></span>: 点击cell触发

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 当前cell的index值
- 说明: 点击cell触发
- 示例:

  ```javascript

  //点击cell触发
  do_CoverFlowView.on("touch",function(data){
  	  deviceone.print(JSON.stringify(data),"当前index");
  })
  //点击cell时回调函数返回的当前index值
  {
      "index":1
  }

  ```

#### <font color ='#40A977'>**5.**</font> 常见问题

#### <font color ='#40A977'>**6.**</font> 基本配置

[回到顶部](#top)
