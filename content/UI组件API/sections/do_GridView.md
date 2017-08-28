---
title: do_GridView 组件
---

### do_GridView 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_GridView)
 GridView是一个二维网格滚动视图，可将数据源中的一条数据显示为表格中的一个cell，若设置为多模版，需要模板的大小相同

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
- 说明 : 设置GridView显示内容（必须是一个数组），例如：
[{"template":0,"image":"source://1.jpg"},{"template":2,"title":"content","image":"source://1.jpg"}]；设置该属性，会把值传递到每个子View，相当于触发了子View的相关属性的修改

>###### <span id=canScrollToTop><font color ='#42b983'>**canScrollToTop**</font></span>: 是否滚动到屏幕顶部

- 数据类型 : <font color ='#808000'>**Boolean**</font>
- 默认值 : true
- 说明 : 属性设置成true时可以通过点击手机状态栏返回内容的顶部；仅支持iOS平台

>###### <span id=templates><font color ='#42b983'>**templates**</font></span>: 显示视图对应UI模板文件

- 数据类型 : <font color ='#808000'>**object**</font>
- 默认值 : 
- 说明 : 一个GridView可以有多个cell模板，这个属性是一个json array，每一个元素都是一个source ui文件，这些ui文件没有自己的逻辑代码，和gridview所在的page共用一个脚本环境。
这个属性的格式类似如下：
["source://view/cell1.ui","source://view/cell2.ui","source://view/cell3.ui]；多模版的大小需要一致

>###### <span id=numColumns><font color ='#42b983'>**numColumns**</font></span>: GridView对应的列数

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 1
- 说明 : 设置这个GridView显示多少列，-1 表示自动适应；若要动态修改numColumns，需要将GridView的宽度设置为-1

>###### <span id=hSpacing><font color ='#42b983'>**hSpacing**</font></span>: 两列之间的间距

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 
- 说明 : 两列之间的间距，单位为px

>###### <span id=vSpacing><font color ='#42b983'>**vSpacing**</font></span>: 两行之间的间距

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 
- 说明 : 两行之间的间距，单位为px

>###### <span id=selectedColor><font color ='#42b983'>**selectedColor**</font></span>: cell选中的背景颜色

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 : 

>###### <span id=isShowbar><font color ='#42b983'>**isShowbar**</font></span>: 是否支持显示滚动条效果

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : true
- 说明 : 为true的时候，当数据内容超出gridview的边界，会出现滚动条标识

>###### <span id=isHeaderVisible><font color ='#42b983'>**isHeaderVisible**</font></span>: 是否显示headerview

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : false
- 说明 : 缺省false不显示

>###### <span id=headerView><font color ='#42b983'>**headerView**</font></span>: 表头视图

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 : 设置要显示的表头视图地址，不填但isHeaderVisible为true时有缺省样式

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=rebound><font color ='#0092db'>**rebound**</font></span>: 复位

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: headerview复位，通常下拉刷新后处理数据后需要调用这个方法恢复状态
- 示例:

  ```javascript
  ...

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
  ...

  ```

[回到顶部](#top)

>##### <span id=refreshItems><font color ='#0092db'>**refreshItems**</font></span>: 刷新item数据

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **indexs** |<font color ='#808000'>**object**</font> | 否 | |要刷新的数据的索引，是一个数组，可以为单个或多个索引。如果不填则为刷新全部数据，仅支持iOS平台
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=touch><font color ='#e96900'>**touch**</font></span>: 点击cell触发

- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 当前cell的position值
- 说明: 点击cell触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <span id=longTouch><font color ='#e96900'>**longTouch**</font></span>: 长按cell触发

- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 当前cell的position值
- 说明: 长按cell触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <span id=pull><font color ='#e96900'>**pull**</font></span>: 下拉headerview事件

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回{state,offset}，其中state表示headerview的状态，offset为headerview下拉的位移量；其中state=0：表示开始下拉headerview，在headerview下拉到headerview复位整个过程中，pull事件会触发很多次；state=1：表示下拉headerview超过headerview的高度，触发一次这个事件，前端开发者接受到这个事件会更新headerview的ui；state=2：下拉超过一定值，触发state=1事件后，松手会触发一次这个事件，前端开发者接受到这个事件会更新headerview的ui，然后开始加载数据，数据加载完后需要调用rebound方法让header复位
- 说明: 下拉headerview事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <span id=scroll><font color ='#e96900'>**scroll**</font></span>: 滑动事件

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: iOS和Android平台返回{firstVisiblePosition,lastVisiblePosition}，其中firstVisiblePosition表示在组件高度范围内第一行可见cell的位置，lastVisiblePosition表示在组件高度范围内最后一行可见cell的位置；windows平台返回offset表示滚动的位移
- 说明: 滑动事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <span id=touch1><font color ='#e96900'>**touch1**</font></span>: 点击cell触发

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 当前cell的position值和在当前cell的绝对位置x,y，如{'position':'2','x':'0','y':'30'}
- 说明: 点击cell触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <span id=longTouch1><font color ='#e96900'>**longTouch1**</font></span>: 长按cell触发

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 当前cell的position值和在当前cell的绝对位置x,y，如{'position':'2','x':'0','y':'30'}
- 说明: 长按cell触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


