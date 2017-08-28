---
title: do_QRCode 组件
---

### do_QRCode 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_QRCode)
 二维码的生成和识别；其中iOS平台的二维码识别功能系统需要iOS8级以上的系统，设备需要5S及以上产品

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#0092db'>异步方法</font>  |[create](#create)| 生成二维码
<font color ='#0092db'>异步方法</font>  |[recognition](#recognition)| 识别二维码

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <span id=create><font color ='#0092db'>**create**</font></span>: 生成二维码

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **text** |<font color ='#808000'>**string**</font> | 是 | |
  **length** |<font color ='#808000'>**number**</font> | 否 | 500|生成的二维码图片边长
  **logoPath** |<font color ='#808000'>**string**</font> | 否 | |只支持本地文件data:// source:// 打头的URI格式，不能包含@符号
  **logoLength** |<font color ='#808000'>**number**</font> | 否 | 20|与图片边长的对比百分比，取值范围为1~100，但建议取值范围为1~30，超过30后可能导致二维码无法被识别；默认值为length值的20%
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 生成的二维码图片会保存在data://temp/do_QRCode目录下，并返回生成的二维码图片的路径
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=recognition><font color ='#0092db'>**recognition**</font></span>: 识别二维码

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **path** |<font color ='#808000'>**string**</font> | 是 | |可设置html链接或本地文件，支持：http:// https:// data:// source:// 打头的URI格式，不能包含@符号。其中文件格式说明可参考Storage类
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回二维码的文本内容
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件


