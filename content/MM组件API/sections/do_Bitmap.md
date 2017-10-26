---
title: do_Bitmap 组件
---

### do_Bitmap 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/MM/do_Bitmap)
 图片的处理组件，通过加载source对应路径的图片到内存中，不再需要使用该位图资源必须调用MM组件基类方法release()来释放该使用内存，Android平台仅支持jpg和JEPG格式

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#0092db'>同步方法</font>  |[getExif](#getExif)| 获取图片拍摄信息
<font color ='#0092db'>异步方法</font>  |[addWatermark](#addWatermark)| 添加水印
<font color ='#0092db'>异步方法</font>  |[loadFile](#loadFile)| 加载位图
<font color ='#0092db'>异步方法</font>  |[save](#save)| 保存位图
<font color ='#0092db'>异步方法</font>  |[toGrayScale](#toGrayScale)| 转成灰色位图
<font color ='#0092db'>异步方法</font>  |[toFrostedGlass](#toFrostedGlass)| 转成毛玻璃位图
<font color ='#0092db'>异步方法</font>  |[toRoundCorner](#toRoundCorner)| 添加圆角

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=getExif><font color ='#0092db'>**getExif**</font></span>: 获取图片拍摄信息

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **source** |<font color ='#808000'>**string**</font> | 是 | |只支持本地文件，支持： data:// source:// 打头的URI格式，不能包含@符号。其中文件格式说明可参考Storage类
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {'Width':'图像横向像素数','Height':'图像纵向像素数','Make:'相机生产厂家','Model':'型号','ExposureTime':'快门速度','FNumber':'光圈','ISO':'感光度','Date':'拍摄时间2016:01:01 09:00:00','FocalLength','镜头焦距','LensMake':'镜头生产商','LensModel':'镜头型号','MeteringMode':'测光模式','LightSource':'白平衡设定'}
- 说明: 获取图片拍摄信息
- 示例:

  ```javascript
  var data = do_Bitmap.getExif({source:"source://view/MM/do_Bitmap/1.jpg"});
	deviceone.print(JSON.stringify(data),"获取信息")

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <span id=addWatermark><font color ='#0092db'>**addWatermark**</font></span>: 添加水印

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **type** |<font color ='#808000'>**string**</font> | 是 | |text：文本类型，image：图片类型
  **source** |<font color ='#808000'>**string**</font> | 是 | |当type = text，source就是要添加的文本内容；type = image，source就是要添加图片的路径，支持source://和data://打头的文件和bitmap对象
  **percentX** |<font color ='#808000'>**number**</font> | 否 | 50|相对于图片大小的一个百分比位置
  **percentY** |<font color ='#808000'>**number**</font> | 否 | 50|相对于图片大小的一个百分比位置
  **fontColor** |<font color ='#808000'>**string**</font> | 否 | 000000FF|设置字体显示颜色，值格式为：8位16进制字符，前6位是RGB颜色值，后两位是透明度（Alpha），例如：000000FF
  **fontStyle** |<font color ='#808000'>**string**</font> | 否 | normal|包含4种类型：normal：常规bold：粗体italic：斜体bold_italic：粗斜体（iOS平台不支持）
  **textFlag** |<font color ='#808000'>**string**</font> | 否 | normal|包含3种类型：normal：常规underline ：下划线strikethrough ：删除线
  **fontSize** |<font color ='#808000'>**number**</font> | 否 | 17|
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: 成功返回true，失败返回false
- 说明: 支持添加文本水印和图片水印，添加水印之前必须先loadFile
- 示例:

  ```javascript
  do_Bitmap.addWatermark({type:"text", source:"12345abcde", fontColor:"64B1FFFF", fontStyle:"italic", textFlag:"strikethrough", fontSize:"33"}, function(data, e) {
		deviceone.print(data,"添加结果")
	})

  ```

[回到顶部](#top)

>##### <span id=loadFile><font color ='#0092db'>**loadFile**</font></span>: 加载位图

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **source** |<font color ='#808000'>**string**</font> | 是 | |可设置网络或本地文件，支持：http:// https:// data:// source:// 打头的URI格式，不能包含@符号。其中文件格式说明可参考Storage类
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: 成功返回true，失败返回false
- 说明: 加载位图到内存中，当加在网络图片时耗时可能稍长
- 示例:

  ```javascript
  do_Bitmap.loadFile({source:"source://view/MM/do_Bitmap/1.jpg"}, function(data, e) {
  	deviceone.print(data,"loadFile结果")
  })

  ```

[回到顶部](#top)

>##### <span id=save><font color ='#0092db'>**save**</font></span>: 保存位图

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **format** |<font color ='#808000'>**string**</font> | 否 | JPEG|支持两种格式：PNG，JPEG
  **quality** |<font color ='#808000'>**number**</font> | 否 | 100|图片的压缩质量，支持 1-100，windows平台不支持
  **outPath** |<font color ='#808000'>**string**</font> | 否 | |保存的图片路径支持：data://开头，如果为空，缺省返回唯一图片路径，会另存到data://temp/do_Bitmap/目录下
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回当前保存的图片路径，为空时表示保存失败
- 说明: 保存位图到本地
- 示例:

  ```javascript
  do_Bitmap.save({format:"PNG", quality:50, outPath:"source://view/MM/do_Bitmap/1.jpg"}, function(data, e) {
		do_ImageView_1.source=data
	})

  ```

[回到顶部](#top)

>##### <span id=toGrayScale><font color ='#0092db'>**toGrayScale**</font></span>: 转成灰色位图

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: 成功返回true，失败返回false
- 说明: 转换成灰色位图
- 示例:

  ```javascript
  do_Bitmap.toGrayScale(function(data, e) {
		deviceone.print(data,"转换结果")
	})

  ```

[回到顶部](#top)

>##### <span id=toFrostedGlass><font color ='#0092db'>**toFrostedGlass**</font></span>: 转成毛玻璃位图

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **degree** |<font color ='#808000'>**number**</font> | 是 | |图片的模糊程度，支持 1-100
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: 成功返回true，失败返回false
- 说明: 转成毛玻璃位图
- 示例:

  ```javascript
  do_Bitmap.toGrayScale(function(data, e) {
		deviceone.print(data,"转换结果")
	})
  ```

[回到顶部](#top)

>##### <span id=toRoundCorner><font color ='#0092db'>**toRoundCorner**</font></span>: 添加圆角

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **radius** |<font color ='#808000'>**number**</font> | 是 | |
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: 成功返回true，失败返回false
- 说明: 为位图添加圆角效果，windows平台不支持
- 示例:

  ```javascript
  do_Bitmap.toRoundCorner({radius:250}, function(data, e) {
		deviceone.print(data,"添加结果")
	})

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件
