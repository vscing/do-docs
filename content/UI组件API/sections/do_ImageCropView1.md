---
title: do_ImageCropView1 组件
---

### do_ImageCropView1 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_ImageCropView1)
 图片裁剪视图，裁剪区域可以拖动和缩放，能设置view的基本属性，宽高等

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#42b983'>属性</font>  |[source](#source)| 图片路径
<font color ='#0092db'>异步方法</font>  |[crop](#crop)| 裁剪图片

#### <font color ='#40A977'>**1.**</font> 属性

>###### <span id=source><font color ='#42b983'>**source**</font></span>: 图片路径

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 : 可设置本地文件，支持 data:// source:// 打头

#### <font color ='#40A977'>**2.**</font> 同步方法

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <span id=crop><font color ='#0092db'>**crop**</font></span>: 裁剪图片

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回裁剪图片的路径
- 说明: 根据裁剪区域，裁剪图片
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件


