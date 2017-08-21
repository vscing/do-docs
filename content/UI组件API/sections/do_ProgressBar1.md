---
title: do_ProgressBar1 组件
---

### do_ProgressBar1 组件

 支持平台: iOS7.0,Android4.0
  横向一组圆点样式的进度条

#### <font color ='#40A977'>**1.**</font> 属性

>###### <font color ='#42b983'>**style**</font>: 进度条样式

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : normal
- 说明 : 进度条样式可以是以下几种类型：normal普通样式：可以设置两种状态对应背景图片，动态改变背景图片的样式。zoom缩放样式：可以设置多颜色，进度条圆点有缩放效果。

>###### <font color ='#42b983'>**pointNum**</font>: 圆点的数量

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 0
- 说明 : 圆点数量需要跟组件宽度相适应，宽度短，设置圆点数量过多，会显示不完整

>###### <font color ='#42b983'>**defaultImage**</font>: 默认圆点图片

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 : 进度条每个圆点默认的背景图片，支持data://和source://,进度条样式为普通时有效

>###### <font color ='#42b983'>**changeImage**</font>: 变化圆点图片

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 : 进度条变化的圆点图片背景图片，支持data://和source://,进度条样式为普通时有效

>###### <font color ='#42b983'>**pointColors**</font>: 圆点可选颜色组

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 : 颜色组成的字符串，比如 000000FF,00FF00FF,#00FFFFFF，中间用逗号隔开。该颜色组用于设置圆点颜色，进度条样式为缩放时有效，当颜色数量大于圆点数量时，选中靠前的颜色，当颜色数量小于圆点数量时，重复选择颜色组中颜色 

#### <font color ='#40A977'>**2.**</font> 同步方法

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件


