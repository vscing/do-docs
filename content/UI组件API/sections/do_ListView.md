---
title: do_ListView 组件
---

### do_ListView 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_ListView)
 List视图是最常用的UI组件，由很多个Cell组成。它可以通过bind一个ListData来构造视图的数据Model，修改数据来更新视图。android平台不支持在cell中放TextField、TextBox组件。

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#42b983'>属性</font>  |[bounces](#bounces)| 反弹效果
<font color ='#42b983'>属性</font>  |[canScrollToTop](#canScrollToTop)| 是否滚动到屏幕顶部
<font color ='#42b983'>属性</font>  |[isHeaderVisible](#isHeaderVisible)| 是否显示headerview
<font color ='#42b983'>属性</font>  |[isFooterVisible](#isFooterVisible)| 是否显示footerview
<font color ='#42b983'>属性</font>  |[selectedColor](#selectedColor)| Cell选中的背景颜色
<font color ='#42b983'>属性</font>  |[templates](#templates)| Cell对应的模板UI文件组
<font color ='#42b983'>属性</font>  |[headerView](#headerView)| 表头视图
<font color ='#42b983'>属性</font>  |[footerView](#footerView)| 底部视图
<font color ='#42b983'>属性</font>  |[isShowbar](#isShowbar)| 是否支持显示滚动条效果
<font color ='#0092db'>同步方法</font>  |[rebound](#rebound)| 复位
<font color ='#0092db'>同步方法</font>  |[bindItems](#bindItems)| 绑定item的数据
<font color ='#0092db'>同步方法</font>  |[refreshItems](#refreshItems)| 刷新item数据
<font color ='#0092db'>同步方法</font>  |[scrollToPosition](#scrollToPosition)| 平滑地滚动到特定位置
<font color ='#0092db'>同步方法</font>  |[showHeader](#showHeader)| 显示HeaderView
<font color ='#e96900'>事件</font>  |[touch](#touch)| 点击cell触发
<font color ='#e96900'>事件</font>  |[longTouch](#longTouch)| 长按cell触发
<font color ='#e96900'>事件</font>  |[touch1](#touch1)| 点击cell触发
<font color ='#e96900'>事件</font>  |[longTouch1](#longTouch1)| 长按cell触发
<font color ='#e96900'>事件</font>  |[pull](#pull)| 下拉headerview事件
<font color ='#e96900'>事件</font>  |[push](#push)| 上拉footerview事件
<font color ='#e96900'>事件</font>  |[scroll](#scroll)| 滑动事件
<font color ='#e96900'>事件</font>  |[sizeChanged](#sizeChanged)| 组件尺寸改变事件

#### <font color ='#40A977'>**1.**</font> 属性

>###### <span id=bounces><font color ='#42b983'>**bounces**</font></span>: 反弹效果

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : true
- 说明 : 只支持iOS平台，为false时没有上拉下拉的反弹效果

  ```javascript

    var do_ListView = ui("do_ListView_1");  //实例化
    do_ListView.bounces = true;

  ```

>###### <span id=canScrollToTop><font color ='#42b983'>**canScrollToTop**</font></span>: 是否滚动到屏幕顶部

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : true
- 编辑类型 : 只允许设计区内修改
- 说明 : 属性设置成true时可以通过点击手机状态栏返回内容的顶部；仅支持iOS平台

>###### <span id=isHeaderVisible><font color ='#42b983'>**isHeaderVisible**</font></span>: 是否显示headerview

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : false
- 编辑类型 : 只允许设计区内修改
- 说明 : 缺省false不显示

>###### <span id=isFooterVisible><font color ='#42b983'>**isFooterVisible**</font></span>: 是否显示footerview

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : false
- 编辑类型 : 只允许设计区内修改
- 说明 : 缺省false不显示

>###### <span id=selectedColor><font color ='#42b983'>**selectedColor**</font></span>: Cell选中的背景颜色

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : ffffff00
- 编辑类型 : 只允许设计区内修改
- 说明 :

>###### <span id=templates><font color ='#42b983'>**templates**</font></span>: Cell对应的模板UI文件组

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 :
- 说明 : 一个ListView可以有多个cell模板，每一个元素都是一个source ui文件。这个属性的格式类似如下： source://view/cell1.ui,source://view/cell2.ui,source://view/cell3.ui

  ```javascript

    do_ListView.templates="source://view/do_ListView/list_cell0.ui,source://view/do_ListView/list_cell1.ui,source://view/do_ListView/list_cell2.ui";

  ```

>###### <span id=headerView><font color ='#42b983'>**headerView**</font></span>: 表头视图

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 :
- 编辑类型 : 只允许设计区内修改
- 说明 : 设置要显示的表头视图地址，不填写isHeaderVisible为true时有缺省样式

>###### <span id=footerView><font color ='#42b983'>**footerView**</font></span>: 底部视图

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 :
- 编辑类型 : 只允许设计区内修改
- 说明 : 设置要显示的表头视图地址，不填写isFooterVisible为true时有缺省样式

>###### <span id=isShowbar><font color ='#42b983'>**isShowbar**</font></span>: 是否支持显示滚动条效果

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : true
- 编辑类型 : 只允许设计区内修改
- 说明 : 为true的时候，当listview内容超出listview的边界，会出现滚动条标识。

  左图为不显示滚动条的效果图，右图是有滚动条的效果图。

  <div align="center">

  <img src="../../images/listview_unshowbar.png" height="330" width="310" >

  <img src="../../images/listview_showbar.png" height="330" width="310" >

  </div>

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=rebound><font color ='#0092db'>**rebound**</font></span>: 复位

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: headerview或footerview复位，通常下拉或上拉刷新处理数据后需要调用这个方法恢复listview状态
- 示例: 具体使用方法参考pull和push使用时的代码

  ```javascript

    do_ListView.rebound();

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

    var do_ListData = mm("do_ListData"); //实例化listdata
    var datas = [
    		{
    			template : 0,
    			icon : "source://view/do_ListView/image/default.png",
    			Content : "十月，最美是枫叶。枫叶红了，漫山红遍、层林尽染;晚风习习，闭上眼，满脑子都是河湖碧透泉瀑流清般的诗情画意。 月已落下，乌鸦仍然在啼叫着，幕色朦胧漫天霜色，夜泊枫桥的张继对着江边的枫树和船上的渔火独自感叹，辗转反侧。满希望。",
    			CreateByName : "张小二",
    			CreateTime : "2017-10-7 10:35"
    		}, {
    			template : 0,
    			icon : "source://view/do_ListView/image/default.png",
    			Content : "万花都落尽 一树红叶烧  谁怜惟薄力 添与江山饶。",
    			CreateByName : "张小四",
    			CreateTime : "2017-10-9 10:35"
    		}, {
    			template : 0,
    			icon : "source://view/do_ListView/image/default.png",
    			Content : "远上寒山石径斜，白云生处有人家。停车坐爱枫林晚，霜叶红于二月花。",
    			CreateByName : "张小五",
    			CreateTime : "2017-10-10 10:35"
    		}, {
    			template : 1,
    			type : "期刊分类",
    			type_arrs : [ {
    				name : "(遴选)核心"
    			}, {
    				name : "科技核心"
    			}, {
    				name : "中文核心"
    			} ]
    		}, {
    			template : 1,
    			type : "级别",
    			type_arrs : [ {
    				name : "国家级"
    			}, {
    				name : "省级"
    			} ]
    		}, {
    			template : 1,
    			type : "第几期",
    			type_arrs : [ {
    				name : "十月第1期"
    			}, {
    				name : "十月第2期"
    			} ]
    		}, {
    			template : 2
    		} ];

    do_ListData.addData(datas);
    do_ListView.bindItems(do_ListData); //绑定listData实例

  ```
  绑定item数据之后的效果图如下

  <div align="center">

  <img src="../../images/listview_item.png" height="330" width="310" >

  </div>

[回到顶部](#top)

>##### <span id=refreshItems><font color ='#0092db'>**refreshItems**</font></span>: 刷新item数据

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明:
- 示例:

  ```javascript

    do_ListData.updateOne(0, {
  		template : 0,
  		icon : "source://view/do_ListView/image/default.png",
  		Content : "更新内容",
  		CreateByName : "张小二",
  		CreateTime : "2017-10-7 10:35"
  	})
  	do_ListView.refreshItems(); //更新数据之后需要刷新item数据才能起作用

  ```
  更新并刷新第一条数据之后的效果图如下：

  <div align="center">

  <img src="../../images/listview_item1.png" height="330" width="310" >

  </div>

[回到顶部](#top)

>##### <span id=scrollToPosition><font color ='#0092db'>**scrollToPosition**</font></span>: 平滑地滚动到特定位置

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **position** |<font color ='#808000'>**number**</font> | 否 | 0|表示listview的第几行，从0开始计数，缺省值是 0
  **isSmooth** |<font color ='#808000'>**Boolean**</font> | 否 | false|缺省是false表示直接跳转到某一行，没有任何平滑过渡的效果。为true表示平滑到那一行；其中为false的时候是不会触发scroll事件的，为true会触发；windows不支持该效果
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明:
- 示例:

  ```javascript

    //平滑的滚动到第二条数据的位置
    do_ListView.scrollToPosition({position:1,isSmooth:true})

  ```

[回到顶部](#top)

>##### <span id=showHeader><font color ='#0092db'>**showHeader**</font></span>: 显示HeaderView

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 当设置isHeaderVisible=true，自动显示HeaderView，并触发pull事件，windows平台不支持
- 示例:

  ```javascript

    do_ListView.showHeader();

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=touch><font color ='#e96900'>**touch**</font></span>: 点击cell触发

- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 当前点击的cell的index值
- 说明: 点击cell触发
- 示例:

  ```javascript

    do_ListView.on("touch",function(_data){
    	deviceone.print(JSON.stringify(_data),"touch事件")
    })

  ```

[回到顶部](#top)

>###### <span id=longTouch><font color ='#e96900'>**longTouch**</font></span>: 长按cell触发

- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 当前点击的cell的index值
- 说明: 长按cell触发
- 示例:

  ```javascript

    do_ListView.on("longTouch",function(_data){
    	deviceone.print(JSON.stringify(_data),"longTouch事件")
    })

  ```

[回到顶部](#top)

>###### <span id=touch1><font color ='#e96900'>**touch1**</font></span>: 点击cell触发

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 当前cell的position值和在当前cell的绝对位置y
- 说明: 点击cell触发
- 示例:

  ```javascript

    do_ListView.on("touch1",function(_data){
    	deviceone.print(JSON.stringify(_data),"touch1事件")
    })

    //touch1事件的返回值示例
    {
        "position":2,
        "y":298.36628849270664
    }


  ```

[回到顶部](#top)

>###### <span id=longTouch1><font color ='#e96900'>**longTouch1**</font></span>: 长按cell触发

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 当前cell的position值和在当前cell的绝对位置y
- 说明: 长按cell触发
- 示例:

  ```javascript

    do_ListView.on("longTouch1",function(_data){
      deviceone.print(JSON.stringify(_data),"longTouch1事件")
    })

    //longTouch1事件的返回值示例
    {
        "position":1,
        "y":149.18314424635332
    }

  ```

[回到顶部](#top)

>###### <span id=pull><font color ='#e96900'>**pull**</font></span>: 下拉headerview事件

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回值示例{"state":0,"offset":"99.45542949756889"}，其中state表示headerview的状态，offset为headerview下拉的位移量。其中state=0：表示开始下拉headerview；在headerview下拉到headerview复位整个过程中，pull事件会触发很多次；state=1：下拉headerview超过headerview的高度时触发一次这个事件，前端开发者可以在该事件触发时更新headerview的ui；state=2：下拉超过headerview的高度触发并松手会触发一次该事件，前端开发者可以在该事件触发时更新headerview的ui，然后开始加载最新的数据，数据加载完后需要调用rebound方法复位headerview。
- 说明: 下拉headerview事件
- 示例:

  ```javascript

    do_ListView.on("pull", function(data) {
    	deviceone.print(JSON.stringify(data),"pull事件")
    	if (data.state == 2) {// 下拉到一定位置松手开始刷新数据并复位
    		do_ListView.rebound();
    	}
    })

    //pull事件返回值示例
    {
        "state":0,
        "offset":"12.972447325769854"
    }

  ```

[回到顶部](#top)

>###### <span id=push><font color ='#e96900'>**push**</font></span>: 上拉footerview事件

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回值示例{"state":0,"offset":"99.45542949756889"}，其中state表示footerview的状态，offset为footerview上拉的位移量。state=0,表示开始上拉，从footerview开始上拉到footerview复位过程中，push事件会多次触发；state=1，如果下拉超过footerview的高度时这个事件会触发一次，前端开发者可以在触发这个事件时更新footerview的ui；state=2，如果超过footerview的高度并松手会触发一次该事件，前端开发者可以在这个事件触发时更新footerview的ui，并开始加载数据，加载完后前端开发者需插入新的数据，并调用rebound复位footerview
- 说明: 上拉footerview事件
- 示例:

  ```javascript

    do_ListView.on("push", function(data) {
    	deviceone.print(JSON.stringify(data),"push事件")
    	if (data.state == 2) {
    		do_ListView.rebound();
    	}
    })

    //push事件返回值示例
    {
        "state":0,
        "offset":"10.089681253376554"
    }

  ```

[回到顶部](#top)

>###### <span id=scroll><font color ='#e96900'>**scroll**</font></span>: 滑动事件

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: iOS和Android平台返回{firstVisiblePosition,lastVisiblePosition}，其中firstVisiblePosition表示在组件高度范围内第一个可见cell的位置，lastVisiblePosition表示在组件高度范围内最后一个可见cell的位置；windows平台返回offset表示滚动的位移
- 说明: 滑动事件
- 示例:

  ```javascript

    do_ListView.on("scroll",function(_data){
    	deviceone.print(JSON.stringify(_data),"scroll事件")
    })

    //scroll事件的返回值示例
    {
        "firstVisiblePosition":0,
        "lastVisiblePosition":4
    }

  ```

[回到顶部](#top)

>###### <span id=sizeChanged><font color ='#e96900'>**sizeChanged**</font></span>: 组件尺寸改变事件

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回{width,height,oldWidth,oldHeight}，其中width表示当前状态的宽，oldWidth表示尺寸改变之前的高；height表示当前状态的高，oldHeight表示状态改变之前的高
- 说明: 组件尺寸改变事件
- 示例:

  ```javascript

    do_ListView.on("sizeChanged",function(_data){
    	deviceone.print(JSON.stringify(_data),"sizeChanged事件")
    })

    //sizeChanged事件的返回值示例
    {
        "w":750,
        "h":807.8951917882226,
        "oldw":750,
        "oldh":803.5710426796327
    }

  ```

#### <font color ='#40A977'>**5.**</font> 常见问题

- 1. android的模板是复用的，当用同一模板，其中某条数据内容有缺失也必须给空的，不能留空，否则会随机根据上下文补充内容  
     原因：原生无法修复
- 2. 页面滑动卡死，无法复位，日志报错,参考如下[报错图片](http://doc.deviceone.net//web/img/20161104/b7305aafeedc4540bf4d5ba6dd99e639.jpg)     
     原因：通常是因为listview的数据在删除之后，需要调用refreshItems方法刷新一下。
- 3. Android下do_ListView里放do_TextField获取不到焦点                     
     原因：do_ListView的模板里可以放textfield和textbox，但是不能触发焦点，所以不建议用户这样使用。可以使用scrollview来加载表单。用listview加载表单不是一个合适的方式，因为有一个隐患就是listview是模板复用，需要不断的更新对应的listdata。详见[文档](http://doc.deviceone.net/web/doc/detail_course/templates.htm)
- 4. listview模板复用问题重复解析                                             
    原因：先解释下绑定数据的数据流向过程。1）setMapping(data) 是在初始化数据；2）用户操作了，data里的某些属性更改；3）更改数据完了，要告诉setMapping data变了，用fire触发一下；4）页面刷新，双向绑定成功。数据重复了说明是在第二步出现了问题。参考[文档](http://bbs.deviceone.net/forum.php?mod=viewthread&tid=1125)


#### <font color ='#40A977'>**6.**</font> 基本配置

  [回到顶部](#top)
