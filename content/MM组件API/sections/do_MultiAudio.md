---
title: do_MultiAudio 组件
---

### do_MultiAudio 组件

* 支持平台: iOS7.0,Android4.0
多音频播放，能支持播放mp3、amr（iOS平台不支持）、aac格式的本地和网络音频

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

#### <font color ='#40A977'>**3.**</font> 异步方法


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

>###### <font color ='#e96900'>**error**</font>: 音频播放错误时触发

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 
- 说明: 音频播放错误时触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**playProgress**</font>: 

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回音频总时间和当前播放时间{currentTime,totalTime}，单位为毫秒
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


