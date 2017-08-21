---
title: M0011_NibiruVRVideoPlayer 组件
---

### M0011_NibiruVRVideoPlayer 组件

* 支持平台: iOS,Android4.0
播放支持8个场景模式，2DNormal 2D180 2D360 2DSphere 3DNormal 3D180 3D360 3DSphere

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

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

>##### <font color ='#0092db'>**play**</font>: 播放视频

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **path** |<font color ='#808000'>**string**</font> |  | 是||支持本地路径播放
  **mode** |<font color ='#808000'>**string**</font> | 2DNormal | 否|2DNormal|支持8个场景模式，2DNormal:2d 普通平面， 2D180:2d 180度平面， 2D360:2d 360度平面， 2DSphere:2d 球幕 ，3DNormal:3d 普通平面， 3D180:3d 180度平面，3D360:3d 360度平面， 3DSphere:3d 球幕
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


#### <font color ='#40A977'>**4.**</font> 事件

>###### <font color ='#e96900'>**finished**</font>: 视频播放完后触发

- 返回值类型 : <font color ='#808000'>**String**</font>
- 返回值描述: 
- 说明: 视频播放完后触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


