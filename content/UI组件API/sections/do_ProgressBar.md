---
title: do_ProgressBar 组件
---

### do_ProgressBar 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_ProgressBar)
 可以设置基于值填充的进度条和显示重复模式的进度条

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#42b983'>属性</font>  |[progress](#progress)| 进度值
<font color ='#42b983'>属性</font>  |[style](#style)| 进度条样式

#### <font color ='#40A977'>**1.**</font> 属性

>###### <span id=progress><font color ='#42b983'>**progress**</font></span>: 进度值

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 :
- 说明 : 设置进度值,取值范围是0-100的Number(style是horizontal时才有效)
- 示例:

  ```javascript

    var do_ProgressBar_1 = ui("do_ProgressBar_1"); //实例化do_ProgressBar组件
    do_ProgressBar_1.progress = 60;

  ```

>###### <span id=style><font color ='#42b983'>**style**</font></span>: 进度条样式

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : normal
- 编辑类型 : 只允许设计区内修改
- 说明 : 进度条样式可以是以下几种类型：horizontal,large,small,normal

  进度条的四种样式对比的效果图如下

  <div align="center">

  <img src="../../images/ProgressBar.png" height="330" width="310" >

  </div>

#### <font color ='#40A977'>**2.**</font> 同步方法

#### <font color ='#40A977'>**3.**</font> 异步方法

#### <font color ='#40A977'>**4.**</font> 事件

#### <font color ='#40A977'>**5.**</font> 常见问题

#### <font color ='#40A977'>**6.**</font> 基本配置

  [回到顶部](#top)
