---
title: do_Album 组件
---

### do_Album 组件

 支持平台: iOS7.0,Android4.0
 可以通过打开手机的系统相册选择图片然后保存在本地目录下，且可以指定保存过后图片的质量，宽高；也支持一张本地的图片收藏到系统相册

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <font color ='#0092db'>**select**</font>: 从系统相册选择照片

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **maxCount** |<font color ='#808000'>**number**</font> | 9 | 否|9|可设置让用户最多一次能选择图片的张数
  **width** |<font color ='#808000'>**number**</font> |  | 否||保存后的图片的宽度，不设置就是不缩放，宽度越小，图片的文件大小越小
  **height** |<font color ='#808000'>**number**</font> |  | 否||保存后的图片的高度，不设置就是不缩放，高度越小，图片的文件大小越小
  **quality** |<font color ='#808000'>**number**</font> | 100 | 否|100|清晰度1-100,缺省是100表示原始的图片质量，质量越小越模糊，但是图片的文件大小越小
  **iscut** |<font color ='#808000'>**Boolean**</font> | false | 否|false|只有在maxCount设置为1时该参数设置成true才有效。

如果这个值为true的话，照片选择结束后会出现一个中间的取景界面，有一个矩形框让用户对照片进行裁剪。

这里可以参考<a href="http://doc.deviceone.net/web/doc/code4do/imagecrop.htm">do_ImageCropView</a>组件来实现新的取景方法。

注:windows不支持这个参数。

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回一个js数组，类似["data://temp/do_Album/random1.png","data://temp/do_Album/random1.png",...]
- 说明:  可以单选一张图片或者复选多张图片，选定的图片经过缩放最后默认会保存到data://temp/do_Album/目录下一个随机的名字的png文件上，然后返回给用户。

 在Android下保存的文件名的扩展名是.png.do,这是为了避免Android的系统自动把图片加到系统相册。

通常相册里的图片分辨率很高，很多超过1m，在App开发中最好通过缩放和减少图片质量来减少文件大小。

这里图片缩放有可能导致图片变形，因为你选择的宽高比和图片自身的宽高比可能不一致，要解决的办法就是通过设置width或者height的参数值为－1来保证宽高比不变。

<pre class="brush: js;toolbar:false;">var album = sm("do_Album");
album.select(1, 188, -1, 100, true, function(data, e) {
	deviceone.print(data[0]);
})
album.select({maxCount:1, width:188, height:-1, quality:100, iscut:true}, function(data, e) {
	deviceone.print(data[0]);
})</pre>
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**save**</font>: 收藏图片到系统相册

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **path** |<font color ='#808000'>**string**</font> |  | 是||要收藏的图片文件路径,支持initdata://、data://、source://下文件
  **name** |<font color ='#808000'>**string**</font> | default.jpg | 否|default.jpg|收藏到相册后的图片的名称,如果要收藏多个图片，记得设置不同的名称，否则会被覆盖
  **width** |<font color ='#808000'>**number**</font> |  | 否||保存后的图片的宽度，不设置就是不缩放，宽度越小，图片的文件大小越小
  **height** |<font color ='#808000'>**number**</font> |  | 否||保存后的图片的高度，不设置就是不缩放，高度越小，图片的文件大小越小
  **quality** |<font color ='#808000'>**number**</font> | 100 | 否|100|清晰度1-100,缺省是100表示原始的图片质量，质量越小越模糊，但是图片的文件大小越小
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: 保存成功返回true，保存失败返回false
- 说明: 将一个data://下的图片文件保存到系统相册，保存成功后，在系统的相册里就能看到。

保存到相册前可以进行图片的缩放和压缩等处理，规则和select方法一致。

<pre class="brush: js;toolbar:false;">var album = sm("do_Album");
album.save("data://test.png", "test.png", function(data, e) {
	deviceone.print("收藏成功");
})
album.save({path:"data://test.png", name:"test.png",height:50,quality:100}, function(data, e) {
	deviceone.print("收藏成功");
})</pre>
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件


