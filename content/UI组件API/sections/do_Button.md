---
title: do_Button 组件
---

### do_Button 组件

 支持平台: iOS7.0,Android4.0
 按钮控件，支持通常按钮的属性，方法和事件，缺省是透明无边框。abc

#### <font color ='#40A977'>**1.**</font> 属性

>###### <font color ='#42b983'>**enabled**</font>: 是否有效

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : true
- 说明 : 控制button的点击事件，缺省为true，表示用户如果点击按钮会触发button的三种touch事件

>###### <font color ='#42b983'>**text**</font>: 标题

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 : 获取或设置与此控件关联的文本

>###### <font color ='#42b983'>**fontColor**</font>: 字体颜色

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

>###### <font color ='#42b983'>**radius**</font>: 圆角半径

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 0
- 说明 : 像素值，为0时表示不是圆角按钮；@deprecated，该属性为不建议使用，建议使用UI的基础属性border来替代

>###### <font color ='#42b983'>**bgImage**</font>: 背景图片

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 : 可设置本地文件：支持data://和source://两种方式。文件格式说明参考Storage类

#### <font color ='#40A977'>**2.**</font> 同步方法

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <font color ='#e96900'>**touch**</font>: 按下并在按钮范围抬起，触发该事件

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 
- 说明: 按下并在按钮范围抬起，触发该事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**touchDown**</font>: 按钮范围内按下即可触发

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 
- 说明: 按钮范围内按下即可触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**touchUp**</font>: 一旦按下，手指离开即触发，不论是否在按钮范围内

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 
- 说明: 一旦按下，手指离开即触发，不论是否在按钮范围内
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


