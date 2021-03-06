---
title: do_Audio 组件
---

### do_Audio 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_Audio)
 播放音频，能支持播放mp3、amr（iOS 4.0系统后不支持）、aac格式的本地和网络音频，录制音频可支持mp3、amr、aac格式输出

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#0092db'>同步方法</font>  |[play](#play)| 开始播放
<font color ='#0092db'>同步方法</font>  |[pause](#pause)| 暂停播放
<font color ='#0092db'>同步方法</font>  |[resume](#resume)| 继续播放
<font color ='#0092db'>同步方法</font>  |[stop](#stop)| 停止播放
<font color ='#0092db'>同步方法</font>  |[startRecord](#startRecord)| 开始录音
<font color ='#0092db'>同步方法</font>  |[stopRecord](#stopRecord)| 结束录音
<font color ='#0092db'>异步方法</font>  |[stopRecordAsync](#stopRecordAsync)| 结束录音
<font color ='#0092db'>异步方法</font>  |[playAsync](#playAsync)| 开始播放
<font color ='#e96900'>事件</font>  |[playFinished](#playFinished)| 音频播放结束后触发
<font color ='#e96900'>事件</font>  |[recordFinished](#recordFinished)| 录音结束后触发
<font color ='#e96900'>事件</font>  |[error](#error)| 音频播放、录音错误时触发
<font color ='#e96900'>事件</font>  |[playProgress](#playProgress)| 
<font color ='#e96900'>事件</font>  |[recordProgress](#recordProgress)| 
<font color ='#e96900'>事件</font>  |[recordVolume](#recordVolume)| 录音音量变化事件

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=play><font color ='#0092db'>**play**</font></span>: 开始播放

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **path** |<font color ='#808000'>**string**</font> | 是 | |支持data://、source://和网络链接
  **point** |<font color ='#808000'>**number**</font> | 否 | |从最开始的第几毫秒
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=pause><font color ='#0092db'>**pause**</font></span>: 暂停播放

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 返回暂停时播放到第几毫秒
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=resume><font color ='#0092db'>**resume**</font></span>: 继续播放

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=stop><font color ='#0092db'>**stop**</font></span>: 停止播放

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=startRecord><font color ='#0092db'>**startRecord**</font></span>: 开始录音

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **path** |<font color ='#808000'>**string**</font> | 是 | |要保存的录音文件路径，支持数据区data://，指定到目录
  **type** |<font color ='#808000'>**string**</font> | 否 | mp3|选择录音输出的格式，支持mp3、amr、aac格式
  **quality** |<font color ='#808000'>**string**</font> | 否 | normal|选择录音输出的质量，支持high、normal、low
  **limit** |<font color ='#808000'>**number**</font> | 否 | -1|录音的时长限制，以毫秒为单位，-1时表示不限制录音时长
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=stopRecord><font color ='#0092db'>**stopRecord**</font></span>: 结束录音

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回录音文件保存的目录及文件名
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <span id=stopRecordAsync><font color ='#0092db'>**stopRecordAsync**</font></span>: 结束录音

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=playAsync><font color ='#0092db'>**playAsync**</font></span>: 开始播放

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **path** |<font color ='#808000'>**string**</font> | 是 | |支持data://、source://和网络链接
  **point** |<font color ='#808000'>**number**</font> | 否 | |从最开始的第几毫秒
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 不可与play方法同时使用，播放网络音频时建议使用该方法，避免卡顿
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=playFinished><font color ='#e96900'>**playFinished**</font></span>: 音频播放结束后触发

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 
- 说明: 音频播放结束后触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <span id=recordFinished><font color ='#e96900'>**recordFinished**</font></span>: 录音结束后触发

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {“path”:“返回录音文件保存的路径”,“time”:“本次录音时长，单位为毫秒”,“size”:“返回的录音文件大小，单位为字节”}
- 说明: 录音结束后触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <span id=error><font color ='#e96900'>**error**</font></span>: 音频播放、录音错误时触发

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 
- 说明: 音频播放、录音错误时触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <span id=playProgress><font color ='#e96900'>**playProgress**</font></span>: 

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回音频总时间和当前播放时间{currentTime,totalTime}
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <span id=recordProgress><font color ='#e96900'>**recordProgress**</font></span>: 

- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回录音总时间totalTime
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <span id=recordVolume><font color ='#e96900'>**recordVolume**</font></span>: 录音音量变化事件

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {“volume”:“实时音量大小”}；Windows平台不支持
- 说明: 录音音量变化事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


