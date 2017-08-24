---
title: do_BaiduLocation 组件
---

### do_BaiduLocation 组件

 支持平台: iOS7.0,Android4.0
 利用设备当前的GPS信息（GPS定位），基站信息（基站定位）和Wi-Fi信息（Wi-Fi定位）完成定位，根据设备当前的实际情况（如是否开启GPS，是否连接网络，是否扫描到Wi-Fi信息等）进行定位

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**getDistance**</font>: 获取实际距离

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **startPoint** |<font color ='#808000'>**string**</font> | 是 | |设置起点经纬度，如39.915174,116.403901表示(纬度,经度)
  **endPoint** |<font color ='#808000'>**string**</font> | 是 | |设置终点经纬度，如40.915174,117.403901表示(纬度,经度)
- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 返回坐标点之间距离，单位为米
- 说明: 根据上两个点的坐标来获取两点之间实际直线距离
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**start**</font>: 开启定位

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **model** |<font color ='#808000'>**string**</font> | 否 | high|high:高精度定位模式（会同时使用Wi-Fi和基站和GPS定位，优先返回最高精度的定位结果）；low：低精度（不会使用GPS，只会使用Wi-Fi和基站定位）；middle: 中精度（不需要连接网络，只使用GPS进行定位，这种模式下不支持室内环境的定位）
  **isLoop** |<font color ='#808000'>**boolean**</font> | 否 | false|为false时只获取一次位置，触发一次result事件。 当值为true时,程序会不断获取新的位置（android是依据时间间隔，根据精度参数的不同，每隔30s返回1~2次结果；iOS是依据距离间隔，根据精度参数的不同，每超过10m/100m/1000m时返回结果），触发result事件
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 开启定位
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**stop**</font>: 停止定位

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 停止定位
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**startScan**</font>: 开启定位扫描

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **model** |<font color ='#808000'>**string**</font> | 否 | high|high:高精度定位模式（会同时使用Wi-Fi和基站和GPS定位，优先返回最高精度的定位结果）；low：低精度（不会使用GPS，只会使用Wi-Fi和基站定位）；middle: 中精度（不需要连接网络，只使用GPS进行定位，这种模式下不支持室内环境的定位）
  **span** |<font color ='#808000'>**number**</font> | 否 | 1000|定位扫描间隔，单位为毫秒，最低为1000毫秒，扫描结果通过result事件返回；iOS平台该参数无效，因机制不同，iOS平台移动距离有变化时返回结果
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 开启定位扫描
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**stopScan**</font>: 停止定位扫描

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 停止定位扫描
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <font color ='#0092db'>**locate**</font>: 定位

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **model** |<font color ='#808000'>**string**</font> | 否 | high|high:高精度定位模式（会同时使用Wi-Fi和基站和GPS定位，优先返回最高精度的定位结果）；low：低精度（不会使用GPS，只会使用Wi-Fi和基站定位）；middle: 中精度（不需要连接网络，只使用GPS进行定位，这种模式下不支持室内环境的定位）
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {latitude:'纬度​'，longitude:'经度', address:'北京市海淀区'}
- 说明: 定位一次
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**geoCode**</font>: 正向地图编码

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **city** |<font color ='#808000'>**string**</font> | 是 | |
  **address** |<font color ='#808000'>**string**</font> | 是 | |
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {latitude:'纬度​'，longitude:'经度'}
- 说明: 实现将地址信息转换为经纬度坐标点的过程
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**reverseGeoCode**</font>: 反向地图编码

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **latitude** |<font color ='#808000'>**string**</font> | 是 | |
  **longitude** |<font color ='#808000'>**string**</font> | 是 | |
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {address:'北京市海淀区上地9街9号',province:'省份名称',city:'城市名称',district:'区县名称',streetName:'街道名称',streetNumber:'街道号码',pois:'兴趣点'}，其中pois为[{'id':'poi id','name':'poi名称','city':'poi所在城市','isPano':'poi点附近是否有街景，可使用uid检索全景组件的全景数据','location':'poi坐标，如：{'latitude':'纬度','longitude':'经度'}','address':'poi地址信息'}]
- 说明: 实现将经纬度坐标点转换为地址信息的过程。
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件

>###### <font color ='#e96900'>**result**</font>: 接收到定位/更新定位时候触发

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {latitude:'纬度​'，longitude:'经度', address:'北京市海淀区'}
- 说明: 接收到定位/更新定位时候触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


