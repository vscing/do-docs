---
title: do_CheckBox 组件
---

### do_CheckBox 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_CheckBox)
 

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#42b983'>属性</font>  |[enabled](#enabled)| 是否可点击
<font color ='#42b983'>属性</font>  |[checked](#checked)| 是否选中
<font color ='#42b983'>属性</font>  |[text](#text)| 文本显示内容
<font color ='#42b983'>属性</font>  |[fontColor](#fontColor)| 字体颜色
<font color ='#42b983'>属性</font>  |[fontStyle](#fontStyle)| 字体风格
<font color ='#42b983'>属性</font>  |[textFlag](#textFlag)| 字体标示
<font color ='#42b983'>属性</font>  |[fontSize](#fontSize)| 字体大小
<font color ='#e96900'>事件</font>  |[checkChanged](#checkChanged)| 选择切换时触发

#### <font color ='#40A977'>**1.**</font> 属性

>###### <span id=enabled><font color ='#42b983'>**enabled**</font></span>: 是否可点击

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : true
- 说明 : 缺省为true控制组件可点击，当为false时不支持点击

>###### <span id=checked><font color ='#42b983'>**checked**</font></span>: 是否选中

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : false
- 说明 : 为true时为选中状态，false为未选中状态

>###### <span id=text><font color ='#42b983'>**text**</font></span>: 文本显示内容

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 : 获取或设置与此控件关联的文本。

>###### <span id=fontColor><font color ='#42b983'>**fontColor**</font></span>: 字体颜色

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 000000FF
- 说明 : 设置字体显示颜色，值格式为：8位16进制字符，前6位是RGB颜色值，后两位是透明度（Alpha），例如：000000FF

>###### <span id=fontStyle><font color ='#42b983'>**fontStyle**</font></span>: 字体风格

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : normal
- 说明 : 包含4种类型：normal：常规bold：粗体italic：斜体bold_italic：粗斜体（iOS平台不支持）

>###### <span id=textFlag><font color ='#42b983'>**textFlag**</font></span>: 字体标示

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : normal
- 说明 : 包含3种类型：
normal：常规
underline ：下划线
strikethrough ：删除线

>###### <span id=fontSize><font color ='#42b983'>**fontSize**</font></span>: 字体大小

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 17
- 说明 : 

#### <font color ='#40A977'>**2.**</font> 同步方法

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=checkChanged><font color ='#e96900'>**checkChanged**</font></span>: 选择切换时触发

- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: 返回当前控件状态
- 说明: 选择切换时触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


