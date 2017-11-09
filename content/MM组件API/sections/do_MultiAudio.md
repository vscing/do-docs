---
title: do_MultiAudio 组件
---

### do_MultiAudio 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/MM/do_MultiAudio)
 多音频播放，能支持播放mp3、amr（iOS平台不支持）、aac格式的本地和网络音频

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#0092db'>同步方法</font>  |[play](#play)| 开始播放
<font color ='#0092db'>同步方法</font>  |[pause](#pause)| 暂停播放
<font color ='#0092db'>同步方法</font>  |[resume](#resume)| 继续播放
<font color ='#0092db'>同步方法</font>  |[stop](#stop)| 停止播放
<font color ='#e96900'>事件</font>  |[playFinished](#playFinished)| 音频播放结束后触发
<font color ='#e96900'>事件</font>  |[error](#error)| 音频播放错误时触发
<font color ='#e96900'>事件</font>  |[playProgress](#playProgress)|

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
  do_MultiAudio.play({path:"source://view/MM/do_MultiAudio/2.mp3", point:0});

  ```

[回到顶部](#top)

>##### <span id=pause><font color ='#0092db'>**pause**</font></span>: 暂停播放

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 返回暂停时播放到第几毫秒
- 说明:
- 示例:

  ```javascript
  var time = do_MultiAudio.pause();
	deviceone.print(time,"播放时间")

  ```

[回到顶部](#top)

>##### <span id=resume><font color ='#0092db'>**resume**</font></span>: 继续播放

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明:
- 示例:

  ```javascript
  var time = do_MultiAudio.resume();

  ```

[回到顶部](#top)

>##### <span id=stop><font color ='#0092db'>**stop**</font></span>: 停止播放

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明:
- 示例:

  ```javascript
  var time = do_MultiAudio.stop();

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=playFinished><font color ='#e96900'>**playFinished**</font></span>: 音频播放结束后触发

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述:
- 说明: 音频播放结束后触发
- 示例:

  ```javascript
  do_MultiAudio.on("playFinished",function(data){
	   deviceone.print("播放结束")
  })
  ```

[回到顶部](#top)

>###### <span id=error><font color ='#e96900'>**error**</font></span>: 音频播放错误时触发

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述:
- 说明: 音频播放错误时触发
- 示例:

  ```javascript
  do_MultiAudio.on("error",function(data){
	   deviceone.print("错误")
  })
  ```

[回到顶部](#top)

>###### <span id=playProgress><font color ='#e96900'>**playProgress**</font></span>:

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回音频总时间和当前播放时间{currentTime,totalTime}，单位为毫秒
- 说明:
- 示例:

  ```javascript
  do_MultiAudio.on("playProgress",function(data){
	   deviceone.print(JSON.stringify(data),"进度信息")
  })

  ```

[回到顶部](#top)
