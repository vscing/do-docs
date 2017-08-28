---
title: do_BaiduMapView 组件
---

### do_BaiduMapView 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_BaiduMapView)
 集成百度地图，实现基本的地图功能，包括设置中心点，添加标记等

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#42b983'>属性</font>  |[mapScene](#mapScene)| 地图场景
<font color ='#42b983'>属性</font>  |[mapType](#mapType)| 地图类型
<font color ='#42b983'>属性</font>  |[zoomLevel](#zoomLevel)| 地图缩放等级
<font color ='#0092db'>同步方法</font>  |[addMarkers](#addMarkers)| 添加一组标记
<font color ='#0092db'>同步方法</font>  |[addOverlay](#addOverlay)| 添加集合图形
<font color ='#0092db'>同步方法</font>  |[getDistance](#getDistance)| 获取实际距离
<font color ='#0092db'>同步方法</font>  |[pauseDownload](#pauseDownload)| 暂停下载离线地图
<font color ='#0092db'>同步方法</font>  |[removeAll](#removeAll)| 移除所有标记
<font color ='#0092db'>同步方法</font>  |[removeDownload](#removeDownload)| 移除下载离线地图
<font color ='#0092db'>同步方法</font>  |[removeMarker](#removeMarker)| 移除一组指定标记
<font color ='#0092db'>同步方法</font>  |[removeOverlay](#removeOverlay)| 移除一组图形集合
<font color ='#0092db'>同步方法</font>  |[setCenter](#setCenter)| 设置地图中心点
<font color ='#0092db'>异步方法</font>  |[getHotCityList](#getHotCityList)| 获得所有热门城市
<font color ='#0092db'>异步方法</font>  |[poiSearch](#poiSearch)| 搜索服务
<font color ='#0092db'>异步方法</font>  |[routePlanSearch](#routePlanSearch)| 路线检索
<font color ='#0092db'>异步方法</font>  |[startDownload](#startDownload)| 开始下载离线地图
<font color ='#e96900'>事件</font>  |[download](#download)| 下载离线地图触发的事件
<font color ='#e96900'>事件</font>  |[regionChange](#regionChange)| 地图区域改变完成后会触发，返回地图区域的中心点坐标
<font color ='#e96900'>事件</font>  |[touchMap](#touchMap)| 点击地图时触发
<font color ='#e96900'>事件</font>  |[touchMarker](#touchMarker)| 点击标记时触发，iOS平台只有第一次点击mark会触发该事件，之后需要点击弹出的缩略图触发

#### <font color ='#40A977'>**1.**</font> 属性

>###### <span id="mapScene"><font color ='#42b983'>**mapScene**</font>: 地图场景

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 0
- 编辑类型 : 只允许设计区内修改。
- 说明 : 地图场景，场景目前支持两种：
  0：表示当前同一个page里面包含VideoView等视频组件的场景（解决会互相覆盖的问题）。
  1：表示不包含，1的渲染效果比0，若不同时在地图页面使用视频组件，建议选1。
  注：iOS平台不支持。

- 如下图，图一为mapScene设置成0时的显示效果。图二为mapScene设置成1时的显示效果。
 ![](../../images/baidumapview_mapScene_0.png)![](../../images/baidumapview_mapScene_1.png)

>###### <span id="mapType"><font color ='#42b983'>**mapType**</font>: 地图类型

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : standard
- 说明 : 地图类型，支持标准地图standard和卫星地图satellite。

- 示例:
   ```javascript

   //标准地图standard
   ui("do_BaiduMapView").mapType = "standard";   
   //卫星地图satellite。
   ui("do_BaiduMapView").mapType = "satellite";  
   //标准地图standard

     ```

如下图，图一为mapType设置成standard时的显示效果。图二为mapType设置成satellite时的显示效果.
 ![](../../images/baidumapview_mapType_standard.png)![](../../images/baidumapview_mapType_satellite.png)

>###### <span id="zoomLevel"><font color ='#42b983'>**zoomLevel**</font>: 地图缩放等级

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 10
- 说明 : 地图缩放等级，可以设置级别为 3-18 ,对应地图比例尺20m - 2000公里，具体对应关系可以参考百度地图开发文档

- 示例:
   ```javascript
   //地图缩放等级10级
   ui("do_BaiduMapView").zoomLevel = 10;   
   //地图缩放等级13级
   ui("do_BaiduMapView").zoomLevel = 13;  

     ```
如下图，图一为zoomLevel设置成10时的显示效果。图二为zoomLevel设置成13时的显示效果。
![](../../images/baidumapview_mapType_standard.png)![](../../images/baidumapview_zoomLevel_13.png)

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id="addMarkers"><font color ='#0092db'>**addMarkers**</font>: 添加一组标记

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **data** |<font color ='#808000'>**object**</font> | 是 | | 将一组经纬度用缩略图在百度地图标记出来,点击缩略图后弹出描述信息,缩略图地址为 data:// source:// 打头的URI格式，不能包含@符号。其中文件格式说明可参考Storage类
- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: true 成功 false 失败
- 说明:参数格式如下：
  ```

[{
      id:标记ID，用户自定义标记唯一ID，是字符串类型,
      latitude:纬度,
      longitude:经度,
      url:缩略图地址,
      info:描述信息,
      popup:是否可点击，是否支持点击弹出信息，为true时支持，为false时点击marks不弹出信息，仅触发touchMarker事件，默认为true,
      textMarker:文字Mark
}]。其中id必须唯一，textMarker为一个JSON对象，包含文字Mark的一些属性，textMarker格式如下：
      textMarker:{
        text: 文本,
        fontColor: 设置字体显示颜色，值格式为：8位16进制字符，前6位是RGB颜色值，后两位是透明度（Alpha），默认值为：000000FF,
        fontSize: 字体大小，默认值为：17,
        fontSize: 设置字体风格包含normal：常规bold：粗体两种风格，默认值为：normal,
        alignX: 支持left(左对齐)，right(右对齐)，center(水平居中对齐)，默认值为：center,
        alignY: 支持top(上对齐)，bottom(下对齐)，center(垂直居中对齐)，默认值为：center ,
        bgColor: 文字背景色，默认值为：FFFFFF00,
        radius: 文字背景圆角，默认值为：0
      }
  ```

- 示例:

  ```javascript
  var do_BaiduMapView = ui("do_BaiduMapView_1");
  do_BaiduMapView.addMarkers([ {
		"id" : "01",    // id为string类型
		"latitude" : "39.915171",
		"longitude" : "116.403808",
		"url" : "source://image/baidumapview/baidumapview_addmarks.png", // 缩略图的图片路径
		"info" : "描述信息1",
		"popup" : true,
		"textMarker" : {
			"text" : "添加的标记1",
			"fontColor" : "FF0000FF",
			"fontStyle" : "bold",
			"fontSize" : 20,
			"alignX" : "center",
			"alignY" : "center",
			"bgColor" : "00FFFFFF",
			"radius" : 0
		}
	} ]);

  ```
  下图为上面示例代码显示效果。
   ![](../../images/baidumapview_addmarks1.png)

[回到顶部](#top)
>##### <span id="addOverlay"><font color ='#0092db'>**addOverlay**</font>: 添加集合图形

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **type** |<font color ='#808000'>**number**</font> | 是 | |支持的类型有，0圆形Circle，1折线:Polyline，2多边形:Polygon，3圆弧:Arc
  **data** |<font color ='#808000'>**object**</font> | 是 | |根据类型传递不同的参数；
  **id** |<font color ='#808000'>**string**</font> | 是 | |要添加的集合图形ID
  **fillColor** |<font color ='#808000'>**string**</font> | 否 | 00000000|只有闭合图形才有填充颜色
  **strokeColor** |<font color ='#808000'>**string**</font> | 否 | 000000FF|
  **width** |<font color ='#808000'>**number**</font> | 否 | 5|
  **isDash** |<font color ='#808000'>**boolean**</font> | 否 | false|线条是否显示为虚线，android只有折线可以设置为虚线
- 返回值类型 : <font color ='#808000'>**无**</font>

- 返回值描述: 无
- 说明: 添加集合图形遮盖物,参数格式如下:

  ```

    圆形:需要中心点坐标(经纬度)和半径(单位:米),圆形的情况只有一个点,代码如下：
    {
    "latitude" : "39.915174",
    "longitude" : "116.403901",
    "radius" : "10000"
    },
    折线和多边形:每一个是一个经纬度点,代码如下：
    [
    {"latitude" : "39.915174","longitude" : "116.403901"},
    {"latitude" : "39.955174","longitude" : "116.403901"},
    {"latitude" : "39.615174","longitude" : "116.603901"},
    {"latitude" : "39.515174","longitude" : "116.553901"},
    {"latitude" : "39.915174","longitude" : "116.403901"},
    ...
    ]
    圆弧:根据指定经纬度生成一段圆弧,指定的经纬度坐标点数组(需传入3个点),每一个是一个经纬度点,代码如下：
    [
    {"latitude":"39.915174","longitude":"116.403901"},
    {"latitude":"39.905174","longitude":"116.002901"},
    {"latitude":"39.855174","longitude":"116.000001"},
    ...
    ]

  ```
- 示例:

  ```javascript
  var do_BaiduMapView = ui("do_BaiduMapView_1");
   // 圆形
  do_BaiduMapView.addOverlay({
		"type" : 0,       
		"data" : {         
			"latitude" : "39.915174",
			"longitude" : "116.403901",
			"radius" : "10000"
		},
		"id" : "0",    // 要添加的集合图形ID
		"fillColor" : "00000088",    // 只有闭合图形才有填充颜色
		"strokeColor" : "FFFFFFFF",    // 外边缘颜色
		"width" : 20,     // 外边缘宽度
		"isDash" : true     // 线条是否显示为虚线，android只有折线可以设置为虚线
	});

//折线
do_BaiduMapView.addOverlay({
		"type" : 1, // 折线
		"data" : [ { // 折线:每一个是一个经纬度点
			"latitude" : "39.916174",
			"longitude" : "116.413911"
		}, {
			"latitude" : "39.517164",
			"longitude" : "116.423921"
		}, {
			"latitude" : "39.915184",
			"longitude" : "116.433911"
		}, {
			"latitude" : "39.917154",
			"longitude" : "116.513921"
		} ],
		"strokeColor" : "FF0000FF",
		"id" : "1", // 要添加的集合图形ID
		"width" : 5,
		"isDash" : false
	});

  //多边形
  do_BaiduMapView.addOverlay({
		"type" : 2, // 多边形
		"data" : [ { // 多边形:每一个是一个经纬度点
			"latitude" : "39.915174",
			"longitude" : "116.403901",
		}, {
			"latitude" : "39.955174",
			"longitude" : "116.403901",
		}, {
			"latitude" : "39.615174",
			"longitude" : "116.603901",
		}, {
			"latitude" : "39.515174",
			"longitude" : "116.553901",
		}, {
			"latitude" : "39.915174",
			"longitude" : "116.403901",
		} ],
		"strokeColor" : "8000FFFF",
		"id" : "2", // 要添加的集合图形ID
		"width" : 2,
		"isDash" : true
	});

  //圆弧
  do_BaiduMapView.addOverlay({
		"type" : 3, // 圆弧
		"data" : [ { // 圆弧:根据指定经纬度生成一段圆弧,指定的经纬度坐标点数组(需传入3个点),每一个是一个经纬度点
			"latitude" : "39.915174",
			"longitude" : "116.403901",
		}, {
			"latitude" : "39.905174",
			"longitude" : "116.002901",
		}, {
			"latitude" : "39.855174",
			"longitude" : "116.000001",
		} ],
		"strokeColor" : "00FFFFFF",
		"id" : "3", // 要添加的集合图形ID
		"width" : 3,
		"isDash" : false
	});

  ```

下图分别为以上示例代码的展示效果。
![](../../images/baidumapview_addOverlay_type0.png)![](../../images/baidumapview_addOverlay_type1.png)
![](../../images/baidumapview_addOverlay_type2.png)![](../../images/baidumapview_addOverlay_type3.png)
[回到顶部](#top)

>##### <span id="getDistance"><font color ='#0092db'>**getDistance**</font>: 获取实际距离

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **startPoint** |<font color ='#808000'>**string**</font> | 是 | |设置起点经纬度，如39.915174,116.403901表示(纬度,经度)
  **endPoint** |<font color ='#808000'>**string**</font> | 是 | |设置终点经纬度，如40.915174,117.403901表示(纬度,经度)
- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 返回坐标点之间距离，单位为米
- 说明: 根据地图上两个点的坐标来获取两点之间实际直线距离
- 示例:

  ```javascript

  var getDistance = do_BaiduMapView.getDistance(({
    "startPoint": (39.915174,116.403901),
    "endPoint": (40.915174,117.403901)
  }))
  deviceone.print(JSON.stringify(getDistance));  //在设计器上logger里面打印返回来的数据

  ```

[回到顶部](#top)

>##### <span id="removeMarker"><font color ='#0092db'>**removeMarker**</font>: 移除一组指定标记

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **ids** |<font color ='#808000'>**object**</font> | 是 | |要移除的标记ID数组
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 移除一组指定标记
- 示例:

  ```javascript
  //ids要和添加标记的自定义标记唯一ID对应上，否则报错
  var removeMarker = do_BaiduMapView.removeMarker(["01"]);

  ```
[回到顶部](#top)

>##### <span id="removeOverlay"><font color ='#0092db'>**removeOverlay**</font>: 移除一组图形集合

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **ids** |<font color ='#808000'>**object**</font> | 是 | |要移除的几何图形ID数组
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 移除一组图形集合
- 示例:

  ```javascript

  //ids要和添加标记的自定义集合图形唯一ID对应上，否则报错

  //移除圆形（上面示例代码中圆形id为"0"）
  var removeOverlay = do_BaiduMapView.removeOverlay(["0"]);

  //移除折线（上面示例代码中折线id为"1"）
  var removeOverlay = do_BaiduMapView.removeOverlay(["1"]);

  //移除多边形（上面示例代码中多边形id为"2"）
  var removeOverlay = do_BaiduMapView.removeOverlay(["2"]);

  //移除弧形（上面示例代码中弧形id为"3"）
  var removeOverlay = do_BaiduMapView.removeOverlay(["3"]);

  //移除圆形，折线（上面示例代码中圆形id为"0",折线id位"3"）
  var removeOverlay = do_BaiduMapView.removeOverlay(["0","3"]);

  ```

[回到顶部](#top)

>##### <span id="setCenter"><font color ='#0092db'>**setCenter**</font>: 设置地图中心点

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **latitude** |<font color ='#808000'>**string**</font> | 是 | 39.915174|设置地图中心点纬度，默认是北京天安门坐标纬度
  **longitude** |<font color ='#808000'>**string**</font> | 是 | 116.403901|设置地图中心点经度，默认是北京天安门坐标经度
- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: true 成功 false 失败
- 说明: 设置地图中心点
- 示例:

  ```javascript

  // 设置地图中心点为抚顺
  var setCenter = do_BaiduMapView.setCenter("41.867335","123.90583");
	deviceone.print(JSON.stringify(setCenter));
	if (setCenter == true) {
		sm("do_Notification").toast("中心点设置成功");
	} else {
		sm("do_Notification").toast("中心点设置失败");
	}

  ```

[回到顶部](#top)

>##### <span id="removeAll"><font color ='#0092db'>**removeAll**</font>: 移除所有标记

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 移除所有标记
- 示例:

  ```javascript

  var removeAll = do_BaiduMapView.removeAll();

  ```

[回到顶部](#top)

  >##### <span id="pauseDownload"><font color ='#0092db'>**pauseDownload**</font>: 暂停下载离线地图

  - 参数:

    名称 | 类型 |必填|默认值|说明
    ---- |-------------  |--------------|--------|------
    **cityID** |<font color ='#808000'>**number**</font> | 是 | |
  - 返回值类型 : <font color ='#808000'>**boolean**</font>
  - 返回值描述: 成功返回true，失败返回false
  - 说明:
  - 示例:

    ```javascript

    do_BaiduMapView.pauseDownload({"cityID":131},function(data){
  		deviceone.print(JSON.stringify(data));  
  	});

    ```

[回到顶部](#top)

>##### <span id="removeDownload"><font color ='#0092db'>**removeDownload**</font>: 移除下载离线地图

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **cityID** |<font color ='#808000'>**number**</font> | 是 | |
- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: 成功返回true，反之返回false
- 说明:
- 示例:

    ```javascript

    do_BaiduMapView.removeDownload({"cityID":131},function(data){
      deviceone.print(JSON.stringify(data));  
    });

    ```
[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <span id="getHotCityList"><font color ='#0092db'>**getHotCityList**</font>: 获得所有热门城市

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: [{'cityID':城市id,'cityName':城市名称,'size':离线包大小，单位为字节}]
- 说明:
- 示例:

  ```javascript
  var getHotCityList = do_BaiduMapView.getHotCityList(function(data){
		if (data) {
			deviceone.print(JSON.stringify(data));
		}
	});

    ```

    ```

  以上代码打印返回的值data为：
  [
    {
        "cityID":131,
        "cityName":"北京市",
        "size":31690530
    },
    {
        "cityID":289,
        "cityName":"上海市",
        "size":35240593
    },
    {
        "cityID":257,
        "cityName":"广州市",
        "size":23512176
    },
    {
        "cityID":315,
        "cityName":"南京市",
        "size":13935505
    },
    {
        "cityID":179,
        "cityName":"杭州市",
        "size":17573485
    },
    {
        "cityID":75,
        "cityName":"成都市",
        "size":19332078
    },
    {
        "cityID":340,
        "cityName":"深圳市",
        "size":14769005
    },
    {
        "cityID":2912,
        "cityName":"香港特别行政区",
        "size":44964625
    },
    {
        "cityID":2911,
        "cityName":"澳门特别行政区",
        "size":20140593
    }
  ]

    ```
[回到顶部](#top)

>##### <span id="poiSearch"><font color ='#0092db'>**poiSearch**</font>: 搜索服务

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **type** |<font color ='#808000'>**number**</font> | 是 | |搜索类型，是一个枚举值。0:城市POI检索;1:在矩形范围内POI检索;2:根据中心点、半径POI检索;
  **keyword** |<font color ='#808000'>**string**</font> | 是 | |搜索的关键字
  **param** |<font color ='#808000'>**object**</font> | 是 | |根据检索类型设置检索参数，当type = 0时，param为{city:''}；当type = 1时，param 为{leftBottom:'39.915174,116.403901(纬度,经度)',rightTop:'39.915174,116.403901(纬度,经度)'}表示矩形区域，左下角和右上角的经纬度坐标点；当type = 2时，param为{location:'39.915174,116.403901(纬度,经度)',radius:''}，其中location为检索的中心点经纬度，radius为周边检索半径，单位为米
  **pageIndex** |<font color ='#808000'>**number**</font> | 否 | 0|
  **pageSize** |<font color ='#808000'>**number**</font> | 否 | 10|
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 搜索结果列表,是一个数组,每一项是一个字典,包括{name:'POI名称',pt:'POI坐标',address:'POI地址',city:'POI所在城市',phone:'POI电话号码'}
- 说明: 根据关键词搜索
- 示例:

  ```javascript

  do_BaiduMapView.poiSearch({
		"type" : 0,
		"keyword" : "北京",
		"param" : {
			city : "北京"
		},
		"pageIndex" : 0,
		"pageSize" : 10
	},function(data){
		deviceone.print(JSON.stringify(data));
	})

  ```
  ```

  以上代码打印返回的值data为：
  [
      {
          "city":"北京市",
          "name":"北京市",
          "pt":"39.910873,116.413677",
          "address":"北京市"
      },
      {
          "city":"北京市",
          "name":"北京南站",
          "pt":"39.873102,116.383974",
          "address":"20路;102路;106路;133路;381路;458路;485路;机场大巴北京南站线;南苑机场大巴公主坟专线;夜17路"
      },
      {
          "city":"北京市",
          "name":"北京南站",
          "pt":"39.870965,116.385169",
          "address":"地铁14号线东段;地铁4号线大兴线"
      },
      {
          "city":"北京市",
          "name":"北京商务会馆",
          "pt":"39.873415,116.365573",
          "address":"北京市南二环右安门外玉林里1号楼(右安门桥西南)"
      },
      {
          "city":"北京市",
          "name":"北京国际饭店",
          "pt":"39.915832,116.435059",
          "address":"北京市东城区建国门内大街9号"
      },
      {
          "city":"北京市",
          "name":"北京北二环高档公寓",
          "pt":"39.957221,116.405287",
          "address":"北京东城区安德路12号"
      },
      {
          "city":"北京市",
          "name":"北京友谊宾馆",
          "pt":"39.971717,116.325891",
          "address":"海淀区中关村南大街1号(四通桥西南角)"
      },
      {
          "city":"北京市",
          "name":"北京银行(房山支行)",
          "pt":"39.748364,116.145404",
          "address":"北京市房山区良乡月华大街3号龙建大厦首层"
      },
      {
          "city":"北京市",
          "name":"北京银行(良乡支行)",
          "pt":"39.729048,116.138520",
          "address":"北京市房山区良乡西潞街道长虹西路71号"
      },
      {
          "city":"北京市",
          "name":"北京北清远帆信息技术有限公司",
          "pt":"39.895708,116.362857",
          "address":"北京市西城区广安门内大街315号it信息大厦b座4层"
      }
  ]
  ```

[回到顶部](#top)

>##### <span id="routePlanSearch"><font color ='#0092db'>**routePlanSearch**</font>: 路线检索

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **type** |<font color ='#808000'>**string**</font> | 是 | |路线检索类型,包括Bus(公交);Ride(骑行);Walk(步行);Drive(驾车)
  **startCityName** |<font color ='#808000'>**string**</font> | 是 | |城市名称
  **endCityName** |<font color ='#808000'>**string**</font> | 是 | |城市名称
  **startCitySite** |<font color ='#808000'>**string**</font> | 是 | |所在城市的地点名称或者开始地点的经纬度例如39.915174,116.403901表示(纬度,经度)
  **endCitySite** |<font color ='#808000'>**string**</font> | 是 | |所在城市的地点名称或者结束地点的经纬度例如39.915174,116.403901表示(纬度,经度)
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 路线检索，检索出的路线会直接显示在地图上，并可点击查看详细信息，当检索城市与地点不在同一城市中，以经纬度为准
- 示例:

  ```javascript

  do_BaiduMapView.routePlanSearch({
		"type" : "Drive",
		"startCityName" : "北京",
		"endCityName" : "北京",
		"startCitySite" : 39.721785+","+117.342488,
		"endCitySite" : 39.160025+","+117.193478
	},function(data){
		deviceone.print("路线检索routePlanSearch方法："+JSON.stringify(data));
	})

  ```

[回到顶部](#top)


>##### <span id="startDownload"><font color ='#0092db'>**startDownload**</font>: 开始下载离线地图

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **cityID** |<font color ='#808000'>**number**</font> | 是 | |
- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: 成功返回true，失败返回false
- 说明: pauseDownload后再次调startDownload可继续下载
- 示例:

  ```javascript

  do_BaiduMapView.startDownload({"cityID":131},function(data){
		deviceone.print(JSON.stringify(data));  
	});

  ```
下图为以上示例代码的展示效果。


[回到顶部](#top)

#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id="download"><font color ='#e96900'>**download**</font>: 下载离线地图触发的事件

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {'cityID':城市id,'cityName':城市名称,'ratio':下载进度（0~100）100表示下载完成}
- 说明: 下载离线地图触发的事件
- 示例:

  ```javascript

  do_BaiduMapView.on("download",function(data){
  	deviceone.print("download事件："+JSON.stringify(data));  
  });

  ```

[回到顶部](#top)

>###### <span id="regionChange"><font color ='#e96900'>**regionChange**</font>: 地图区域改变完成后会触发，返回地图区域的中心点坐标

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {latitude:'', longitude:''}
- 说明: 地图区域改变完成后会触发，返回地图区域的中心点坐标
- 示例:

  ```javascript

  do_BaiduMapView.on("regionChange",function(data){
	if (data) {
		deviceone.print("regionChange事件："+JSON.stringify(data));  
	}
});

  ```

  ```

  以上代码打印返回的值data为：
  {
      "cityID":131,
      "ratio":2,
      "cityName":"北京市"
  }
  ```

[回到顶部](#top)

>###### <span id="touchMap"><font color ='#e96900'>**touchMap**</font>: 点击地图时触发

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回当前点击的位置坐标{"latitude":"纬度","longitude":"经度"}
- 说明: 点击地图时触发
- 示例:

  ```javascript

  do_BaiduMapView.on("touchMap",function(data){
  	if (data) {
  		deviceone.print("touchMap事件："+JSON.stringify(data));  
  	}
  });

  ```

  ```

  以上代码打印返回的值data为：
  //获取的是我随机点击地图某一位置的经纬度
  {
    "longitude":"116.201987",
    "latitude":"39.655533"
  }

  ```
[回到顶部](#top)

>###### <span id="touchMarker"><font color ='#e96900'>**touchMarker**</font>: 点击标记时触发，iOS平台只有第一次点击mark会触发该事件，之后需要点击弹出的缩略图触发

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述:
- 说明: 点击标记时触发，iOS平台只有第一次点击mark会触发该事件，之后需要点击弹出的缩略图触发
- 示例:

  ```javascript

  do_BaiduMapView.on("touchMarker",function(data){
	if (data) {
		deviceone.print("touchMarker事件："+JSON.stringify(data));  
	}
});

  ```

  ```

  以上代码打印返回的值data为（点击上述addMarkers方法示例代码实现的标记，触发touchMarker事件返回的data）：
  [ {
		"id" : "01",    // id为string类型
		"latitude" : "39.915171",
		"longitude" : "116.403808",
		"url" : "source://image/baidumapview/baidumapview_addmarks.png", // 缩略图的图片路径
		"info" : "描述信息1",
		"popup" : true,
		"textMarker" : {
			"text" : "添加的标记1",
			"fontColor" : "FF0000FF",
			"fontStyle" : "bold",
			"fontSize" : 20,
			"alignX" : "center",
			"alignY" : "center",
			"bgColor" : "00FFFFFF",
			"radius" : 0
		}
	} ])

  ```

#### <font color ='#40A977'>**5.**</font> 常见问题
  - 1.do_BaiduMapView-iOSaddMark时，add多个initpopupvisibal为true，popup为true的地标，只能显示一个，这个原生的，不存在多个都显示

#### <font color ='#40A977'>**6.**</font> 基本配置
  - 1.使用百度地图时需要给组件配置对应的key,具体key值怎么获取参见[示例文档](/UI组件API/sections/百度定位相关配置/)
[回到顶部](#top)
