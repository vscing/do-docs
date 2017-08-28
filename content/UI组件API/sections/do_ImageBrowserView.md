---
title: do_ImageBrowserView 组件
---

### do_ImageBrowserView 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_ImageBrowserView)
 这个组件用于浏览大量网络或本地图片，图片路径可以http://链接或本地data://、source://目录，支持手势缩放原图，多图片支持左右滑动预览

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#42b983'>属性</font>  |[index](#index)| 索引
<font color ='#0092db'>同步方法</font>  |[bindItems](#bindItems)| 绑定数据
<font color ='#e96900'>事件</font>  |[indexChanged](#indexChanged)| 切换图片后触发该事件
<font color ='#e96900'>事件</font>  |[touch](#touch)| 点击图片触发
<font color ='#e96900'>事件</font>  |[longTouch](#longTouch)| 长按图片触发

#### <font color ='#40A977'>**1.**</font> 属性

>###### <span id=index><font color ='#42b983'>**index**</font></span>: 索引

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 0
- 说明 : 设置当前视图索引值，默认为0

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=bindItems><font color ='#0092db'>**bindItems**</font></span>: 绑定数据

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **data** |<font color ='#808000'>**object**</font> | 是 | |数据结构[{ source : '', init : ''},{source :'' , init : ''}, ..... ]其中source 为原图，init为缩略图
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 给视图绑定显示的图片
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=indexChanged><font color ='#e96900'>**indexChanged**</font></span>: 切换图片后触发该事件

- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 返回当前index值
- 说明: 切换图片后触发该事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <span id=touch><font color ='#e96900'>**touch**</font></span>: 点击图片触发

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回当前index值,如：{'index':1}
- 说明: 点击图片触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <span id=longTouch><font color ='#e96900'>**longTouch**</font></span>: 长按图片触发

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回当前index值，如:{'index':1}
- 说明: 长按图片触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


