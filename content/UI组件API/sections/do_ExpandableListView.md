---
title: do_ExpandableListView 组件
---

### do_ExpandableListView 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_ExpandableListView)
 一个可分组可展开的List视图

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#42b983'>属性</font>  |[allExpanded](#allExpanded)| 是否全部展开
<font color ='#42b983'>属性</font>  |[canScrollToTop](#canScrollToTop)| 是否滚动到屏幕顶部
<font color ='#42b983'>属性</font>  |[groupTemplate](#groupTemplate)| 组模板UI文件
<font color ='#42b983'>属性</font>  |[childTemplate](#childTemplate)| 子项模板UI文件
<font color ='#42b983'>属性</font>  |[selectedColor](#selectedColor)| 按下cell显示的背景色
<font color ='#42b983'>属性</font>  |[isShowbar](#isShowbar)| 是否支持显示滚动条效果
<font color ='#0092db'>同步方法</font>  |[bindItems](#bindItems)| 绑定item的数据
<font color ='#0092db'>同步方法</font>  |[refreshItems](#refreshItems)| 刷新item数据
<font color ='#0092db'>同步方法</font>  |[refreshSpecifiedItems](#refreshSpecifiedItems)| 刷新指定组数据
<font color ='#0092db'>同步方法</font>  |[expandGroup](#expandGroup)| 展开组
<font color ='#0092db'>同步方法</font>  |[collapseGroup](#collapseGroup)| 收缩组
<font color ='#0092db'>同步方法</font>  |[scrollToPosition](#scrollToPosition)| 平滑地滚动到特定位置
<font color ='#e96900'>事件</font>  |[groupTouch](#groupTouch)| 点击group中的cell触发
<font color ='#e96900'>事件</font>  |[childTouch](#childTouch)| 点击child中的cell触发
<font color ='#e96900'>事件</font>  |[groupExpand](#groupExpand)| group展开触发
<font color ='#e96900'>事件</font>  |[groupCollapse](#groupCollapse)| group收缩触发
<font color ='#e96900'>事件</font>  |[scroll](#scroll)| 滑动事件

#### <font color ='#40A977'>**1.**</font> 属性

>###### <span id=allExpanded><font color ='#42b983'>**allExpanded**</font></span>: 是否全部展开

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : false
- 编辑类型 : 只允许设计区内修改
- 说明 : 控制组件初始化时所有group是否全部展开
  左图为设置allExpanded为false，右图为设置allExpanded为true：

  <div>
  <img src="../../images/expandablelistView_expand_false.png" height="380" width="320" >

  <img src="../../images/expandablelistView_expand_true.png" height="380" width="320" >

  </div>

>###### <span id=canScrollToTop><font color ='#42b983'>**canScrollToTop**</font></span>: 是否滚动到屏幕顶部

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : true
- 编辑类型 : 只允许设计区内修改
- 说明 : 属性设置成true时可以通过点击手机状态栏返回内容的顶部；仅支持iOS平台

>###### <span id=groupTemplate><font color ='#42b983'>**groupTemplate**</font></span>: 组模板UI文件

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 无
- 编辑类型 : 只允许设计区内修改
- 说明 : group对应的模板UI文件,如： source://view/group.ui，支持多模版

>###### <span id=childTemplate><font color ='#42b983'>**childTemplate**</font></span>: 子项模板UI文件

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 无
- 编辑类型 : 只允许设计区内修改
- 说明 : child对应的模板UI文件,如： source://view/child.ui，支持多模版。        
  下图是对groupTemplate和childTemplate赋值并绑定数据的效果图：
  <img src="../../images/expandablelistView_template.png" height="380" width="330" >

>###### <span id=selectedColor><font color ='#42b983'>**selectedColor**</font></span>: 按下cell显示的背景色

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 00000000
- 编辑类型 : 只允许设计区内修改
- 说明 : 点击cell时，该cell的背景色会变成设置的颜色（模板背景色为透明时才可以看到效）                                                            
  下图是设置selectedColor为FFD9ECFF的效果图：                                                                     
  <img src="../../images/expandablelistView_selectedColor.png" height="380" width="330" >

>###### <span id=isShowbar><font color ='#42b983'>**isShowbar**</font></span>: 是否支持显示滚动条效果

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : true
- 编辑类型 : 只允许设计区内修改
- 说明 : 为true的时候，当内容超出视图的边界，滚动时屏幕右侧会出现滚动条            
  下图是设置isShowbar为true的效果图：                                       
  <img src="../../images/expandablelistView_isShowbar.png" height="380" width="330" >                                        

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=bindItems><font color ='#0092db'>**bindItems**</font></span>: 绑定item的数据

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **groupData** |<font color ='#808000'>**object**</font> | 否 | |
  **childData** |<font color ='#808000'>**object**</font> | 否 | |
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: groupData和childData都是listData实例
- 示例:

  ```javascript

  var do_ExpandableListView = ui("do_ExpandableListView_1");  //实例化do_ExpandableListView组件
  var group_listdata = mm("do_ListData");    //定义一个do_ListData为groupData
  var child_listdata = mm("do_ListData");    //定义一个do_ListData为childData

  //为group_listdata增加数据
  group_listdata.addData([ {
  	"groupid" : "001001",
  	"img_type" : "source://view/do_ExpandableListView/zk.jpg",
  	"gname" : "MacBook Air"
  }, {
  	"groupid" : "001002",
  	"img_type" : "source://view/do_ExpandableListView/zk.jpg",
  	"gname" : "MacBook Pro"
  }, {
  	"groupid" : "001003",
  	"img_type" : "source://view/do_ExpandableListView/zk.jpg",
  	"gname" : "iMac"
  }, {
  	"groupid" : "001004",
  	"img_type" : "source://view/do_ExpandableListView/zk.jpg",
  	"gname" : "Mac mini"
  } ]);
  //为child_listdata增加数据
  child_listdata.addData([ [ {
  	"groupid" : "001001",
  	"childid" : 496,
  	"cname" : "MacBook Air 11英寸 MJVP2CH/A",
  	"productTypeName" : "MacBook Air",
  	"img":"source://view/do_ExpandableListView/1.png"
  },{
  	"groupid" : "001001",
  	"childid" : 3,
  	"cname" : "MacBook Air 13英寸 MD760CH/A",
  	"productTypeName" : "MacBook Air",
  	"img" : "source://view/do_ExpandableListView/1.png"
  }, {
  	"groupid" : "001001",
  	"childid" : 2,
  	"cname" : "MacBook Air 11英寸 MD712CH/A",
  	"productTypeName" : "MacBook Air",
  	"img":"source://view/do_ExpandableListView/1.png"
  }, {
  	"groupid" : "001001",
  	"childid" : 1,
  	"cname" : "MacBook Air 11英寸 MD711CH/A",
  	"productTypeName" : "MacBook Air",
  	"img":"source://view/do_ExpandableListView/1.png"
  } ], [ {
  	"groupid" : "001002",
  	"childid" : 492,
  	"cname" : "MacBook Pro 13英寸 MF841CH/A",
  	"productTypeName" : "MacBook Pro",
  	"img":"source://view/do_ExpandableListView/1.png"
  }, {
  	"groupid" : "001002",
  	"childid" : 491,
  	"cname" : "MacBook Pro 13英寸 MF840CH/A",
  	"productTypeName" : "MacBook Pro",
  	"img":"source://view/do_ExpandableListView/1.png"
  }, {
  	"groupid" : "001002",
  	"childid" : 401,
  	"cname" : "MacBook Pro 15英寸 MD322CH/A",
  	"productTypeName" : "MacBook Pro",
  	"img":"source://view/do_ExpandableListView/1.png"
  }, {
  	"groupid" : "001002",
  	"childid" : 9,
  	"cname" : "MacBook Pro 13英寸 MD101CH/A",
  	"productTypeName" : "MacBook Pro",
  	"img":"source://view/do_ExpandableListView/1.png"
  } ], [ {
  	"groupid" : "001003",
  	"childid" : 434,
  	"cname" : "iMac 27英寸 MF886CH/A",
  	"productTypeName" : "iMac",
  	"img":"source://view/do_ExpandableListView/1.png"
  }, {
  	"groupid" : "001003",
  	"childid" : 30,
  	"cname" : "iMac 27英寸 MD096CH/A",
  	"productTypeName" : "iMac",
  	"img":"source://view/do_ExpandableListView/1.png"
  }, {
  	"groupid" : "001003",
  	"childid" : 29,
  	"cname" : "iMac 27英寸 MD095CH/A",
  	"productTypeName" : "iMac",
  	"img":"source://view/do_ExpandableListView/1.png"
  },{
  	"groupid" : "001003",
  	"childid" : 23,
  	"cname" : "iMac 21.5英寸 ME086CH/A",
  	"productTypeName" : "iMac",
  	"img":"source://view/do_ExpandableListView/1.png"
  } ], [ {
  	"groupid" : "001004",
  	"childid" : 523,
  	"cname" : "apple watch 38mm MLLD2CH/A不锈钢红运动表带",
  	"productTypeName" : "Mac mini",
  	"img":"source://view/do_ExpandableListView/1.png"
  }, {
  	"groupid" : "001004",
  	"childid" : 522,
  	"cname" : "apple watch 42mm MJ3T2CH/A灰铝黑运动表带",
  	"productTypeName" : "Mac mini",
  	"img":"source://view/do_ExpandableListView/1.png"
  }, {
  	"groupid" : "001004",
  	"childid" : 32,
  	"cname" : "Mac mini MD388CH/A",
  	"productTypeName" : "Mac mini",
  	"img":"source://view/do_ExpandableListView/1.png"
  }, {
  	"groupid" : "001004",
  	"childid" : 31,
  	"cname" : "Mac mini MD387CH/A",
  	"productTypeName" : "Mac mini",
  	"img":"source://view/do_ExpandableListView/1.png"
  } ] ]);
  //绑定item的数据,绑定数据后刷新item才可以看到效果
  do_ExpandableListView.bindItems(group_listdata,child_listdata);

  ```

[回到顶部](#top)

>##### <span id=refreshItems><font color ='#0092db'>**refreshItems**</font></span>: 刷新item数据

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明:
- 示例:

  ```javascript

  //刷新item数据
  do_ExpandableListView.refreshItems();

  ```
  绑定并刷新数据，效果图如下：
  <img src="../../images/expandablelistView_binditems.png" height="380" width="330" >

[回到顶部](#top)

>##### <span id=refreshSpecifiedItems><font color ='#0092db'>**refreshSpecifiedItems**</font></span>: 刷新指定组数据

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **groupIndexes** |<font color ='#808000'>**object**</font> | 否 | |刷新指定组数据，参数不填或传递[ ]刷新所有组数据；
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 参数格式示例如下：

  ```

  //刷新第0,...,k,...i组数据;该数组是需要刷新数据的索引数组
  //所有手动更改数据源的值如:listdata.updateOne(x,data)中的索引x值都应该包含在[0,...,k,...i]中
  [
      0,
      ...
      k,
      ...
      i
  ]


  ```

- 示例:

  ```javascript

  do_ExpandableListView.refreshSpecifiedItems([0,1]);   //刷新第一组第二组数据

  ```

[回到顶部](#top)

>##### <span id=expandGroup><font color ='#0092db'>**expandGroup**</font></span>: 展开组

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **indexs** |<font color ='#808000'>**object**</font> | 是 | |同时展开一组或多组，indexs表示视图的第几组，从0开始计数
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明:
- 示例:

  ```javascript

  //展开第一组和第二组数据
	do_ExpandableListView.expandGroup([0,1]);

  ```

[回到顶部](#top)

>##### <span id=collapseGroup><font color ='#0092db'>**collapseGroup**</font></span>: 收缩组

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **indexs** |<font color ='#808000'>**object**</font> | 是 | |同时收缩一组或多组，indexs表示视图的第几组，从0开始计数
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明:
- 示例:

  ```javascript

  //收缩第一组和第二组数据
  do_ExpandableListView.collapseGroup([0,1]);

  ```

[回到顶部](#top)

>##### <span id=scrollToPosition><font color ='#0092db'>**scrollToPosition**</font></span>: 平滑地滚动到特定位置

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **groupIndex** |<font color ='#808000'>**number**</font> | 否 | 0|表示第几组，从0开始计数，缺省值是0
  **childIndex** |<font color ='#808000'>**number**</font> | 否 | 0|表示某一组的第几行，从0开始计数，缺省值是0
  **isSmooth** |<font color ='#808000'>**boolean**</font> | 否 | false|缺省是false表示直接跳转到某一行，没有任何平滑过渡的效果。为true表示平滑到那一行；其中为false的时候是不会触发scroll事件的，为true会触发；windows平台不支持该效果
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明:
- 示例:

  ```javascript

  //平滑的滚动到第二组第三行数据
  do_ExpandableListView.scrollToPosition({groupIndex:1,childIndex:2,isSmooth:true});

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=groupTouch><font color ='#e96900'>**groupTouch**</font></span>: 点击group中的cell触发

- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 当前cell的索引值
- 说明: 点击group中的cell触发
- 示例:

  ```javascript

  var group_imgsource = ["source://view/do_ExpandableListView/zk.jpg","source://view/do_ExpandableListView/ss.jpg"];
  //点击group时触发，点击时自动展开或收缩该组数据
  do_ExpandableListView.on("groupTouch",function(d){
    	var g_item = group_listdata.getOne(d);
    	g_item.img_type == group_imgsource[0] ? g_item.img_type = group_imgsource[1] : g_item.img_type = group_imgsource[0];
    	group_listdata.updateOne(d, g_item); //更新点击的group数据
    	do_ExpandableListView.refreshSpecifiedItems([d]);//刷新指定组数据（不调用该方法刷新数据可能会导致页面数据错乱）
  });

  ```

[回到顶部](#top)

>###### <span id=childTouch><font color ='#e96900'>**childTouch**</font></span>: 点击child中的cell触发

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 当前group的索引值和cell的索引值,如：{'groupIndex':1,'childIndex':5}
- 说明: 点击child中的cell触发
- 示例:

  ```javascript

  var child_imgsource = ["source://view/do_ExpandableListView/1.png","source://view/do_ExpandableListView/2.png"];
  //点击child时触发
  do_ExpandableListView.on("childTouch",function(data){
    	var c_item = child_listdata.getOne(data.groupIndex);
    	c_item.map(function(v,k){
      		if (k == data.childIndex){
      			v.img == child_imgsource[0] ? v.img = child_imgsource[1] : v.img = child_imgsource[0];
      		}
    	});
    	child_listdata.updateOne(data.groupIndex, c_item);//更新点击的child数据
    	var device = sm("do_Device").getInfo();
    	if (device.OS == "android"){//安卓更新child数据时需要调用refreshItems方法刷新数据,否则数据刷新不了
    		  do_ExpandableListView.refreshItems();   
    	}
    	do_ExpandableListView.expandGroup([data.groupIndex]); //展开一组数据，点击child时需要展开该child所在的group
  })

  ```

[回到顶部](#top)

>###### <span id=groupExpand><font color ='#e96900'>**groupExpand**</font></span>: group展开触发

- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 当前group中cell的索引值
- 说明: group展开触发
- 示例:

  ```javascript

  //组展开时触发
  do_ExpandableListView.on("groupExpand",function(_index){
    	deviceone.print(_index,"当前展开的组的索引");
  })

  ```

[回到顶部](#top)

>###### <span id=groupCollapse><font color ='#e96900'>**groupCollapse**</font></span>: group收缩触发

- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 当前group中cell的索引值
- 说明: group收缩触发
- 示例:

  ```javascript

  //组收缩时触发
  do_ExpandableListView.on("groupCollapse",function(_index){
  	  deviceone.print(_index,"当前收缩的组的索引");
  })

  ```

[回到顶部](#top)

>###### <span id=scroll><font color ='#e96900'>**scroll**</font></span>: 滑动事件

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: Android平台返回{firstVisiblePosition,lastVisiblePosition}，其中firstVisiblePosition表示在组件高度范围内第一个可见cell的位置，lastVisiblePosition表示在组件高度范围内最后一个可见cell的位置；iOS和windows平台返回offset表示滚动的位移
- 说明: 滑动事件
- 示例:

  ```javascript

  //滑动时触发
  do_ExpandableListView.on("scroll",function(_data){

  	deviceone.print(JSON.stringify(_data),"scroll事件返回值");  

  })

  //Android平台返回{firstVisiblePosition,lastVisiblePosition}，其中firstVisiblePosition表示在组件高度范围内第一个可见cell的位置，lastVisiblePosition表示在组件高度范围内最后一个可见cell的位置。示例如下：
	{
	    "firstVisiblePosition":0,
	    "lastVisiblePosition":11
	}

  // iOS和windows平台返回offset表示滚动的位移，示例如下：
	{
	    "offset":146.8125
	}

  ```

#### <font color ='#40A977'>**5.**</font> 常见问题

- 1. 点击并展开group的时候，scroll事件IOS不触发，android触发。                                
     原因：原生无法修复
- 2. IOS平台当group的背景为透明时，child展开关闭时会有一闪的问题，该问题必须用户给group一个白色背景。                     
    原因：原生无法解决

#### <font color ='#40A977'>**6.**</font> 基本配置


[回到顶部](#top)
