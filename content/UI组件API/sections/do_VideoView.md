---
title: do_VideoView 组件
---

### do_VideoView 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_VideoView)
 一个简单的播放视频的UI组件，能支持播放本地和网络视频，可支持mp4格式，可以通过点击全屏按钮切换到全屏播放

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#42b983'>属性</font>  |[path](#path)| 播放文件源路径
<font color ='#0092db'>同步方法</font>  |[play](#play)| 开始播放
<font color ='#0092db'>同步方法</font>  |[pause](#pause)| 暂停播放
<font color ='#0092db'>同步方法</font>  |[resume](#resume)| 继续播放
<font color ='#0092db'>同步方法</font>  |[stop](#stop)| 停止播放
<font color ='#0092db'>同步方法</font>  |[isPlaying](#isPlaying)| 当前视频是否正在播放
<font color ='#0092db'>同步方法</font>  |[getCurrentPosition](#getCurrentPosition)| 视频当前播放的时间
<font color ='#0092db'>同步方法</font>  |[expand](#expand)| 全屏播放
<font color ='#0092db'>同步方法</font>  |[setControlVisible](#setControlVisible)| 设置控制按钮是否显示
<font color ='#0092db'>异步方法</font>  |[getFrameAsImage](#getFrameAsImage)| 保存为图片
<font color ='#0092db'>异步方法</font>  |[getFrameAsBitmap](#getFrameAsBitmap)| 保存为Bitmap
<font color ='#e96900'>事件</font>  |[finished](#finished)| 视频播放完后触发
<font color ='#e96900'>事件</font>  |[error](#error)| 视频播放异常时触发

#### <font color ='#40A977'>**1.**</font> 属性

>###### <span id=path><font color ='#42b983'>**path**</font></span>: 播放文件源路径

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 :
- 说明 : 支持initdata://、data://、source://和网络地址

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=play><font color ='#0092db'>**play**</font></span>: 开始播放

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **point** |<font color ='#808000'>**number**</font> | 否 | |从视频中的某一点开始播放，毫秒值
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 开始播放视频,默认从0开始播放
- 示例:

  ```javascript
  do_VideoView.play({point:100})
  ```

[回到顶部](#top)

>##### <span id=pause><font color ='#0092db'>**pause**</font></span>: 暂停播放

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 返回当前视频暂停时的位置，毫秒值
- 说明:
- 示例:

  ```javascript
  var point = do_VideoView.pause()
  deviceone.print(point,"暂停时间")
  ```

[回到顶部](#top)

>##### <span id=resume><font color ='#0092db'>**resume**</font></span>: 继续播放

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明:  
- 示例:

  ```javascript
  do_VideoView.resume()

  ```

[回到顶部](#top)

>##### <span id=stop><font color ='#0092db'>**stop**</font></span>: 停止播放

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明:
- 示例:

  ```javascript
  do_VideoView.stop()

  ```

[回到顶部](#top)

>##### <span id=isPlaying><font color ='#0092db'>**isPlaying**</font></span>: 当前视频是否正在播放

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: true为正在播放，false 为暂停播放、停止或未开始状态
- 说明: 判断当前视频为播放状态还是暂停状态
- 示例:

  ```javascript
  var data = do_VideoView.isPlaying();
  deviceone.print(data,"当前视频状态")
  ```

[回到顶部](#top)

>##### <span id=getCurrentPosition><font color ='#0092db'>**getCurrentPosition**</font></span>: 视频当前播放的时间

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回当前播放的时间，单位为毫秒
- 说明:
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=expand><font color ='#0092db'>**expand**</font></span>: 全屏播放

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **isFullScreen** |<font color ='#808000'>**Boolean**</font> | 否 | false|为false是表示退出全屏，小窗口播放，若已为小窗口播放则没有变化；为true是表示转为全屏播放，若已为全屏播放则没有变化
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明:
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=setControlVisible><font color ='#0092db'>**setControlVisible**</font></span>: 设置控制按钮是否显示

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **visible** |<font color ='#808000'>**boolean**</font> | 否 | true|
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 控制视频上的按钮是否显示
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <span id=getFrameAsImage><font color ='#0092db'>**getFrameAsImage**</font></span>: 保存为图片

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **time** |<font color ='#808000'>**number**</font> | 否 | |默认取第一帧截图
  **format** |<font color ='#808000'>**string**</font> | 否 | JPEG|支持两种格式：PNG，JPEG
  **quality** |<font color ='#808000'>**number**</font> | 否 | 100|图片的压缩质量，支持 1-100，windows平台不支持
  **outPath** |<font color ='#808000'>**string**</font> | 否 | |保存的图片路径支持data://目录，如果为空，缺省返回唯一图片路径，会另存到data://temp/do_VideoView/目录下
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回当前保存的图片路径，为空时表示保存失败
- 说明: 将获取的那一帧保存为一个图片,暂不支持网络视频截取
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=getFrameAsBitmap><font color ='#0092db'>**getFrameAsBitmap**</font></span>: 保存为Bitmap

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **bitmap** |<font color ='#808000'>**string**</font> | 是 | |
  **time** |<font color ='#808000'>**number**</font> | 否 | |默认取第一帧截图
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 将获取的那一帧保存为一个Btimap,暂不支持网络视频截取
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=finished><font color ='#e96900'>**finished**</font></span>: 视频播放完后触发

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述:
- 说明: 视频播放完后触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <span id=error><font color ='#e96900'>**error**</font></span>: 视频播放异常时触发

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述:
- 说明: 视频播放异常时触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)
