---
title: do_CoverFlowView 组件
---

### do_CoverFlowView 组件

 支持平台: iOS7.0,Android14
 这个UI组件包含多个子视图，实现多个子视图之间左右平缓滑动效果；该组件支持设置多个模板视图，要求多个模板大小相同

#### <font color ='#40A977'>**1.**</font> 属性

>###### <font color ='#42b983'>**looping**</font>: 左右无限滑动

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : false
- 说明 : 左右无限循环滑动视图，设置值为true表示支持无限循环滑动，默认为false，windows平台不支持

>###### <font color ='#42b983'>**spacing**</font>: 间距

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 30
- 说明 : 页间距

>###### <font color ='#42b983'>**index**</font>: 当前滑动View索引

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 0
- 说明 : 设置滑动视图索引值，默认为0

>###### <font color ='#42b983'>**templates**</font>: 显示视图对应UI模板文件

- 数据类型 : <font color ='#808000'>**object**</font>
- 默认值 : 
- 说明 : 一个CoverFlowView可以有多个cell模板，这个属性是一个json array，每一个元素都是一个source ui文件，这些ui文件没有自己的逻辑代码，和CoverFlowView所在的page共用一个脚本环境。
这个属性的格式类似如下：
["source://view/cell1.ui","source://view/cell2.ui","source://view/cell3.ui]；多模版的大小需要一致

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**bindItems**</font>: 绑定视图模板数据

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **data** |<font color ='#808000'>**object**</font> | 否 | |
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 绑定数据类型为do_ListData实例
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**refreshItems**</font>: 刷新数据

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 支持动态刷新当前视图显示数据
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <font color ='#e96900'>**indexChanged**</font>: 滑动显示当前视图后触发该事件

- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回当前index
- 说明: 滑动显示当前视图后触发该事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**touch**</font>: 点击cell触发

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 当前cell的index值
- 说明: 点击cell触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


