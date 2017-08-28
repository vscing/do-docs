---
title: do_DraggableGridView 组件
---

### do_DraggableGridView 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_DraggableGridView)
 DraggableGridView是一个可拖拽的二维网格滚动视图，可将数据源中的一条数据显示为表格中的一个cell

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#42b983'>属性</font>  |[templates](#templates)| 显示视图对应UI模板文件
<font color ='#42b983'>属性</font>  |[numColumns](#numColumns)| DraggableGridView对应的列数
<font color ='#42b983'>属性</font>  |[hSpacing](#hSpacing)| 两列之间的间距
<font color ='#42b983'>属性</font>  |[vSpacing](#vSpacing)| 两行之间的间距
<font color ='#0092db'>同步方法</font>  |[bindItems](#bindItems)| 绑定item的数据
<font color ='#0092db'>同步方法</font>  |[refreshItems](#refreshItems)| 刷新item数据
<font color ='#0092db'>同步方法</font>  |[edit](#edit)| 进入可以拖拽的状态
<font color ='#0092db'>同步方法</font>  |[cancel](#cancel)| 退出可以拖拽的状态
<font color ='#e96900'>事件</font>  |[touch](#touch)| 点击cell触发
<font color ='#e96900'>事件</font>  |[longTouch](#longTouch)| 长按cell触发
<font color ='#e96900'>事件</font>  |[dragged](#dragged)| cell拖拽到其它cell位置并松开手指后触发

#### <font color ='#40A977'>**1.**</font> 属性

>###### <span id=templates><font color ='#42b983'>**templates**</font></span>: 显示视图对应UI模板文件

- 数据类型 : <font color ='#808000'>**object**</font>
- 默认值 : 
- 说明 : 一个DraggableGridView可以有多个cell模板，这个属性是一个json array，每一个元素都是一个source ui文件，这些ui文件没有自己的逻辑代码，和DraggableGridView所在的page共用一个脚本环境。
这个属性的格式类似如下：
["source://view/cell1.ui","source://view/cell2.ui","source://view/cell3.ui]；多模版的大小需要一致

>###### <span id=numColumns><font color ='#42b983'>**numColumns**</font></span>: DraggableGridView对应的列数

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 
- 说明 : 设置这个DraggableGridView显示多少列，-1 表示自动适应，iOS不支持（通过cell的宽度和屏幕宽度自动计算列数）

>###### <span id=hSpacing><font color ='#42b983'>**hSpacing**</font></span>: 两列之间的间距

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 
- 说明 : 两列之间的间距，单位为px

>###### <span id=vSpacing><font color ='#42b983'>**vSpacing**</font></span>: 两行之间的间距

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 
- 说明 : 两行之间的间距，单位为px

#### <font color ='#40A977'>**2.**</font> 同步方法

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

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=edit><font color ='#0092db'>**edit**</font></span>: 进入可以拖拽的状态

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=cancel><font color ='#0092db'>**cancel**</font></span>: 退出可以拖拽的状态

- 参数: **无**
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

>###### <span id=dragged><font color ='#e96900'>**dragged**</font></span>: cell拖拽到其它cell位置并松开手指后触发

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {'old':未拖动之前的数据索引,'new':拖动之后的数据索引}
- 说明: cell拖拽到其它cell位置并松开手指后触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


