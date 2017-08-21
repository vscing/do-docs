---
title: do_BaiduMapView 组件
---

### do_BaiduMapView 组件

 支持平台: iOS7.0,Android4.0
 集成百度地图，实现基本的地图功能，包括设置中心点，添加标记等

#### <font color ='#40A977'>**1.**</font> 属性

>###### <font color ='#42b983'>**mapScene**</font>: 地图场景

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 0
- 说明 : 地图场景，场景目前支持两种：0表示当前同一个page里面包含VideoView等视频组件的场景（解决会互相覆盖的问题），1表示不包含，1的渲染效果比0好，若不同时在地图页面使用视频组件，建议选1。iOS平台不支持

>###### <font color ='#42b983'>**mapType**</font>: 地图类型

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : standard
- 说明 : 地图类型，支持标准地图standard和卫星地图satellite

>###### <font color ='#42b983'>**zoomLevel**</font>: 地图缩放等级

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 10
- 说明 : 地图缩放等级，可以设置级别为 3-18 ,对应地图比例尺20m - 2000公里，具体对应关系可以参考百度地图开发文档

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**addMarkers**</font>: 添加一组标记

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **data** |<font color ='#808000'>**object**</font> |  | 是||[{id:标记ID，用户自定义标记唯一ID，是字符串类型,latitude:纬度,longitude:经度,url:缩略图地址,info:描述信息,popup:是否可点击，是否支持点击弹出信息，为true时支持，为false时点击marks不弹出信息，仅触发touchMarker事件，默认为true,textMarker:文字Mark}]，其中id必须唯一，textMarker为一个JSON对象，包含文字Mark的一些属性，如{ text: 文本, fontColor: 设置字体显示颜色，值格式为：8位16进制字符，前6位是RGB颜色值，后两位是透明度（Alpha），默认值为：000000FF, fontStyle: 设置字体风格包含normal：常规bold：粗体两种风格，默认值为：normal, fontSize: 字体大小，默认值为：17, alignX: 支持left(左对齐)，right(右对齐)，center(水平居中对齐)，默认值为：center, alignY: 支持top(上对齐)，bottom(下对齐)，center(垂直居中对齐)，默认值为：center , bgColor: 文字背景色，默认值为：FFFFFF00, radius: 文字背景圆角，默认值为：0 }
- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: true 成功 false 失败
- 说明: 将一组经纬度用缩略图在百度地图标记出来,点击缩略图后弹出描述信息,缩略图地址为 data:// source:// 打头的URI格式，不能包含@符号。其中文件格式说明可参考Storage类
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**addOverlay**</font>: 添加集合图形

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **type** |<font color ='#808000'>**number**</font> |  | 是||支持的类型有，0圆形Circle，1折线:Polyline，2多边形:Polygon，3圆弧:Arc
  **data** |<font color ='#808000'>**object**</font> |  | 是||根据类型传递不同的参数；圆形:需要中心点坐标(经纬度)和半径(单位:米),{"latitude":"39.965","longitude":"116.404","radius":"10000"}；折线和多边形:每一个是一个经纬度点,[{"latitude":"39.965","longitude":"116.404"},{"latitude":"39.965","longitude":"116.404"}...]；圆弧:根据指定经纬度生成一段圆弧,指定的经纬度坐标点数组(需传入3个点),每一个是一个经纬度点[{"latitude":"39.965","longitude":"116.404"},{"latitude":"39.965","longitude":"116.404"}]，需要注意的是圆形的情况只有一个点，不是数组
  **id** |<font color ='#808000'>**string**</font> |  | 是||要添加的集合图形ID
  **fillColor** |<font color ='#808000'>**string**</font> | 00000000 | 否|00000000|只有闭合图形才有填充颜色
  **strokeColor** |<font color ='#808000'>**string**</font> | 000000FF | 否|000000FF|
  **width** |<font color ='#808000'>**number**</font> | 5 | 否|5|
  **isDash** |<font color ='#808000'>**boolean**</font> | false | 否|false|线条是否显示为虚线，android只有折线可以设置为虚线
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 添加集合图形遮盖物
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**getDistance**</font>: 获取实际距离

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **startPoint** |<font color ='#808000'>**string**</font> |  | 是||设置起点经纬度，如39.915174,116.403901表示(纬度,经度)
  **endPoint** |<font color ='#808000'>**string**</font> |  | 是||设置终点经纬度，如40.915174,117.403901表示(纬度,经度)
- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 返回坐标点之间距离，单位为米
- 说明: 根据地图上两个点的坐标来获取两点之间实际直线距离
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**pauseDownload**</font>: 暂停下载离线地图

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **cityID** |<font color ='#808000'>**number**</font> |  | 是||
- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: 成功返回true，失败返回false
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**removeAll**</font>: 移除所有标记

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 移除所有标记
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**removeDownload**</font>: 移除下载离线地图

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **cityID** |<font color ='#808000'>**number**</font> |  | 是||
- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: 成功返回true，反之返回false
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**removeMarker**</font>: 移除一组指定标记

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **ids** |<font color ='#808000'>**object**</font> |  | 是||要移除的标记ID数组
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 移除一组指定标记
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**removeOverlay**</font>: 移除一组图形集合

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **ids** |<font color ='#808000'>**object**</font> |  | 是||要移除的几何图形ID数组
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 移除一组图形集合
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**setCenter**</font>: 设置地图中心点

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **latitude** |<font color ='#808000'>**string**</font> | 39.915174 | 是|39.915174|设置地图中心点纬度，默认是北京天安门坐标纬度
  **longitude** |<font color ='#808000'>**string**</font> | 116.403901 | 是|116.403901|设置地图中心点经度，默认是北京天安门坐标经度
- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: true 成功 false 失败
- 说明: 设置地图中心点
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <font color ='#0092db'>**getHotCityList**</font>: 获得所有热门城市

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: [{'cityID':城市id,'cityName':城市名称,'size':离线包大小，单位为字节}]
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**poiSearch**</font>: 搜索服务

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **type** |<font color ='#808000'>**number**</font> |  | 是||搜索类型，是一个枚举值。0:城市POI检索;1:在矩形范围内POI检索;2:根据中心点、半径POI检索;
  **keyword** |<font color ='#808000'>**string**</font> |  | 是||搜索的关键字
  **param** |<font color ='#808000'>**object**</font> |  | 是||根据检索类型设置检索参数，当type = 0时，param为{city:''}；当type = 1时，param 为{leftBottom:'39.915174,116.403901(纬度,经度)',rightTop:'39.915174,116.403901(纬度,经度)'}表示矩形区域，左下角和右上角的经纬度坐标点；当type = 2时，param为{location:'39.915174,116.403901(纬度,经度)',radius:''}，其中location为检索的中心点经纬度，radius为周边检索半径，单位为米
  **pageIndex** |<font color ='#808000'>**number**</font> | 0 | 否|0|
  **pageSize** |<font color ='#808000'>**number**</font> | 10 | 否|10|
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 搜索结果列表,是一个数组,每一项是一个字典,包括{name:'POI名称',pt:'POI坐标',address:'POI地址',city:'POI所在城市',phone:'POI电话号码'}
- 说明: 根据关键词搜索
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**routePlanSearch**</font>: 路线检索

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **type** |<font color ='#808000'>**string**</font> |  | 是||路线检索类型,包括Bus(公交);Ride(骑行);Walk(步行);Drive(驾车)
  **startCityName** |<font color ='#808000'>**string**</font> |  | 是||城市名称
  **endCityName** |<font color ='#808000'>**string**</font> |  | 是||城市名称
  **startCitySite** |<font color ='#808000'>**string**</font> |  | 是||所在城市的地点名称或者开始地点的经纬度例如39.915174,116.403901表示(纬度,经度)
  **endCitySite** |<font color ='#808000'>**string**</font> |  | 是||所在城市的地点名称或者结束地点的经纬度例如39.915174,116.403901表示(纬度,经度)
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 路线检索，检索出的路线会直接显示在地图上，并可点击查看详细信息，当检索城市与地点不在同一城市中，以经纬度为准
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**startDownload**</font>: 开始下载离线地图

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **cityID** |<font color ='#808000'>**number**</font> |  | 是||
- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: 成功返回true，失败返回false
- 说明: pauseDownload后再次调startDownload可继续下载
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件

>###### <font color ='#e96900'>**download**</font>: 下载离线地图触发的事件

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {'cityID':城市id,'cityName':城市名称,'ratio':下载进度（0~100）100表示下载完成}
- 说明: 下载离线地图触发的事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**regionChange**</font>: 地图区域改变完成后会触发，返回地图区域的中心点坐标

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {latitude:'', longitude:''}
- 说明: 地图区域改变完成后会触发，返回地图区域的中心点坐标
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**touchMap**</font>: 点击地图时触发

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回当前点击的位置坐标{"latitude":"纬度","longitude":"经度"}
- 说明: 点击地图时触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**touchMarker**</font>: 点击标记时触发，iOS平台只有第一次点击mark会触发该事件，之后需要点击弹出的缩略图触发

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 
- 说明: 点击标记时触发，iOS平台只有第一次点击mark会触发该事件，之后需要点击弹出的缩略图触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


