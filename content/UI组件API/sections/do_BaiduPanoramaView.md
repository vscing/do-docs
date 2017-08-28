---
title: do_BaiduPanoramaView 组件
---

### do_BaiduPanoramaView 组件

 支持平台: iOS7.0,Android4.0
 百度全景图是一种实景地图服务。为用户提供城市、街道和其他环境的360度全景图像，用户可以通过该服务获得如临其境的地图浏览体验。全景地图使用新的地图技术，营造新的产品体验。真正实现“人视角”的地图浏览体验，为用户提供更加真实准确、更富画面细节的地图服务。参考[示例](https://github.com/do-api/docs-example/tree/master/source/view/do_BaiduPanoramaView)
#### <font color ='#40A977'>**1.**</font> 属性

>###### <font color ='#42b983'>**zoomLevel**</font>: 全景图缩放级别

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 2
- 说明 : 设置全景图的缩放级别，默认缩放级别为2级，缩放级别总共分为5级，分别是1-5级，随着级别的增大清晰度逐渐提高。

>###### <font color ='#42b983'>**imageLevel**</font>: 全景图片的显示级别

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 2
- 说明 : 设置全景图片的显示级别，1为较低清晰度, 2为中等清晰度 , 3为较高清晰度。

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**showPanoramaView**</font>: 显示全景图

- 参数:

  名称 | 类型 | 必填 | 默认值 | 说明
  ---- |------|------|------|------
  **latitude** |<font color ='#808000'>**string**</font> | 是 |     |坐标纬度
  **longitude** |<font color ='#808000'>**string**</font> | 是 |     |坐标经度
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 根据经纬度显示全景图
- 示例:
  ```javascript
  var do_BaiduPanoramaView = ui("do_BaiduPanoramaView_1");

  //显示全景图
  do_BaiduPanoramaView.showPanoramaView({
  	"latitude" : "41.867335",
  	"longitude" : "123.90583"
  });
  ```
  下图所示是经度123.90583，纬度41.867335的全景图：
  ![](../../images/baidupanoramaview_realmap.png)
[回到顶部](#top)

>##### <font color ='#0092db'>**addImageMarkers**</font>: 添加一组缩略图标记

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |------|------|------|------
  **data** |<font color ='#808000'>**object**</font> | 是 | |
- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: true 成功 false 失败
- 说明: 将一组经纬度用缩略图在百度地图标记出来,缩略图地址为 data:// source:// 打头的URI格式，不能包含@符号。其中文件格式说明可参考Storage类；iOS8.0以下不支持。参数示例，其中标记ID必须唯一
  ```

  [
      {
          "id":标记ID,用户自定义标记唯一ID,
          "latitude":纬度,
          "longitude":经度,
          "url":缩略图地址
      },
      ...
  ]
  ```
- 示例:
  ```javascript
  //添加一组缩略图标记
  do_BaiduPanoramaView.addImageMarkers([ {
  	"id" : "id1",
  	"latitude" : "41.867335",
  	"longitude" : "123.90583",
  	"url" : "source://view/do_BaiduPanoramaView/location.png"
  }, {
  	"id" : "id2",
  	"latitude" : "41.857335",
  	"longitude" : "123.90583",
  	"url" : "source://view/do_BaiduPanoramaView/location.png"
  }, {
  	"id" : "id3",
  	"latitude" : "41.847335",
  	"longitude" : "123.90583",
  	"url" : "source://view/do_BaiduPanoramaView/location.png"
  }, {
  	"id" : "id4",
  	"latitude" : "41.837335",
  	"longitude" : "123.90583",
  	"url" : "source://view/do_BaiduPanoramaView/location.png"
  } ])

  ```
  下图所示是添加一组缩略图标记的全景图：
  ![](../../images/baidupanoramaview_addimagemarkers.png)
[回到顶部](#top)

>##### <font color ='#0092db'>**addTextMarkers**</font>: 添加一组文本标记

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |------|------|------|------
  **data** |<font color ='#808000'>**object**</font> | 是 | |
- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: true 成功 false 失败
- 说明:参数示例，其中标记ID必须唯一
  ```

  [
      {
          "id":标记ID,用户自定义标记唯一ID,
          "latitude":纬度,
          "longitude":经度,
          "text":文字标注的内容,
          "fontColor":字体颜色,
          "fontSize":字体大小
      },
      ...
  ]
  ```
- 示例:
  ```javascript
  //添加一组文本标记
  do_BaiduPanoramaView.addTextMarkers([ {
 	"id" : "01",
 	"latitude" : "40.767335",
 	"longitude" : "123.80583",
 	"text" : "文字标记1",
 	"fontColor" : "000000FF",
 	"fontSize" : 30
 }, {
 	"id" : "02",
 	"latitude" : "40.667335",
 	"longitude" : "124.70583",
 	"text" : "文字标记2",
 	"fontColor" : "FF0000FF",
 	"fontSize" : 30
 }, {
 	"id" : "03",
 	"latitude" : "40.567335",
 	"longitude" : "125.60583",
 	"text" : "文字标记3",
 	"fontColor" : "00FF00FF",
 	"fontSize" : 20
 }, {
 	"id" : "04",
 	"latitude" : "40.467335",
 	"longitude" : "126.50583",
 	"text" : "文字标记4",
 	"fontColor" : "FF8000FF",
 	"fontSize" : 20
 }, {
 	"id" : "05",
 	"latitude" : "40.367335",
 	"longitude" : "127.40583",
 	"text" : "文字标记5",
 	"fontColor" : "FF0080FF",
 	"fontSize" : 20
 } ])

  ```
  下图所示是添加一组文本标记的全景图：
  ![](../../images/baidupanoramaview_addtextmarkers.png)
[回到顶部](#top)

>##### <font color ='#0092db'>**removeMarker**</font>: 移除一组指定标记

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |------|------|------|------
  **ids** |<font color ='#808000'>**object**</font> | 是 | |要移除的标记ID数组
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 移除一组指定标记，参数示例
  ```

  {
      "ids":[
          "id1",
          "id2",
          ...  
      ]
  }
  ```
- 示例:
  ```javascript

  //移除一组指定标记，全景图上有对应标记的时候才可以使用
  do_BaiduPanoramaView.removeMarker({
  	  ids : [ "01", "02", "03", "04", "05" ]
  });

  ```

>##### <font color ='#0092db'>**removeAll**</font>: 移除所有标记

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 移除所有标记
- 示例:

  ```javascript

  //移除当前全景图上添加的所有标记
  do_BaiduPanoramaView.removeAll();
  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <font color ='#e96900'>**touchMarker**</font>: 点击标记时触发

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述:
  ```

  {
      "id":标记ID,用户自定义标记唯一ID,
      "latitude":纬度,
      "longitude":经度,
      "type":ImageMark|TextMark,
      "info":当type为ImageMark时返回缩略图地址|当type为TextMark时返回文字标注内容
  }
  ```
- 说明: 点击标记时触发
- 示例:
  ```javascript

  //点击标记时触发该事件
  do_BaiduPanoramaView.on("touchMarker", function(data) {
  	  deviceone.print(JSON.stringify(data), "点击标记");
  });

  ```

#### <font color ='#40A977'>**5.**</font> 常见问题

#### <font color ='#40A977'>**6.**</font> 基本配置
  - 1.使用百度全景图时需要给组件配置对应的key,具体key值怎么获取参见[示例文档](/UI组件API/sections/百度定位相关配置/)


[回到顶部](#top)
