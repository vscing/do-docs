---
title: do_CheckBox 组件
---

### do_CheckBox 组件

* 支持平台: iOS7.0,Android4.0


#### <font color ='#40A977'>**1.**</font> 属性

>###### <font color ='#42b983'>**enabled**</font>: 是否可点击

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : true
- 说明 : 缺省为true控制组件可点击，当为false时不支持点击

>###### <font color ='#42b983'>**checked**</font>: 是否选中

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : false
- 说明 : 为true时为选中状态，false为未选中状态

>###### <font color ='#42b983'>**text**</font>: 文本显示内容

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 : 获取或设置与此控件关联的文本。

>###### <font color ='#42b983'>**fontColor**</font>: 字体颜色

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 000000FF
- 说明 : 设置字体显示颜色，值格式为：8位16进制字符，前6位是RGB颜色值，后两位是透明度（Alpha），例如：000000FF

>###### <font color ='#42b983'>**fontStyle**</font>: 字体风格

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : normal
- 说明 : 包含4种类型：normal：常规bold：粗体italic：斜体bold_italic：粗斜体（iOS平台不支持）

>###### <font color ='#42b983'>**textFlag**</font>: 字体标示

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : normal
- 说明 : 包含3种类型：
normal：常规
underline ：下划线
strikethrough ：删除线

>###### <font color ='#42b983'>**fontSize**</font>: 字体大小

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 17
- 说明 : 

#### <font color ='#40A977'>**2.**</font> 同步方法

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <font color ='#e96900'>**checkChanged**</font>: 选择切换时触发

- 返回值类型 : <font color ='#808000'>**Bool**</font>
- 返回值描述: 返回当前控件状态
- 说明: 选择切换时触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


