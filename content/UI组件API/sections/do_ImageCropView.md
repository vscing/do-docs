---
title: do_ImageCropView 组件
---

### do_ImageCropView 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_ImageCropView)
 图片裁剪视图，能设置view的基本属性，宽高等

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#42b983'>属性</font>  |[source](#source)| 图片路径
<font color ='#42b983'>属性</font>  |[cropArea](#cropArea)| 裁剪的区域
<font color ='#0092db'>异步方法</font>  |[crop](#crop)| 裁剪图片

#### <font color ='#40A977'>**1.**</font> 属性

>###### <span id=source><font color ='#42b983'>**source**</font></span>: 图片路径

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 :
- 说明 : 可设置本地文件，支持 data:// source:// 打头
- 示例:

  ```javascript

  var do_ImageCropView = ui("do_ImageCropView_1");
  do_ImageCropView.source = "source://view/do_ImageCropView/image/1.jpg";

  ```

>###### <span id=cropArea><font color ='#42b983'>**cropArea**</font></span>: 裁剪的区域

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 :
- 说明 : 设置裁剪区域的宽高，width,height，中间用逗号隔开；裁剪区域不建议设置超出组件本身宽高和范围；默认值取控件的一半宽高，居中显示
- 示例:

  ```javascript

  var do_ImageCropView = ui("do_ImageCropView_1");
  do_ImageCropView.cropArea = "500,500";

  ```
  下图分别为剪裁区域为(500,500)和(300,500)的效果图。

  <div>

  <img src="../../images/imagecropview_500.png" height="380" width="320" >

  <img src="../../images/imagecropview_300.png" height="380" width="320" >

  </div>

#### <font color ='#40A977'>**2.**</font> 同步方法

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <span id=crop><font color ='#0092db'>**crop**</font></span>: 裁剪图片

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回裁剪图片的路径
- 说明: 根据裁剪区域，裁剪图片
- 示例:

  ```javascript

  do_ImageCropView.crop(function(data, e) {
		deviceone.print(data);
	})

  ```

  ```
  以上示例代码返回的data如下:

  ios剪裁后返回的图片路径:
      data://tmp/do_ImageCropView/2C6B2461-64D0-4828-A43B-4589245468DE.jpg

  android剪裁后返回的图片路径:
      data://temp/do_ImageCropView/201709151506334.png.do

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件
