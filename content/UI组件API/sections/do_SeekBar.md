---
title: do_SeekBar 组件
---

### do_SeekBar 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_SeekBar)
 可以拖动的进度条，取值范围为0~100

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#42b983'>属性</font>  |[progress](#progress)| 第一进度值
<font color ='#42b983'>属性</font>  |[secondaryProgress](#secondaryProgress)| 第二进度值
<font color ='#e96900'>事件</font>  |[progressChanged](#progressChanged)| 第一进度值变化时候触发

#### <font color ='#40A977'>**1.**</font> 属性

>###### <span id=progress><font color ='#42b983'>**progress**</font></span>: 第一进度值

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 :
- 说明 : 设置第一进度值，支持手势拖动
- 示例:

  ```javascript

  var do_SeekBar_1 = ui("do_SeekBar_1");
  do_SeekBar_1.progress = 50;

  ```

>###### <span id=secondaryProgress><font color ='#42b983'>**secondaryProgress**</font></span>: 第二进度值

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 :
- 说明 : 设置第二进度值
- 示例:

  ```javascript

  do_SeekBar_1.secondaryProgress = 90;

  ```

  下图为以上示例代码的展示效果。

  <div>

  <img src="../../images/seekbar.png" height="380" width="330" >

  </div>

#### <font color ='#40A977'>**2.**</font> 同步方法

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=progressChanged><font color ='#e96900'>**progressChanged**</font></span>: 第一进度值变化时候触发

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述:
- 说明: 第一进度值变化时候触发
- 示例:

  ```javascript

  do_SeekBar.on("progressChanged",function(data){
    
  })

  ```

[回到顶部](#top)
