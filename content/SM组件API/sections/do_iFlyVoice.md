---
title: do_iFlyVoice 组件
---

### do_iFlyVoice 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_iFlyVoice)
 集成科大讯飞提供的讯飞语音组件，支持语音识别和语音合成功能，语音识别主要是把“你说的话”转换成“文本”，语音合成主要是把“文本”读出来

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#0092db'>同步方法</font>  |[speak](#speak)| 开始播放
<font color ='#0092db'>同步方法</font>  |[pause](#pause)| 暂停播放
<font color ='#0092db'>同步方法</font>  |[resume](#resume)| 继续播放
<font color ='#0092db'>同步方法</font>  |[stop](#stop)| 停止播放
<font color ='#0092db'>异步方法</font>  |[open](#open)| 打开语音识别功能
<font color ='#e96900'>事件</font>  |[begin](#begin)| 合成完成，开始播放时触发
<font color ='#e96900'>事件</font>  |[finished](#finished)| 播放完成或播放错误时触发

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=speak><font color ='#0092db'>**speak**</font></span>: 开始播放

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **text** |<font color ='#808000'>**string**</font> | 是 | |要读出的文本内容
  **role** |<font color ='#808000'>**string**</font> | 否 | xiaoyan|需要朗读的角色,值列表见http://bbs.deviceone.net/forum.php?mod=viewthread&tid=32&extra=
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 开始合成，合成完成自动播放
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=pause><font color ='#0092db'>**pause**</font></span>: 暂停播放

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
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

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <span id=open><font color ='#0092db'>**open**</font></span>: 打开语音识别功能

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: result：语音识别过后的文本结果；spell：语音识别过后的拼音结果；errorMsg：语音识别异常信息
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=begin><font color ='#e96900'>**begin**</font></span>: 合成完成，开始播放时触发

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 
- 说明: 合成完成，开始播放时触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <span id=finished><font color ='#e96900'>**finished**</font></span>: 播放完成或播放错误时触发

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 
- 说明: 播放完成或播放错误时触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


