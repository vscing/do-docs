---
title: do_ProgressBar2 组件
---

### do_ProgressBar2 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_ProgressBar2)
 环行进度条，进度条大小为组件最大内接圆，居中显示在组件范围内

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#42b983'>属性</font>  |[style](#style)| 进度条样式
<font color ='#42b983'>属性</font>  |[progress](#progress)| 进度值
<font color ='#42b983'>属性</font>  |[progressColor](#progressColor)| 进度颜色
<font color ='#42b983'>属性</font>  |[progressBgColor](#progressBgColor)| 进度条背景颜色
<font color ='#42b983'>属性</font>  |[progressWidth](#progressWidth)| 进度宽度
<font color ='#42b983'>属性</font>  |[text](#text)| 文本
<font color ='#42b983'>属性</font>  |[fontColor](#fontColor)| 字体颜色
<font color ='#42b983'>属性</font>  |[fontSize](#fontSize)| 字体大小

#### <font color ='#40A977'>**1.**</font> 属性

>###### <span id=style><font color ='#42b983'>**style**</font></span>: 进度条样式

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : normal
- 编辑类型 : 只允许设计区内修改
- 说明 : 进度条样式可以是以下几种类型：normal,cycle

  设置进度条样式为normal和cycle的效果图：

  <div align="center">

  <img src="../../images/ProgressBar2_style.png" height="330" width="310" >

  </div>

>###### <span id=progress><font color ='#42b983'>**progress**</font></span>: 进度值

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 0
- 说明 : 设置进度值，取值范围是0-100的浮点值,进度条样式是普通样式时有效
- 示例 :

  ```javascript

    //实例化三个do_ProgressBar2组件
    var do_ProgressBar2_1 = ui("do_ProgressBar2_1");
    var do_ProgressBar2_2 = ui("do_ProgressBar2_2");
    var do_ProgressBar2_3 = ui("do_ProgressBar2_3");
    do_ProgressBar2_1.progress = 52;
  	do_ProgressBar2_2.progress = 62;
  	do_ProgressBar2_3.progress = 28;

  ```
  设置进度值分别为52、62、和28的效果图：

  <div align="center">

  <img src="../../images/ProgressBar2_progress.png" height="330" width="310" >

  </div>

[回到顶部](#top)


>###### <span id=progressColor><font color ='#42b983'>**progressColor**</font></span>: 进度颜色

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 000000FF
- 说明 : 8位16进制整数，前6位为rgb颜色值，后两位为透明度
- 示例 :

  ```javascript

    do_ProgressBar2_1.progressColor = "0000FFFF";
  	do_ProgressBar2_2.progressColor = "800080FF";
  	do_ProgressBar2_3.progressColor = "00FFFFFF";

  ```

  设置进度颜色分别为0000FFFF、800080FF、和00FFFFFF的效果图：

  <div align="center">

  <img src="../../images/ProgressBar2_progresscolor.png" height="330" width="310" >

  </div>

[回到顶部](#top)


>###### <span id=progressBgColor><font color ='#42b983'>**progressBgColor**</font></span>: 进度条背景颜色

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : FFFFFFFF
- 说明 : 8位16进制整数，前6位为rgb颜色值，后两位为透明度
- 示例 :

  ```javascript

    do_ProgressBar2_1.progressBgColor = "FFFFFFFF";
    do_ProgressBar2_2.progressBgColor = "F0F0F0FF";
    do_ProgressBar2_3.progressBgColor = "FFFFDBFF";

  ```

  设置进度条背景颜色分别为FFFFFFFF、F0F0F0FF、和FFFFDBFF的效果图：

  <div align="center">

  <img src="../../images/ProgressBar2_progressbgcolor.png" height="330" width="310" >

  </div>

[回到顶部](#top)


>###### <span id=progressWidth><font color ='#42b983'>**progressWidth**</font></span>: 进度宽度

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 1
- 说明 : 进度宽度，范围 为1-100，表示占环形进度条最外圈半径的百分比，如20表示占环形进度条半径的20%宽度
- 示例 :

  ```javascript

    do_ProgressBar2_1.progressWidth = 1;
    do_ProgressBar2_2.progressWidth = 10;
    do_ProgressBar2_3.progressWidth = 20;

  ```

  设置进度条宽度分别为1、10、和20的效果图：

  <div align="center">

  <img src="../../images/ProgressBar2_progressWidth.png" height="330" width="310" >

  </div>


>###### <span id=text><font color ='#42b983'>**text**</font></span>: 文本

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 :
- 说明 : 环形进度条中间文本,进度条样式为normal时有效
- 示例 :

  ```javascript

    do_ProgressBar2_1.text = "52%";

  ```

[回到顶部](#top)


>###### <span id=fontColor><font color ='#42b983'>**fontColor**</font></span>: 字体颜色

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 000000FF
- 说明 : 字体颜色，为8位16进制整数，前6位为rgb颜色值，后两位为透明度
- 示例 :

  ```javascript

    do_ProgressBar2_1.fontColor = "0000FFFF";
    do_ProgressBar2_2.fontColor = "800080FF";
    do_ProgressBar2_3.fontColor = "00FFFFFF";

  ```


>###### <span id=fontSize><font color ='#42b983'>**fontSize**</font></span>: 字体大小

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 17
- 说明 :
- 示例 :

  ```javascript

    do_ProgressBar2_1.fontSize = 20;
    do_ProgressBar2_2.fontSize = 30;
    do_ProgressBar2_3.fontSize = 40;

  ```

  设置字体颜色和字体大小的效果图：

  <div align="center">

  <img src="../../images/ProgressBar2_font.png" height="330" width="310" >

  </div>

#### <font color ='#40A977'>**2.**</font> 同步方法

#### <font color ='#40A977'>**3.**</font> 异步方法

#### <font color ='#40A977'>**4.**</font> 事件

#### <font color ='#40A977'>**5.**</font> 常见问题

#### <font color ='#40A977'>**6.**</font> 基本配置

[回到顶部](#top)
