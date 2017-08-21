---
title: do_ComboBox 组件
---

### do_ComboBox 组件

 支持平台: iOS7.0,Android4.0
 点击控件会弹出一个选择列表，单击选项即可选中

#### <font color ='#40A977'>**1.**</font> 属性

>###### <font color ='#42b983'>**fontColor**</font>: 字体前景色

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 000000FF
- 说明 : 设置字体显示颜色，值格式为：8位16进制字符，前6位是RGB颜色值，后两位是透明度（Alpha），例如：000000FF

>###### <font color ='#42b983'>**fontSize**</font>: 字体大小

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 17
- 说明 : 

>###### <font color ='#42b983'>**fontStyle**</font>: 字体风格

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : normal
- 说明 : 包含4种类型：normal：常规bold：粗体italic：斜体bold_italic：粗斜体（iOS平台不支持）

>###### <font color ='#42b983'>**textFlag**</font>: 字体标示

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : normal
- 说明 : 包含3种类型：normal：常规underline ：下划线strikethrough ：删除线

>###### <font color ='#42b983'>**index**</font>: 当前选中的数据索引

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 
- 说明 : 数据的索引值，设置时会切换数据选择，索引小于0时指向数组第一个数据，越界时指向数组最后一个数据

>###### <font color ='#42b983'>**items**</font>: 数据集合

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 : 可供选择的数据集合，中间用逗号隔开多个文本，如'北京,上海,广州...'

>###### <font color ='#42b983'>**textAlign**</font>: 文本对齐方式

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : left
- 说明 : 对齐方式为以下3种：left 左对齐（默认）；center 居中；right 右对齐；windows平台不支持

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**bindItems**</font>: 绑定item的数据

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **data** |<font color ='#808000'>**object**</font> |  | 否||比如[{'text':'a1','id':'1'},{'text':'a2','id':'2'}]，其中text字段是必须的，用于显示文本内容，这里显示的就是a1，a2，其他字段可任意增加，根据选择的item索引获取内容
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

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <font color ='#e96900'>**selectChanged**</font>: 当数据变化或数据索引变化触发

- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 返回选中数据的索引
- 说明: 当数据变化或数据索引变化触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


