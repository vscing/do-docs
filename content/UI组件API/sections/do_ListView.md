---
title: do_ListView 组件
---

### do_ListView 组件

 支持平台: iOS7.0,Android4.0
 List视图是最常用的UI组件，由很多个Cell组成。它可以通过bind一个ListData来构造视图的数据Model，修改数据来更新视图。android平台不支持在cell中放TextFiled、TextBox组件

#### <font color ='#40A977'>**1.**</font> 属性

>###### <font color ='#42b983'>**bounces**</font>: 反弹效果

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : true
- 说明 : 只支持iOS平台，为false时没有上拉下拉的反弹效果

>###### <font color ='#42b983'>**canScrollToTop**</font>: 是否滚动到屏幕顶部

- 数据类型 : <font color ='#808000'>**Boolean**</font>
- 默认值 : true
- 说明 : 属性设置成true时可以通过点击手机状态栏返回内容的顶部；仅支持iOS平台

>###### <font color ='#42b983'>**isHeaderVisible**</font>: 是否显示headerview

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : false
- 说明 : 缺省false不显示

>###### <font color ='#42b983'>**isFooterVisible**</font>: 是否显示footerview

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : false
- 说明 : 缺省false不显示

>###### <font color ='#42b983'>**selectedColor**</font>: Cell选中的背景颜色

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : ffffff00
- 说明 : 

>###### <font color ='#42b983'>**templates**</font>: Cell对应的模板UI文件组

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 : 一个ListView可以有多个cell模板，这个属性是一个json array，每一个元素都是一个source ui文件。这个属性的格式类似如下： source://view/cell1.ui,source://view/cell2.ui,source://view/cell3.ui

>###### <font color ='#42b983'>**headerView**</font>: 表头视图

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 : 设置要显示的表头视图地址，不填但isHeaderVisible为true时有缺省样式

>###### <font color ='#42b983'>**footerView**</font>: 底部视图

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 : 设置要显示的表头视图地址，不填但isFooterVisible为true时有缺省样式

>###### <font color ='#42b983'>**isShowbar**</font>: 是否支持显示滚动条效果

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : true
- 说明 : 为true的时候，当listview内容超出listview的边界，会出现滚动条标识。

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**rebound**</font>: 复位

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: headerview或footerview复位，通常下拉或上拉刷新后处理数据后需要调用这个方法恢复状态
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**bindItems**</font>: 绑定item的数据

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

>##### <font color ='#0092db'>**refreshItems**</font>: 刷新item数据

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**scrollToPosition**</font>: 平滑地滚动到特定位置

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
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**showHeader**</font>: 显示HeaderView

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 当设置isHeaderVisible=true，自动显示HeaderView，并触发pull事件，windows平台不支持
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <font color ='#e96900'>**touch**</font>: 点击cell触发

- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 当前cell的position值
- 说明: 点击cell触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**longTouch**</font>: 长按cell触发

- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 当前cell的position值
- 说明: 长按cell触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**touch1**</font>: 点击cell触发

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 当前cell的position值和在当前cell的绝对位置y
- 说明: 点击cell触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**longTouch1**</font>: 长按cell触发

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 当前cell的position值和在当前cell的绝对位置y
- 说明: 长按cell触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**pull**</font>: 下拉headerview事件

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回{state,offset}，其中state表示headerview的状态，offset为headerview下拉的位移量；其中state=0：表示开始下拉headerview，在headerview下拉到headerview复位整个过程中，pull事件会触发很多次；state=1：表示下拉headerview超过headerview的高度，触发一次这个事件，前端开发者接受到这个事件会更新headerview的ui；state=2：下拉超过一定值，触发state=1事件后，松手会触发一次这个事件，前端开发者接受到这个事件会更新headerview的ui，然后开始加载数据，数据加载完后需要调用rebound方法让header复位
- 说明: 下拉headerview事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**push**</font>: 上拉footerview事件

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回{state,offset}，其中state表示headerview的状态，offset为footerview上拉的位移量；state=0,表示一直上拉，当listview的content到listview的底部，从0开始到footerview复位，会多次触发这个事件；state=1，如果超过footerview的高度，这个事件只触发一次，前端接受到这个事件会更新footview的ui；state=2，如果超过footview的高度并松手，这个事件只触发一次，前端接受到这个事件会更新footview的ui，并开始加载数据，加载完后前端开发者需插入新的数据，并调用rebound复位footerview
- 说明: 上拉footerview事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**scroll**</font>: 滑动事件

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: iOS和Android平台返回{firstVisiblePosition,lastVisiblePosition}，其中firstVisiblePosition表示在组件高度范围内第一个可见cell的位置，lastVisiblePosition表示在组件高度范围内最后一个可见cell的位置；windows平台返回offset表示滚动的位移
- 说明: 滑动事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**sizeChanged**</font>: 组件尺寸改变事件

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回{width,height,oldWidth,oldHeight}，其中width表示当前状态的宽，oldWidth表示尺寸改变之前的高；height表示当前状态的高，oldHeight表示状态改变之前的高
- 说明: 组件尺寸改变事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


