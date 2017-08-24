---
title: do_Camera 组件
---

### do_Camera 组件

 支持平台: iOS7.0,Android4.0
 启动系统的相机拍照获取照片


#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <font color ='#0092db'>**capture**</font>: 拍照、获取照片

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **width** |<font color ='#808000'>**number**</font> | 否 | |不设置表示原始大小
  **height** |<font color ='#808000'>**number**</font> | 否 | |不设置表示原始大小
  **quality** |<font color ='#808000'>**number**</font> | 否 | 100|100表示原始的图片质量，清晰度越低，图片文件大小越小。windows平台不支持
  **iscut** |<font color ='#808000'>**Boolean**</font> | 否 | false|如果这个值为true的话，拍照结束后会出现一个中间的取景界面，有一个矩形框让用户选择局部区域；windowsPhone不支持
  **facingFront** |<font color ='#808000'>**Boolean**</font> | 否 | false|如果这个值为true的话，一启动拍照会打开前置摄像头，windows平台不支持
  **outPath** |<font color ='#808000'>**string**</font> | 否 | |要保存的图片文件路径，支持数据区data://，指定到文件名，若不填写则默认保存到data://temp/do_Camera/目录下
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 执行方法后，弹出系统相机，拍照后，图片的原始分辨率通常比较高。拍完的图片缺省会另存到data://temp/do_Camera/目录下可以通过用户传入width，height来裁剪图片大小。如果设置的宽高比例和真实图片宽高比例不一致的话，图片会自动平铺拉伸。width和height均为-1时保持图片的原始宽高不变；width或height有任何一个值为-1，则保持图片的原始宽高比不变 ,以不为-1的那个值做为基准, 保持原图的宽高比。也可以通过设置清晰度quality来使图片文件变小
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件


