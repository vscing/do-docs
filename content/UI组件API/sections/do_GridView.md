---
title: do_GridView 组件
---

### do_GridView 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_GridView)
 GridView是一个二维网格滚动视图，可将数据源中的一条数据显示为表格中的一个cell，若设置为多模版，需要模板的大小相同。

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#42b983'>属性</font>  |[items](#items)| GridView显示内容
<font color ='#42b983'>属性</font>  |[canScrollToTop](#canScrollToTop)| 是否滚动到屏幕顶部
<font color ='#42b983'>属性</font>  |[templates](#templates)| 显示视图对应UI模板文件
<font color ='#42b983'>属性</font>  |[numColumns](#numColumns)| GridView对应的列数
<font color ='#42b983'>属性</font>  |[hSpacing](#hSpacing)| 两列之间的间距
<font color ='#42b983'>属性</font>  |[vSpacing](#vSpacing)| 两行之间的间距
<font color ='#42b983'>属性</font>  |[selectedColor](#selectedColor)| cell选中的背景颜色
<font color ='#42b983'>属性</font>  |[isShowbar](#isShowbar)| 是否支持显示滚动条效果
<font color ='#42b983'>属性</font>  |[isHeaderVisible](#isHeaderVisible)| 是否显示headerview
<font color ='#42b983'>属性</font>  |[headerView](#headerView)| 表头视图
<font color ='#0092db'>同步方法</font>  |[rebound](#rebound)| 复位
<font color ='#0092db'>同步方法</font>  |[bindItems](#bindItems)| 绑定item的数据
<font color ='#0092db'>同步方法</font>  |[refreshItems](#refreshItems)| 刷新item数据
<font color ='#e96900'>事件</font>  |[touch](#touch)| 点击cell触发
<font color ='#e96900'>事件</font>  |[longTouch](#longTouch)| 长按cell触发
<font color ='#e96900'>事件</font>  |[pull](#pull)| 下拉headerview事件
<font color ='#e96900'>事件</font>  |[scroll](#scroll)| 滑动事件
<font color ='#e96900'>事件</font>  |[touch1](#touch1)| 点击cell触发
<font color ='#e96900'>事件</font>  |[longTouch1](#longTouch1)| 长按cell触发

#### <font color ='#40A977'>**1.**</font> 属性

>###### <span id=items><font color ='#42b983'>**items**</font></span>: GridView显示内容

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 :
- 说明 : 设置GridView显示内容（必须是一个数组），设置该属性，会把值传递到每个子View，相当于触发了子View的相关属性的修改,格式示例如下：

  ```javascript

    [
        {
            "template":0,
            "image":"source://1.jpg"
        },
        {
            "template":2,
            "title":"content",
            "image":"source://1.jpg"
        }
    ]

  ```
- 示例:

  ```javascript

    var do_GridView = ui("do_GridView_1"); //实例化gridview
    do_GridView.items = [ {
    	template : 0,
    	image : "source://view/do_GridView/image/video.png"
    }, {
    	template : 1,
    	image : "source://view/do_GridView/image/video_det.png",
    	title : "第二条数据"
    },{
    	template : 0,
    	image : "source://view/do_GridView/image/video.png"
    }, {
    	template : 1,
    	image : "source://view/do_GridView/image/video_det.png",
    	title : "第四条数据"
    },{
    	template : 0,
    	image : "source://view/do_GridView/image/video.png"
    }, {
    	template : 1,
    	image : "source://view/do_GridView/image/video_det.png",
    	title : "第六条数据"
    }]

  ```

>###### <span id=canScrollToTop><font color ='#42b983'>**canScrollToTop**</font></span>: 是否滚动到屏幕顶部

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : true
- 编辑类型 : 只允许设计区内修改
- 说明 : 属性设置成true时可以通过点击手机状态栏返回内容的顶部；仅支持iOS平台

>###### <span id=templates><font color ='#42b983'>**templates**</font></span>: 显示视图对应UI模板文件

- 数据类型 : <font color ='#808000'>**object**</font>
- 默认值 :
- 编辑类型 : 只允许设计区内修改
- 说明 : 一个GridView可以有多个cell模板，这个属性是一个json array，每一个元素都是一个source ui文件，这些ui文件没有自己的逻辑代码，和gridview所在的page共用一个脚本环境。gridview的模板cell不能是-1;多模版时,模版不能动态,大小必须大小一致。
这个属性的格式类似如下：
["source://view/cell1.ui","source://view/cell2.ui","source://view/cell3.ui]；多模版的大小需要一致

>###### <span id=numColumns><font color ='#42b983'>**numColumns**</font></span>: GridView对应的列数

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 1
- 说明 : 设置这个GridView显示多少列，-1 表示自动适应；若要动态修改numColumns，需要将GridView的宽度设置为-1
- 示例:

  ```javascript

    do_GridView.numColumns = 3;

  ```
  对items属性赋值并且设置numColumns为3后的效果图如下：

  <div align="center">

  <img src="../../images/gridview_items.png" height="330" width="310" >

  </div>


>###### <span id=hSpacing><font color ='#42b983'>**hSpacing**</font></span>: 两列之间的间距

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 :
- 编辑类型 : 只允许设计区内修改
- 说明 : 两列之间的间距，单位为px

>###### <span id=vSpacing><font color ='#42b983'>**vSpacing**</font></span>: 两行之间的间距

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 :
- 编辑类型 : 只允许设计区内修改
- 说明 : 两行之间的间距，单位为px

  设置vSpacing为50px的效果图如下：

  <div align="center">

  <img src="../../images/gridview_vspacing.png" height="330" width="310" >

  </div>

>###### <span id=selectedColor><font color ='#42b983'>**selectedColor**</font></span>: cell选中的背景颜色

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : FFFFFF00
- 编辑类型 : 只允许设计区内修改
- 说明 :

>###### <span id=isShowbar><font color ='#42b983'>**isShowbar**</font></span>: 是否支持显示滚动条效果

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : true
- 编辑类型 : 只允许设计区内修改
- 说明 : 为true的时候，当数据内容超出gridview的边界，会出现滚动条标识

>###### <span id=isHeaderVisible><font color ='#42b983'>**isHeaderVisible**</font></span>: 是否显示headerview

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : false
- 编辑类型 : 只允许设计区内修改
- 说明 : 缺省false不显示

>###### <span id=headerView><font color ='#42b983'>**headerView**</font></span>: 表头视图

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 :
- 编辑类型 : 只允许设计区内修改
- 说明 : 设置要显示的表头视图地址，不填但isHeaderVisible为true时有缺省样式

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=rebound><font color ='#0092db'>**rebound**</font></span>: 复位

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: headerview复位，通常下拉刷新处理数据后需要调用这个方法恢复状态
- 示例: 具体使用方法参考pull和push事件使用时的代码

  ```javascript

    do_GridView.rebound(); //gridview复位

  ```

[回到顶部](#top)

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

    var _datas = [ {
    	template : 0,
    	image : "source://view/do_GridView/image/video.png"
    }, {
    	template : 1,
    	image : "source://view/do_GridView/image/video_det.png",
    	title : "第二条数据"
    },{
    	template : 0,
    	image : "source://view/do_GridView/image/video.png"
    }, {
    	template : 1,
    	image : "source://view/do_GridView/image/video_det.png",
    	title : "第四条数据"
    },{
    	template : 0,
    	image : "source://view/do_GridView/image/video.png"
    }, {
    	template : 1,
    	image : "source://view/do_GridView/image/video_det.png",
    	title : "第六条数据"
    }]
    do_ListData.addData(_datas);
    do_GridView.bindItems(do_ListData); //绑定do_ListData实例

  ```
  绑定item的数据的效果图如下：

  <div align="center">

  <img src="../../images/gridview_binditem.png" height="330" width="310" >

  </div>

[回到顶部](#top)

>##### <span id=refreshItems><font color ='#0092db'>**refreshItems**</font></span>: 刷新item数据

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **indexs** |<font color ='#808000'>**object**</font> | 否 | |要刷新的数据的索引，是一个数组，可以为单个或多个索引(仅支持iOS平台)。如果不填则为刷新全部数据(安卓和IOS平台都支持)
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明:
- 示例:

  ```javascript

    do_ListData.updateOne(1, {
      template : 1,
      image : "source://view/do_GridView/image/video_det.png",
      title : "更新数据"
    })
    do_GridView.refreshItems([1]); //也可使用do_GridView.refreshItems()刷新所有数据

  ```
  更新并刷新第二条数据之后的效果图如下：

  <div align="center">

  <img src="../../images/listview_refresh.png" height="330" width="310" >

  </div>

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=touch><font color ='#e96900'>**touch**</font></span>: 点击cell触发

- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 当前cell的position值
- 说明: 点击cell触发
- 示例:

  ```javascript

    do_GridView.on("touch",function(_data){
    	deviceone.print(JSON.stringify(_data),"touch事件")
    })

  ```

[回到顶部](#top)

>###### <span id=longTouch><font color ='#e96900'>**longTouch**</font></span>: 长按cell触发

- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 当前cell的position值
- 说明: 长按cell触发
- 示例:

  ```javascript

    do_GridView.on("longTouch",function(_data){
    	deviceone.print(JSON.stringify(_data),"longTouch事件")
    })

  ```

[回到顶部](#top)

>###### <span id=pull><font color ='#e96900'>**pull**</font></span>: 下拉headerview事件

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回值示例{"state":0,"offset":"100.45542949756889"}，其中state表示headerview的状态，offset为headerview下拉的位移量。其中state=0：表示开始下拉headerview；在headerview下拉到headerview复位整个过程中，pull事件会触发很多次；state=1：下拉headerview超过headerview的高度时触发一次这个事件，前端开发者可以在该事件触发时更新headerview的ui；state=2：下拉超过headerview的高度触发并松手会触发一次该事件，前端开发者可以在该事件触发时更新headerview的ui，然后开始加载最新的数据，数据加载完后需要调用rebound方法复位headerview。
- 说明: 下拉headerview事件
- 示例:

  ```javascript

    do_GridView.on("pull", function(data) {
      deviceone.print(JSON.stringify(data),"pull事件")
      if (data.state == 2) {// 下拉到一定位置松手复位gridview
        do_GridView.rebound();
      }
    })

    //pull事件的返回值示例
    {
        "state":2,
        "offset":"100.17612101566722"
    }
  ```

[回到顶部](#top)

>###### <span id=scroll><font color ='#e96900'>**scroll**</font></span>: 滑动事件

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: iOS和Android平台返回{firstVisiblePosition,lastVisiblePosition}，其中firstVisiblePosition表示在组件高度范围内第一行可见cell的位置，lastVisiblePosition表示在组件高度范围内最后一行可见cell的位置；windows平台返回offset表示滚动的位移
- 说明: 滑动事件
- 示例:

  ```javascript

    do_GridView.on("scroll",function(_data){
    	deviceone.print(JSON.stringify(_data),"scroll事件")
    })

    //scroll事件的返回值示例
    {
        "firstVisiblePosition":0,
        "lastVisiblePosition":11
    }

  ```

[回到顶部](#top)

>###### <span id=touch1><font color ='#e96900'>**touch1**</font></span>: 点击cell触发

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 当前cell的position值和在当前cell的绝对位置x,y，如{'position':2,'x':'0','y':'30'}
- 说明: 点击cell触发
- 示例:

  ```javascript

    do_GridView.on("touch1",function(_data){
    	deviceone.print(JSON.stringify(_data),"touch1事件")
    })

    //touch1事件的返回值示例
    {
        "position":4,
        "x":246.5277777777778,
        "y":49.72771474878444
    }

  ```

[回到顶部](#top)

>###### <span id=longTouch1><font color ='#e96900'>**longTouch1**</font></span>: 长按cell触发

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 当前cell的position值和在当前cell的绝对位置x,y，如{'position':2,'x':'0','y':'30'}
- 说明: 长按cell触发
- 示例:

  ```javascript

    do_GridView.on("longTouch1",function(_data){
    	deviceone.print(JSON.stringify(_data),"longTouch1事件")
    })

    //longTouch1事件的返回值示例
    {
        "position":9,
        "x":0,
        "y":549.8876283090221
    }
  ```


#### <font color ='#40A977'>**5.**</font> 常见问题

- 1. 多模板时，模板大小必须要一样  
     原因：原生无法修复
- 2. 报错索引不存在,[报错图片](http://doc.deviceone.net/web/img/20161110/274417be5b0f4a519b81cf0962402dab.jpg)     
     原因：出现这个错误通常是因为在设计器中给GridView的templates属性赋值了一个模板路径，但是绑数据时绑的数组里参数key为template的值为1。修改key值为0或者给GridView的templates属性再增加一个模板即可。


#### <font color ='#40A977'>**6.**</font> 基本配置

[回到顶部](#top)
