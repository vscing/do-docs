---
title: do_ScrollView 组件
---

### do_ScrollView 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_ScrollView)
 滚动视图，支持上下和左右滚动两种类型，只有在滚动视图内容宽、高度超过自身定义的宽、高度时才可以滚动，滚动视图只能包含一个子组件，通常都是一个ALayout或LinearLayout

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#42b983'>属性</font>  |[canScrollToTop](#canScrollToTop)| 是否滚动到屏幕顶部
<font color ='#42b983'>属性</font>  |[isHeaderVisible](#isHeaderVisible)| 是否显示headerview
<font color ='#42b983'>属性</font>  |[isFooterVisible](#isFooterVisible)| 是否显示footerview
<font color ='#42b983'>属性</font>  |[direction](#direction)| 滚动方向
<font color ='#42b983'>属性</font>  |[isShowbar](#isShowbar)| 显示滚动条
<font color ='#42b983'>属性</font>  |[headerView](#headerView)| 顶部视图
<font color ='#42b983'>属性</font>  |[footerView](#footerView)| 底部视图
<font color ='#0092db'>同步方法</font>  |[toBegin](#toBegin)| 滚到到最前
<font color ='#0092db'>同步方法</font>  |[toEnd](#toEnd)| 滚到到最后
<font color ='#0092db'>同步方法</font>  |[rebound](#rebound)| 顶部视图复位
<font color ='#0092db'>同步方法</font>  |[scrollTo](#scrollTo)| 滚动到指定位置
<font color ='#0092db'>异步方法</font>  |[screenShot](#screenShot)| 截屏
<font color ='#e96900'>事件</font>  |[pull](#pull)| 下拉滑动显示顶部视图时触发事件
<font color ='#e96900'>事件</font>  |[push](#push)| 上拉footerview事件
<font color ='#e96900'>事件</font>  |[scroll](#scroll)| 控件滚动触发

#### <font color ='#40A977'>**1.**</font> 属性

>###### <span id=canScrollToTop><font color ='#42b983'>**canScrollToTop**</font></span>: 是否滚动到屏幕顶部

- 数据类型 : <font color ='#808000'>**Boolean**</font>
- 默认值 : true
- 说明 : 属性设置成true时可以通过点击手机状态栏返回内容的顶部；仅支持iOS平台

>###### <span id=isHeaderVisible><font color ='#42b983'>**isHeaderVisible**</font></span>: 是否显示headerview

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : false
- 说明 : 设置是否显示顶部视图，只有滚动方向为纵向才有效，横向不支持；缺省false不显示

>###### <span id=isFooterVisible><font color ='#42b983'>**isFooterVisible**</font></span>: 是否显示footerview

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : false
- 说明 : 缺省false不显示

>###### <span id=direction><font color ='#42b983'>**direction**</font></span>: 滚动方向

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : vertical
- 说明 : 设置视图滚动方向值，支持两种类型：horizontal（横向）、vertical（纵向）

>###### <span id=isShowbar><font color ='#42b983'>**isShowbar**</font></span>: 显示滚动条

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : false
- 说明 : 为true的时候，当scrollview内内容超出scrollview的边界，会出现滚动条标识

>###### <span id=headerView><font color ='#42b983'>**headerView**</font></span>: 顶部视图

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 : 可自定义下拉滑动显示顶部视图效果，通常用于动态加载数据过程，下拉顶部自定义视图是一个UI模板文件，例如source://view/head.ui，只有滚动方向为纵向才有效，横向不支持

>###### <span id=footerView><font color ='#42b983'>**footerView**</font></span>: 底部视图

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 : 设置要显示的表头视图地址，不填但isFooterVisible为true时有缺省样式

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=toBegin><font color ='#0092db'>**toBegin**</font></span>: 滚到到最前

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 当前滚动视图是横向则滚动到最左边，如果是纵向则滚到最顶部
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=toEnd><font color ='#0092db'>**toEnd**</font></span>: 滚到到最后

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 当前滚动视图是横向则滚动到最右边，如果是纵向则滚到最底部
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=rebound><font color ='#0092db'>**rebound**</font></span>: 顶部视图复位

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 如顶部视图当前属于可见状态，则将其变为不可见，恢复到没有下拉滑动之前视图效果
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=scrollTo><font color ='#0092db'>**scrollTo**</font></span>: 滚动到指定位置

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **offset** |<font color ='#808000'>**number**</font> | 否 | 0|
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 滚动方向跟ScrollView的方向一致
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <span id=screenShot><font color ='#0092db'>**screenShot**</font></span>: 截屏

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回截屏图片保存的地址，是一个data://temp/do_ScrollView目录下一个图片文件，文件名是日期+时间
- 说明: 截取当前ScrollView中所有内容
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=pull><font color ='#e96900'>**pull**</font></span>: 下拉滑动显示顶部视图时触发事件

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回{state,offset}，其中state表示headerview的状态，offset为headerview下拉的位移量；其中state=0：表示开始下拉headerview，在headerview下拉到headerview复位整个过程中，pull事件会触发很多次；state=1：表示下拉headerview超过headerview的高度，触发一次这个事件，前端开发者接受到这个事件会更新headerview的ui；state=2：下拉超过一定值，触发state=1事件后，松手会触发一次这个事件，前端开发者接受到这个事件会更新headerview的ui，然后开始加载数据，数据加载完后需要调用rebound方法让header复位
- 说明: 下拉滑动显示顶部视图时触发事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <span id=push><font color ='#e96900'>**push**</font></span>: 上拉footerview事件

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回{state,offset}，其中state表示headerview的状态，offset为footerview上拉的位移量；state=0,表示一直上拉，从0开始到footerview复位，会多次触发这个事件；state=1，如果超过footerview的高度，这个事件只触发一次，前端接受到这个事件会更新footview的ui；state=2，如果超过footview的高度并松手，这个事件只触发一次，前端接受到这个事件会更新footview的ui，并开始加载数据，加载完后前端开发者需插入新的数据，并调用rebound复位footerview
- 说明: 上拉footerview事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <span id=scroll><font color ='#e96900'>**scroll**</font></span>: 控件滚动触发

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 控件滚动的距离，若direction属性为horizontal，返回值为{left:滚动离左边的距离,oldLeft:上一次滚动离左边的距离}；若direction属性为vertical，返回值为{top:滚动离顶部的距离,oldTop:上一次滚动离顶部的距离}
- 说明: 控件滚动触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


