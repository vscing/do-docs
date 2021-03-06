---
title: do_ImageView 组件
---

### do_ImageView 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_ImageView)
 图片控件，可以设置图片背景，也可以设置点击事件作为特殊的按钮使用，当不清楚原图大小时可设置宽高为-1，会显示原始大小的宽高

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#42b983'>属性</font>  |[animation](#animation)| 动画效果
<font color ='#42b983'>属性</font>  |[defaultImage](#defaultImage)| 网络初始化图片
<font color ='#42b983'>属性</font>  |<span style="TEXT-DECORATION: line-through">[radius](#radius)</span>| 圆角半径
<font color ='#42b983'>属性</font>  |[enabled](#enabled)| 是否可点击
<font color ='#42b983'>属性</font>  |[source](#source)| 图片路径
<font color ='#42b983'>属性</font>  |[scale](#scale)| 图片显示类型
<font color ='#42b983'>属性</font>  |[cacheType](#cacheType)| 是否支持网络图片的本地cache
<font color ='#0092db'>同步方法</font>  |[setBitmap](#setBitmap)| 绑定bitmap对象
<font color ='#e96900'>事件</font>  |[touch](#touch)| 点击触发这个事件

#### <font color ='#40A977'>**1.**</font> 属性

>###### <span id=animation><font color ='#42b983'>**animation**</font></span>: 动画效果

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : none
- 说明 : 加载图片时的动画效果，支持none没有动画效果和fade淡入淡出效果
- 示例:

  ```javascript

  var do_ImageView = ui("do_ImageView_1");  //实例化
  do_ImageView.animation = "fade"; //fade淡入淡出效果

  ```
>###### <span id=defaultImage><font color ='#42b983'>**defaultImage**</font></span>: 网络初始化图片

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 :
- 说明 : 当加载一个网络图片比较慢的时候，先显示这个图片，生命周期为从开始加载网络图片到完全正确加载完网络图片为止；支持data://和source://
- 示例:

  ```javascript

  do_ImageView.defaultImage = "source://view/do_ImageCropView/image/1.jpg";

  ```
>###### <span id=radius><font color ='#42b983'>**radius**</font></span>: 圆角半径

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 0
- 说明 : 像素值，为0时表示不是圆角图片；当同时设置了border属性，则radius属性失效（已废弃，建议使用border属性）
- 示例:通过代码设置border属性

  ```javascript

  do_ImageView.border = "ffffffff,1,[175,175,175,175]"

  ```

  下图为未设置border和设置border为"ffffffff,1,[175,175,175,175]"的效果图。

  <div align="center">

  <img src="../../images/imageview_unborder.png" height="310" width="310" >

  <img src="../../images/imageview_border.png" height="310" width="310" >

  </div>
>###### <span id=enabled><font color ='#42b983'>**enabled**</font></span>: 是否可点击

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : false
- 说明 : 缺省为false，控制imageview是否可点击，如果enabled为true，则imageview是可以点击的，否则不可点击。
- 示例:

  ```javascript

  do_ImageView.enabled = true; //可点击

  ```

>###### <span id=source><font color ='#42b983'>**source**</font></span>: 图片路径

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 :
- 说明 : 可设置网络或本地文件，支持：http:// https:// data:// source:// 打头的URI格式，不能包含@符号。其中文件格式说明可参考Storage类
- 示例:

  ```javascript

  do_ImageView.source = "http://photocdn.sohu.com/20161128/Img474303098.jpg?qq-pf-to=pcqq.discussion"; //网络图片

  ```

>###### <span id=scale><font color ='#42b983'>**scale**</font></span>: 图片显示类型

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : fillxy
- 编辑类型 : 只允许设计区内修改。
- 说明 : 图片显示类型，有以下几种方式,缺省为fillxy；
  ```

  fillxy：拉伸图片（不按比例）以填充View的宽高；
  center：按原图大小显示图片，但图片宽高大于View的宽高时，截图图片中间部分显示；
  fillxory：按比例放大原图直至等于某边View的宽高显示；
  centercrop：当图片大于组件时按图片中心点比例缩小图片，直到图片的宽高大于或等于ImageView组件的宽高时截取图片中间部分显示、当图片小于组件时按比例放大直到填充ImageView的宽或高

  ```

>###### <span id=cacheType><font color ='#42b983'>**cacheType**</font></span>: 是否支持网络图片的本地cache

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : never
- 编辑类型 : 只允许设计区内修改。
- 说明 : 只有当imageview的source是http或者https的网络图片时，这个属性才有意义。支持三种缓存方式：
  ```

  always：表示只读本地缓存，缓存没有的时候从远程读取一次然后就缓存到本地;
  never：表示永远不读本地缓存，永远都是读远程图片;
  temporay：表示每次打开这个imageview都会先读缓存的本地图片，然后再读服务器的网络图片，然后再缓存到本地,然后再更新到imageview

  ```

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=setBitmap><font color ='#0092db'>**setBitmap**</font></span>: 绑定bitmap对象

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **bitmap** |<font color ='#808000'>**string**</font> | 是 | |
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明:
- 示例:

  ```javascript

  var bitmap = mm("do_Bitmap");
  do_ImageView.setBitmap(bitmap);

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=touch><font color ='#e96900'>**touch**</font></span>: 点击触发这个事件

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述:
- 说明: 点击触发这个事件
- 示例:

  ```javascript
//点击图片给图片增加"deviceone"水印,并将imageview组件赋值为新增加水印的图片。写的时候记得将do_ImageView组件绑定bitmap对象，即setBitmap方法。
do_ImageView.on("touch",function(){
  //支持添加文本水印和图片水印，添加水印之前必须先loadFile
  	bitmap.loadFile(do_ImageView.source, function(data, e) {
  		if (data) {
  			bitmap.addWatermark("text", "deviceone", 50, 20, "8080FFFF", "bold", "underline",80, function(_data, e) {
  				if (_data) {
  					var _image = "data://save/" + sm("do_Global").getTime() + ".png";
  					bitmap.save("PNG", 100, _image, function(bitmap_image, e) {
  						if (bitmap_image) {
  							do_ImageView.source = bitmap_image;
  							deviceone.print(bitmap_image);
  						};
  					});
  				};
  			});
  		};
  	});
});

  ```

  下图为的效果图。

  <div>

  <img src="../../images/imageview_bitmap.png" height="310" width="310" >

  </div>

[回到顶部](#top)

#### <font color ='#40A977'>**5.**</font> 常见问题
    - 1.为什么do_ImageView的touch事件无效？
      do_ImageView缺省是用来加载图片，缺省是不支持点击的，有一个属性enable设置为true就可以了。

#### <font color ='#40A977'>**6.**</font> 基本配置
    - 1.   

[回到顶部](#top)           
