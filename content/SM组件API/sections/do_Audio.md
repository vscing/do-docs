---
title: do_Audio 组件
---

### do_Audio 组件

* 支持平台: iOS7.0,Android4.0
播放音频，能支持播放mp3、amr（iOS 4.0系统后不支持）、aac格式的本地和网络音频，录制音频可支持mp3、amr、aac格式输出

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**play**</font>: 开始播放

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **path** |<font color ='#808000'>**string**</font> |  | 是||支持data://、source://和网络链接
  **point** |<font color ='#808000'>**number**</font> |  | 否||从最开始的第几毫秒
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
- 返回值描述: 返回暂停时播放到第几毫秒
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

>##### <font color ='#0092db'>**startRecord**</font>: 开始录音

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **path** |<font color ='#808000'>**string**</font> |  | 是||要保存的录音文件路径，支持数据区data://，指定到目录
  **type** |<font color ='#808000'>**string**</font> | mp3 | 否|mp3|选择录音输出的格式，支持mp3、amr、aac格式
  **quality** |<font color ='#808000'>**string**</font> | normal | 否|normal|选择录音输出的质量，支持high、normal、low
  **limit** |<font color ='#808000'>**number**</font> | -1 | 否|-1|录音的时长限制，以毫秒为单位，-1时表示不限制录音时长
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**stopRecord**</font>: 结束录音

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

>##### <font color ='#0092db'>**stopRecordAsync**</font>: 结束录音

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**playAsync**</font>: 开始播放

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **path** |<font color ='#808000'>**string**</font> |  | 是||支持data://、source://和网络链接
  **point** |<font color ='#808000'>**number**</font> |  | 否||从最开始的第几毫秒
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 不可与play方法同时使用，播放网络音频时建议使用该方法，避免卡顿
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件

>###### <font color ='#e96900'>**playFinished**</font>: 音频播放结束后触发

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 
- 说明: 音频播放结束后触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**recordFinished**</font>: 录音结束后触发

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {“path”:“返回录音文件保存的路径”,“time”:“本次录音时长，单位为毫秒”,“size”:“返回的录音文件大小，单位为字节”}
- 说明: 录音结束后触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**error**</font>: 音频播放、录音错误时触发

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 
- 说明: 音频播放、录音错误时触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**playProgress**</font>: 

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回音频总时间和当前播放时间{currentTime,totalTime}
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**recordProgress**</font>: 

- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回录音总时间totalTime
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**recordVolume**</font>: 录音音量变化事件

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {“volume”:“实时音量大小”}；Windows平台不支持
- 说明: 录音音量变化事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


