---
title: do_iFlyVoice 组件
---

### do_iFlyVoice 组件

 支持平台: iOS7.0,Android4.0
 集成科大讯飞提供的讯飞语音组件，支持语音识别和语音合成功能，语音识别主要是把“你说的话”转换成“文本”，语音合成主要是把“文本”读出来

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**speak**</font>: 开始播放

- 参数:

  名称 | 类型 |是否必填|缺省值|说明
  ---- |-------------  |--------------|--------|------
  **text** |<font color ='#808000'>**string**</font> |  | 是|要读出的文本内容
  **role** |<font color ='#808000'>**string**</font> | xiaoyan | 否|需要朗读的角色,值列表见http://bbs.deviceone.net/forum.php?mod=viewthread&tid=32&extra=
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 开始合成，合成完成自动播放
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**pause**</font>: 暂停播放

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
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

>##### <font color ='#0092db'>**open**</font>: 打开语音识别功能

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

>###### <font color ='#e96900'>**begin**</font>: 合成完成，开始播放时触发

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 
- 说明: 合成完成，开始播放时触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**finished**</font>: 播放完成或播放错误时触发

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 
- 说明: 播放完成或播放错误时触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


