---
title: do_ExpandableListView 组件
---

### do_ExpandableListView 组件

* 支持平台: iOS7.0,Android4.0
一个可分组可展开的List视图

#### <font color ='#40A977'>**1.**</font> 属性

>###### <font color ='#42b983'>**allExpanded**</font>: 是否全部展开

- 数据类型 : <font color ='#808000'>**Boolean**</font>
- 默认值 : false
- 说明 : 控制组件初始化时所有group是否全部展开

>###### <font color ='#42b983'>**canScrollToTop**</font>: 是否滚动到屏幕顶部

- 数据类型 : <font color ='#808000'>**Boolean**</font>
- 默认值 : true
- 说明 : 属性设置成true时可以通过点击手机状态栏返回内容的顶部；仅支持iOS平台

>###### <font color ='#42b983'>**groupTemplate**</font>: 组模板UI文件

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 : group对应的模板UI文件,如： source://view/group.ui，支持多模版

>###### <font color ='#42b983'>**childTemplate**</font>: 子项模板UI文件

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 : child对应的模板UI文件,如： source://view/child.ui，支持多模版

>###### <font color ='#42b983'>**selectedColor**</font>: 按下cell显示的背景色

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : ffffff00
- 说明 : 

>###### <font color ='#42b983'>**isShowbar**</font>: 是否支持显示滚动条效果

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : true
- 说明 : 为true的时候，当内容超出视图的边界，会出现滚动条标识。

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**bindItems**</font>: 绑定item的数据

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **groupData** |<font color ='#808000'>**object**</font> |  | 否||
  **childData** |<font color ='#808000'>**object**</font> |  | 否||
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

>##### <font color ='#0092db'>**refreshSpecifiedItems**</font>: 刷新指定组数据

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **groupIndexes** |<font color ='#808000'>**object**</font> |  | 否||刷新指定组数据，参数不填或传递[ ]刷新所有组数据；正确参数格式[0,...,k,...i](刷新第0,...,k,...i组数据;所有手动更改数据源的值如:listdata.updateOne(x,data)中的x值都应该包含在[0,...,k,...i]中). 
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**expandGroup**</font>: 展开组

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **indexs** |<font color ='#808000'>**object**</font> |  | 是||同时展开一组或多组，indexs表示视图的第几组，从0开始计数
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**collapseGroup**</font>: 收缩组

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **indexs** |<font color ='#808000'>**object**</font> |  | 是||同时收缩一组或多组，indexs表示视图的第几组，从0开始计数
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

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **groupIndex** |<font color ='#808000'>**number**</font> | 0 | 否|0|表示第几组，从0开始计数，缺省值是0
  **childIndex** |<font color ='#808000'>**number**</font> | 0 | 否|0|表示某一组的第几行，从0开始计数，缺省值是0
  **isSmooth** |<font color ='#808000'>**Boolean**</font> | false | 否|false|缺省是false表示直接跳转到某一行，没有任何平滑过渡的效果。为true表示平滑到那一行；其中为false的时候是不会触发scroll事件的，为true会触发；windows平台不支持该效果
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

>###### <font color ='#e96900'>**groupTouch**</font>: 点击group中的cell触发

- 返回值类型 : <font color ='#808000'>**Number**</font>
- 返回值描述: 当前cell的索引值
- 说明: 点击group中的cell触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**childTouch**</font>: 点击child中的cell触发

- 返回值类型 : <font color ='#808000'>**Node**</font>
- 返回值描述: 当前group的索引值和cell的索引值,如：{'groupIndex':1,'childIndex':5}
- 说明: 点击child中的cell触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**groupExpand**</font>: group展开触发

- 返回值类型 : <font color ='#808000'>**Number**</font>
- 返回值描述: 当前group中cell的索引值
- 说明: group展开触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**groupCollapse**</font>: group收缩触发

- 返回值类型 : <font color ='#808000'>**Number**</font>
- 返回值描述: 当前group中cell的索引值
- 说明: group收缩触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**scroll**</font>: 滑动事件

- 返回值类型 : <font color ='#808000'>**node**</font>
- 返回值描述: Android平台返回{firstVisiblePosition,lastVisiblePosition}，其中firstVisiblePosition表示在组件高度范围内第一个可见cell的位置，lastVisiblePosition表示在组件高度范围内最后一个可见cell的位置；iOS和windows平台返回offset表示滚动的位移
- 说明: 滑动事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


