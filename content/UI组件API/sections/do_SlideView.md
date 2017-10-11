---
title: do_SlideView 组件
---

### do_SlideView 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_SlideView)
 这个UI组件包含多个子视图(UI文件），实现多个子视图之间左右平缓滑动效果，通过设置looping属性支持无限循环滑动，该组件还支持设置多个不同模板视图

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#42b983'>属性</font>  |[allowGesture](#allowGesture)| 是否支持手势滑动
<font color ='#42b983'>属性</font>  |[isAllCache](#isAllCache)| 是否缓存页面状态（已废弃）
<font color ='#42b983'>属性</font>  |[looping](#looping)| 左右无限滑动
<font color ='#42b983'>属性</font>  |[index](#index)| 当前滑动UIView索引
<font color ='#42b983'>属性</font>  |[templates](#templates)| 显示视图对应UI模板文件
<font color ='#0092db'>同步方法</font>  |[bindItems](#bindItems)| 绑定视图模板数据
<font color ='#0092db'>同步方法</font>  |[refreshItems](#refreshItems)| 刷新数据
<font color ='#0092db'>同步方法</font>  |[startLoop](#startLoop)| 开始轮播
<font color ='#0092db'>同步方法</font>  |[stopLoop](#stopLoop)| 停止轮播
<font color ='#0092db'>同步方法</font>  |[getView](#getView)| 获取子View
<font color ='#e96900'>事件</font>  |[indexChanged](#indexChanged)| 滑动显示当前视图后触发该事件
<font color ='#e96900'>事件</font>  |[touch](#touch)| 点击cell触发

#### <font color ='#40A977'>**1.**</font> 属性

>###### <span id=allowGesture><font color ='#42b983'>**allowGesture**</font></span>: 是否支持手势滑动

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : true
- 说明 : 当属性值为true时，组件可通过手势左右滑动来切换页面；为false时，手势无法滑动，只能通过修改index来切换页面；Windows平台不支持

>###### <span id=isAllCache><font color ='#42b983'>**isAllCache**</font></span>: 是否缓存页面状态（已废弃）

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : false
- 说明 : （不论设置成true和false，效果都为设置成true时一样）为true的时候每一条数据缓存一个View，对应的ui文件和js文件只会加载一次，对应的dataRefresh事件只会触发一次，以后不管如何左右滑动都不再加载和触发事件。如果数据不多，建议设置为true
为false时，可以复用View，对应的ui和js可能在来回滑动SlideView的时候会加载多次，而datarefreshed事件每次滑动到这一页就会触发一次。如果需要不想保留每一个页的状态变化，另外需加载较多数据的时候，建议使用false

>###### <span id=looping><font color ='#42b983'>**looping**</font></span>: 左右无限滑动

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : false
- 说明 : 左右无限循环滑动视图，设置值为true表示支持无限循环滑动，默认为false，windows不支持

>###### <span id=index><font color ='#42b983'>**index**</font></span>: 当前滑动UIView索引

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 0
- 说明 : 设置滑动视图索引值，默认为0

>###### <span id=templates><font color ='#42b983'>**templates**</font></span>: 显示视图对应UI模板文件

- 数据类型 : <font color ='#808000'>**object**</font>
- 默认值 :
- 说明 : 可以设置一个或多个UI模板文件，值为String类型，多个模板之间分别用“,”分隔，例如：“source://view/temp/t0.ui,source://view/temp/t1.ui”

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
  var do_SlideView = ui("do_SlideView");
  var listData0 = mm("do_ListData");
  //通过template属性来选定模板
  var data0 = [
  {template:2,"$text":"index 0","$source":"source://image/3.jpg"},
  {template:2,"$text":"index 1","$source":"source://image/4.jpg"},
  {template:0,"$text":"index 2","$source":"source://image/3.jpg"},
  {template:0,"$text":"index 3","$source":"data://3.png"},
  {template:1,"$text":"index 4","$source":"data://3.png"},
  {template:1,"$text":"index 5","$source":"data://4.png"},
  ];
  listData0.addData(data0);
  do_SlideView.bindItems({
  	data : listData0
  });

  ```

[回到顶部](#top)

>##### <span id=refreshItems><font color ='#0092db'>**refreshItems**</font></span>: 刷新数据

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 支持动态刷新当前视图显示数据
- 示例:

  ```javascript
  do_SlideView.refreshItems()

  ```

[回到顶部](#top)

>##### <span id=startLoop><font color ='#0092db'>**startLoop**</font></span>: 开始轮播

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **interval** |<font color ='#808000'>**number**</font> | 否 | 300|轮播间隔时间，单位为毫秒
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 当looping属性为true时，轮播会从右至左按index顺序循环；当looping为false时，顺序轮播完所有index页后再逆序轮播
- 示例:

  ```javascript
  //设置间隔500毫秒轮播
  do_SlideView.startLoop({interval : 500});

  ```

[回到顶部](#top)

>##### <span id=stopLoop><font color ='#0092db'>**stopLoop**</font></span>: 停止轮播

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 停止轮播
- 示例:

  ```javascript
  do_SlideView.stopLoop()

  ```

[回到顶部](#top)

>##### <span id=getView><font color ='#0092db'>**getView**</font></span>: 获取子View

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **index** |<font color ='#808000'>**string**</font> | 是 | |要获取的View的索引
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 子view对应的ui文件RootView地址
- 说明: 获取某个子view对应的ui文件RootView地址
- 示例:

  ```javascript
  //获取第0个子view的地址
  var data = do_SlideView.getView({
					index : 0
				});

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
  do_SlideView.on("indexChanged", function(data, e) {
    deviceone.print(data,"滑动到第几个视图")
  })

  ```

[回到顶部](#top)

>###### <span id=touch><font color ='#e96900'>**touch**</font></span>: 点击cell触发

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 当前cell的index值,如：{'index':1}
- 说明: 点击cell触发
- 示例:

  ```javascript
  do_SlideView.on("touch", function(data, e) {
    deviceone.print(data,"点击第几个视图")
  })

  ```

[回到顶部](#top)
