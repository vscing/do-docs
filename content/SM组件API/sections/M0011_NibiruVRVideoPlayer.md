---
title: M0011_NibiruVRVideoPlayer 组件
---

### M0011_NibiruVRVideoPlayer 组件

 支持平台: iOS,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/M0011_NibiruVRVideoPlayer)
 播放支持8个场景模式，2DNormal 2D180 2D360 2DSphere 3DNormal 3D180 3D360 3DSphere

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#0092db'>同步方法</font>  |[pause](#pause)| 暂停播放
<font color ='#0092db'>同步方法</font>  |[play](#play)| 播放视频
<font color ='#0092db'>同步方法</font>  |[resume](#resume)| 继续播放
<font color ='#0092db'>同步方法</font>  |[stop](#stop)| 停止播放
<font color ='#e96900'>事件</font>  |[finished](#finished)| 视频播放完后触发

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

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

>##### <span id=play><font color ='#0092db'>**play**</font></span>: 播放视频

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **path** |<font color ='#808000'>**string**</font> | 是 | |支持本地路径播放
  **mode** |<font color ='#808000'>**string**</font> | 否 | 2DNormal|支持8个场景模式，2DNormal:2d 普通平面， 2D180:2d 180度平面， 2D360:2d 360度平面， 2DSphere:2d 球幕 ，3DNormal:3d 普通平面， 3D180:3d 180度平面，3D360:3d 360度平面， 3DSphere:3d 球幕
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


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=finished><font color ='#e96900'>**finished**</font></span>: 视频播放完后触发

- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 
- 说明: 视频播放完后触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


