---
title: do_ProgressBar1 组件
---

### do_ProgressBar1 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_ProgressBar1)
  横向一组圆点样式的进度条

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#42b983'>属性</font>  |[style](#style)| 进度条样式
<font color ='#42b983'>属性</font>  |[pointNum](#pointNum)| 圆点的数量
<font color ='#42b983'>属性</font>  |[defaultImage](#defaultImage)| 默认圆点图片
<font color ='#42b983'>属性</font>  |[changeImage](#changeImage)| 变化圆点图片
<font color ='#42b983'>属性</font>  |[pointColors](#pointColors)| 圆点可选颜色组

#### <font color ='#40A977'>**1.**</font> 属性

>###### <span id=style><font color ='#42b983'>**style**</font></span>: 进度条样式

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : normal
- 编辑类型 : 只允许设计区内修改
- 说明 : 进度条样式可以是以下几种类型：normal普通样式：可以设置两种状态对应不同的背景图片，动态改变背景图片。zoom缩放样式：可以设置多种颜色，进度条圆点有缩放效果。
  左图为normal样式的效果图，右图为zoom样式的效果图：

  <div align="center">

  <img src="../../images/ProgressBar1_normal.png" height="330" width="310" >

  <img src="../../images/ProgressBar1_zoom.png" height="330" width="310" >

  </div>

>###### <span id=pointNum><font color ='#42b983'>**pointNum**</font></span>: 圆点的数量

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 0
- 说明 : 圆点数量需要跟组件宽度相适应，宽度短，设置圆点数量过多，会显示不完整
- 示例:

  ```javascript

    var do_ProgressBar1 = ui("do_ProgressBar1_1");; //实例化do_ProgressBar组件
    do_ProgressBar1.pointNum = 7;

  ```
  设置圆点数量为7的效果图：

  <div align="center">

  <img src="../../images/ProgressBar1_pointnum.png" height="330" width="310" >

  </div>

>###### <span id=defaultImage><font color ='#42b983'>**defaultImage**</font></span>: 默认圆点图片

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 :
- 说明 : 进度条每个圆点默认的背景图片，支持data://和source://,进度条样式为normal时有效
- 示例:

  ```javascript

    do_ProgressBar1.defaultImage = "source://view/do_ProgressBar1/image/circle.png"

  ```

>###### <span id=changeImage><font color ='#42b983'>**changeImage**</font></span>: 变化圆点图片

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 :
- 说明 : 进度条变化的圆点图片背景图片，支持data://和source://,进度条样式为normal时有效
- 示例:

  ```javascript

    do_ProgressBar1.changeImage = "source://view/do_ProgressBar1/image/smile.png"

  ```
  设置默认图片和变化图片的效果图：

  <div align="center">

  <img src="../../images/ProgressBar1_image.png" height="330" width="310" >

  </div>

>###### <span id=pointColors><font color ='#42b983'>**pointColors**</font></span>: 圆点可选颜色组

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 :
- 说明 : 颜色组成的字符串，比如 000000FF,00FF00FF,00FFFFFF，中间用逗号隔开。该颜色组用于设置圆点颜色，进度条样式为zoom时有效，当颜色数量大于圆点数量时，选中靠前的颜色，当颜色数量小于圆点数量时，重复选择颜色组中颜色
- 示例:

  ```javascript

    do_ProgressBar1.pointColors = "000000FF,FF0000FF,00FFFFFF,FF00FFFF";

  ```
  设置圆点颜色组的效果图：

  <div align="center">

  <img src="../../images/ProgressBar1_pointcolor.png" height="330" width="310" >

  </div>

                                                             
#### <font color ='#40A977'>**2.**</font> 同步方法

#### <font color ='#40A977'>**3.**</font> 异步方法

#### <font color ='#40A977'>**4.**</font> 事件

#### <font color ='#40A977'>**5.**</font> 常见问题

#### <font color ='#40A977'>**6.**</font> 基本配置

  [回到顶部](#top)
