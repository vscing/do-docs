---
title: do_VideoView 组件
---

### do_VideoView 组件

 支持平台: iOS7.0,Android4.0
 一个简单的播放视频的UI组件，能支持播放本地和网络视频，可支持mp4格式，可以通过点击全屏按钮切换到全屏播放

#### <font color ='#40A977'>**1.**</font> 属性

>###### <font color ='#42b983'>**path**</font>: 播放文件源路径

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 : 支持initdata://、data://、source://和网络地址

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**play**</font>: 开始播放

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **point** |<font color ='#808000'>**number**</font> |  | 否||从视频中的某一点开始播放，毫秒值
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**pause**</font>: 暂停播放

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 返回当前视频暂停时的位置，毫秒值
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**resume**</font>: 继续播放

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
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

>##### <font color ='#0092db'>**isPlaying**</font>: 当前视频是否正在播放

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: true为正在播放，false 为暂停播放、停止或未开始状态
- 说明: 判断当前视频为播放状态还是暂停状态
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**getCurrentPosition**</font>: 视频当前播放的时间

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回当前播放的时间，单位为毫秒
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**expand**</font>: 全屏播放

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **isFullScreen** |<font color ='#808000'>**Boolean**</font> | false | 否|false|为false是表示退出全屏，小窗口播放，若已为小窗口播放则没有变化；为true是表示转为全屏播放，若已为全屏播放则没有变化
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**setControlVisible**</font>: 设置控制按钮是否显示

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **visible** |<font color ='#808000'>**boolean**</font> | true | 否|true|
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 控制视频上的按钮是否显示
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <font color ='#0092db'>**getFrameAsImage**</font>: 保存为图片

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **time** |<font color ='#808000'>**number**</font> |  | 否||默认取第一帧截图
  **format** |<font color ='#808000'>**string**</font> | JPEG | 否|JPEG|支持两种格式：PNG，JPEG
  **quality** |<font color ='#808000'>**number**</font> | 100 | 否|100|图片的压缩质量，支持 1-100，windows平台不支持
  **outPath** |<font color ='#808000'>**string**</font> |  | 否||保存的图片路径支持data://目录，如果为空，缺省返回唯一图片路径，会另存到data://temp/do_VideoView/目录下
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回当前保存的图片路径，为空时表示保存失败
- 说明: 将获取的那一帧保存为一个图片,暂不支持网络视频截取
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**getFrameAsBitmap**</font>: 保存为Bitmap

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **bitmap** |<font color ='#808000'>**string**</font> |  | 是||
  **time** |<font color ='#808000'>**number**</font> |  | 否||默认取第一帧截图
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 将获取的那一帧保存为一个Btimap,暂不支持网络视频截取
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件

>###### <font color ='#e96900'>**finished**</font>: 视频播放完后触发

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 
- 说明: 视频播放完后触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**error**</font>: 视频播放异常时触发

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 
- 说明: 视频播放异常时触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


