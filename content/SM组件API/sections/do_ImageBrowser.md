---
title: do_ImageBrowser 组件
---

### do_ImageBrowser 组件

 支持平台: iOS7.0,Android4.0
 这个组件用于浏览大量网络或本地图片，图片路径可以http://链接或本地data://、source://、initdata://目录，支持放大后缩放原图，多图片支持左右滑动预览，进入浏览界面单击一下屏幕退出

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**show**</font>: 预览

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **data** |<font color ='#808000'>**object**</font> | 是 | |预览图片传递数据结构[{ source : '', init : ''},{source :'' , init : ''}, ..... ]其中source 为原图，init为缩略图
  **index** |<font color ='#808000'>**number**</font> | 是 | 0|设置当前预览图片索引值，默认为0
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 打开预览，图片底部显示当前图片索引和总图片数
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <font color ='#e96900'>**longTouch**</font>: 长按预览图片触发

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 当前图片的索引值和图片的source，如['index':'','source':'']
- 说明: 长按预览图片触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**result**</font>: 点击关闭预览时触发

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 当前预览图片的索引{'index':''}
- 说明: 点击关闭预览时触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


