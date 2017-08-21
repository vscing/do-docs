---
title: do_LinearLayout 组件
---

### do_LinearLayout 组件

* 支持平台: iOS7.0,Android4.0
横、纵向布局。如果是纵向布局的话，所有内部子控件都从上向下排列，不会有重合，当height=-1时，表示自动高度，整个layout的高度是所有内部子控件的高之和。
如果是横向布局的话，当width=-1时，所有内部组件横向方向顺序排列，宽度是所有子控件宽度之和

#### <font color ='#40A977'>**1.**</font> 属性

>###### <font color ='#42b983'>**direction**</font>: 布局方向

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : vertical
- 说明 : 支持2种方向布局，只允许设计器修改：
horizontal：横向布局
vertical：纵向布局

>###### <font color ='#42b983'>**padding**</font>: 内边距

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 0,0,0,0
- 说明 : 0,0,0,0 分别表示上，右，下，左的内边距，通常只用于height和width为-1的情况

>###### <font color ='#42b983'>**enabled**</font>: 是否可点击

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : true
- 说明 : 缺省为'true'，如果enable为true，则Layout是可以点击的，touch事件才有意义，否则不可点击

>###### <font color ='#42b983'>**bgImage**</font>: 背景图片

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 : 可设置本地文件：支持data://和source://两种方式。文件格式说明参考Storage类

>###### <font color ='#42b983'>**bgImageFillType**</font>: 背景图片填充方式

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : fillxy
- 说明 : 背景图片填充方式，缺省为fillxy，win8不支持repeatxy方式：
fillxy：拉伸图片（不按比例）以填充layout的宽高
repeatxy：按原图大小重复填充

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**add**</font>: 插入一个UI

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **id** |<font color ='#808000'>**string**</font> |  | 是||为了确保ui自身的id属性和父容器里其他子ui的id重复。这个id作为一个在父容器的唯一标识
  **path** |<font color ='#808000'>**string**</font> |  | 是||插入的ui对应的文件路径，支持data://和source://目录。文件格式说明请参考Storage类。
  **target** |<font color ='#808000'>**string**</font> |  | 否||要插入目标组件模块的id或者地址，插入的ui加在该组件的右面或者下面，为空时表示加在LinearLayout最上面或左边。
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回这个ui文件对应的根节点view的地址
- 说明: 可以在LinearLayout控件内动态插入新的ui组件，新的ui组件的脚本环境和LinearLayout所在的环境是一致的
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**getChildren**</font>: 获取子view的id

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回一个JSON数组，类似['do_Button_1','do_Button_2']
- 说明: 获取当前组件内所有第一层子view的id
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <font color ='#e96900'>**touch**</font>: 点击触发

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 
- 说明: 点击触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


