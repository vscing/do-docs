---
title: M0011_TXLiveView 组件
---

### M0011_TXLiveView 组件

 支持平台: iOS,Android 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/M0011_TXLiveView)
 详细文档请见https://www.qcloud.com/document/product/267/7977

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#0092db'>同步方法</font>  |[startPush](#startPush)| 开始直播(主播)
<font color ='#0092db'>同步方法</font>  |[startPlay](#startPlay)| 观看直播(观众)
<font color ='#0092db'>同步方法</font>  |[stop](#stop)| 停止推流
<font color ='#0092db'>同步方法</font>  |[pause](#pause)| 暂停推流
<font color ='#0092db'>同步方法</font>  |[resume](#resume)| 恢复推流
<font color ='#0092db'>同步方法</font>  |[switchCamera](#switchCamera)| 切换摄像头
<font color ='#0092db'>同步方法</font>  |[setBeauty](#setBeauty)| 设置美颜美白
<font color ='#0092db'>同步方法</font>  |[toggleTorch](#toggleTorch)| 闪光灯
<font color ='#0092db'>同步方法</font>  |[setMute](#setMute)| 设置是否静音

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=startPush><font color ='#0092db'>**startPush**</font></span>: 开始直播(主播)

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **rtmpURL** |<font color ='#808000'>**string**</font> | 是 | |腾讯云的推流地址
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 启动推流
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=startPlay><font color ='#0092db'>**startPlay**</font></span>: 观看直播(观众)

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **url** |<font color ='#808000'>**string**</font> | 是 | |腾讯云的拉流地址
  **videoType** |<font color ='#808000'>**number**</font> | 是 | |0:RTMP直播;1:FLV直播,必须和url的类型对应
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 启动拉流
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=stop><font color ='#0092db'>**stop**</font></span>: 停止推流

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **liveType** |<font color ='#808000'>**number**</font> | 是 | |0:停止推流;1:停止拉流
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=pause><font color ='#0092db'>**pause**</font></span>: 暂停推流

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **liveType** |<font color ='#808000'>**number**</font> | 是 | |0:暂停推流;1:暂停拉流
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=resume><font color ='#0092db'>**resume**</font></span>: 恢复推流

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **liveType** |<font color ='#808000'>**number**</font> | 是 | |0:恢复推流;1:恢复拉流
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=switchCamera><font color ='#0092db'>**switchCamera**</font></span>: 切换摄像头

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 仅支持主播使用
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=setBeauty><font color ='#0092db'>**setBeauty**</font></span>: 设置美颜美白

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **beautyLevel** |<font color ='#808000'>**number**</font> | 否 | 0|美颜级别取值范围 0 ~ 9； 0 表示关闭 1 ~ 9值越大 效果越明显
  **whiteningLevel** |<font color ='#808000'>**number**</font> | 否 | 0|美白级别取值范围 0 ~ 3； 0 表示关闭 1 ~ 3值越大 效果越明显
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 仅支持主播使用
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=toggleTorch><font color ='#0092db'>**toggleTorch**</font></span>: 闪光灯

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **enable** |<font color ='#808000'>**boolean**</font> | 否 | false|是否开启闪光灯
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 仅支持主播
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=setMute><font color ='#0092db'>**setMute**</font></span>: 设置是否静音

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **enable** |<font color ='#808000'>**boolean**</font> | 否 | false|是否静音
  **liveType** |<font color ='#808000'>**number**</font> | 是 | |0:设置是否静音(推流);1:设置是否静音（拉流）
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件


