---
title: do_PainterView 组件
---

### do_PainterView 组件

 支持平台: iOS7.0,Android4.0
 手势滑动时会在view中留下移动痕迹

#### <font color ='#40A977'>**1.**</font> 属性

>###### <font color ='#42b983'>**brushWidth**</font>: 画笔宽度

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 3
- 说明 : 宽度最小为1，表示1像素宽度

>###### <font color ='#42b983'>**brushColor**</font>: 画笔颜色

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : FF0000FF
- 说明 : 设置画笔颜色，值格式为：8位16进制字符，前6位是RGB颜色值，后两位是透明度（Alpha），例如：000000FF，默认为红色

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**undo**</font>: 回退操作

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 撤销当前步骤，回退到上一步
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**clear**</font>: 清空画板

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 清空整个画板内容
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <font color ='#0092db'>**saveAsImage**</font>: 保存为图片

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **format** |<font color ='#808000'>**string**</font> | 否 | JPEG|支持两种格式：PNG，JPEG
  **quality** |<font color ='#808000'>**number**</font> | 否 | 100|图片的压缩质量，支持 1-100，windows平台不支持
  **outPath** |<font color ='#808000'>**string**</font> | 否 | |保存的图片路径支持data://目录，如果为空，缺省返回唯一图片路径，会另存到data://temp/do_PainterView/目录下
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回当前保存的图片路径，为空时表示保存失败
- 说明: 将整个view保存为一个图片
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**saveAsBitmap**</font>: 保存为Bitmap

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **bitmap** |<font color ='#808000'>**string**</font> | 是 | |
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 将整个view保存为一个Btimap
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件


