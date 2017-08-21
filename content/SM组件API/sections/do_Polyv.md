---
title: do_Polyv 组件
---

### do_Polyv 组件

* 支持平台: iOS7.0,Android4.0
保利威视提供网络播放、本地播放、视频下载、视频上传、视频拍摄等功能，不支持windows平台

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**play**</font>: 播放视频

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **id** |<font color ='#808000'>**string**</font> |  | 是||
  **bitRate** |<font color ='#808000'>**number**</font> | 0 | 否|0|支持：0是自动根据当前网络环境适应，1表示流畅，2表示高清，3表示超清，默认值
  **point** |<font color ='#808000'>**number**</font> |  | 否||从视频中的某一点开始播放，毫秒值
  **isFull** |<font color ='#808000'>**Boolean**</font> | false | 否|false|iOS平台只支持全屏播放
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 支持全屏和小窗口播放
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**getState**</font>: 获取视频状态

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {state:0},state表示视频的当前状态，0:表示停止，1：表示正在播放
- 说明: 获取当前视频状态
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**stop**</font>: 停止播放

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**getCurrentTime**</font>: 获取当前视频播放时间

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 获取当前视频播放时间，毫秒值
- 说明: 获取当前视频播放时间
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**download**</font>: 下载视频

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **id** |<font color ='#808000'>**string**</font> |  | 是||
  **bitRate** |<font color ='#808000'>**number**</font> |  | 是||支持：1表示流畅，2表示高清，3表示超清
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 支持不同码率视频的下载
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <font color ='#0092db'>**getList**</font>: 获取视频列表

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **pageIndex** |<font color ='#808000'>**number**</font> | 0 | 否|0|
  **pageSize** |<font color ='#808000'>**number**</font> | 10 | 否|10|
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回结果列表,是一个数组,每一项是一个字典,包括视频的基本信息：{id:'唯一标识',title:'标题',duration:'时长',imageUrl:'预览图片地址',fileSize:'文件大小(字节)','bitRates':'支持的码率'}
- 说明: 获取视频列表，支持分页
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**getInfo**</font>: 获取视频信息

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **id** |<font color ='#808000'>**string**</font> |  | 是||
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {id:'唯一标识',title:'标题',duration:'时长',imageUrl:'预览图片地址',fileSize:'文件大小(字节)','bitRates':'支持的码率'}
- 说明: 根据视频唯一标识获取视频信息
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件

>###### <font color ='#e96900'>**downloadProgress**</font>: 下载进度事件

- 返回值类型 : <font color ='#808000'>**Node**</font>
- 返回值描述: 返回当前下载进度百分比{progress:20}表示20%
- 说明: 下载进度事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**success**</font>: 请求成功事件

- 返回值类型 : <font color ='#808000'>**Node**</font>
- 返回值描述: 返回值{type:0}，type表示事件类型，0表示下载事件
- 说明: 请求成功事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**fail**</font>: 请求出错事件

- 返回值类型 : <font color ='#808000'>**Node**</font>
- 返回值描述: 返回值{type:0}，type表示事件类型，0表示下载事件
- 说明: 请求出错事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


