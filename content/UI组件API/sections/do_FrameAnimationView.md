---
title: do_FrameAnimationView 组件
---

### do_FrameAnimationView 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_FrameAnimationView)
 加载gif动图的视图，也可以将多张图片组合设置为动图效果；gifSource:和imagesSource属性不会同时起作用，两个属性同时设置时以imagesSource为准

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#0092db'>同步方法</font>  |[startImages](#startImages)| 开始动画
<font color ='#0092db'>同步方法</font>  |[startGif](#startGif)| 开始动画
<font color ='#0092db'>同步方法</font>  |[stop](#stop)| 结束动画

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=startImages><font color ='#0092db'>**startImages**</font></span>: 开始动画

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **data** |<font color ='#808000'>**object**</font> | 是 | |[ {path:'data://2.png',duration:50}, {path:'data://3.png',duration:50} ] ，支持data://, source://路径，其中duration的单位为毫秒
  **repeat** |<font color ='#808000'>**number**</font> | 否 | 1|帧动画的重复次数，为-1或小于0时表示无限循环，为0时表示没有动画，默认执行一次
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=startGif><font color ='#0092db'>**startGif**</font></span>: 开始动画

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **data** |<font color ='#808000'>**string**</font> | 是 | |支持data://, source://路径
  **repeat** |<font color ='#808000'>**number**</font> | 否 | 1|帧动画的重复次数，为-1或小于0时表示无限循环，为0时表示没有动画，默认执行一次；windows平台不支持设置重复次数，只能循环播放
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=stop><font color ='#0092db'>**stop**</font></span>: 结束动画

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


