---
title: do_GestureView 组件
---

### do_GestureView 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_GestureView)
 手势组件，缺省是透明的，windowsPC不支持

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#e96900'>事件</font>  |[touch](#touch)| 按下并在组件范围抬起，触发该事件
<font color ='#e96900'>事件</font>  |[touchDown](#touchDown)| 组件范围内按下即可触发
<font color ='#e96900'>事件</font>  |[touchUp](#touchUp)| 一旦按下，手指离开即触发，不论是否在组件范围内
<font color ='#e96900'>事件</font>  |[longTouch](#longTouch)| 长按触发该事件
<font color ='#e96900'>事件</font>  |[fling](#fling)| 手指在触摸屏上迅速移动，并松开的动作，松开时触发
<font color ='#e96900'>事件</font>  |[move](#move)| 手指在触摸屏上移动时触发

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=touch><font color ='#e96900'>**touch**</font></span>: 按下并在组件范围抬起，触发该事件

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {x:'100',y:'100'} 返回手指在组件内x,y的绝对值
- 说明: 按下并在组件范围抬起，触发该事件
- 示例:

  ```javascript

  var do_GestureView = ui("do_GestureView_1");
  //按下并在组件范围抬起，触发该事件
  do_GestureView.on("touch",function(_data){
    //将do_Button_1移动到点击的位置
  	ui("do_Button_1").x  = _data.x;
  	ui("do_Button_1").y  = _data.y;
  	ui("do_Button_1").redraw();  
  	deviceone.print(JSON.stringify(_data),"touch事件返回值")
  })

  //返回值格式如下
  {
    "x":496.0684458414714,
    "y":646.5142899195353
  }

  ```
  点击时把页面上的button组件移动到点击的位置，效果图如下：
  <div>
  <img src="../../images/GestureView_normal.png" height="380" width="320" >

  <img src="../../images/GestureView_touch.png" height="380" width="320" >

  </div>

[回到顶部](#top)

>###### <span id=touchDown><font color ='#e96900'>**touchDown**</font></span>: 组件范围内按下即可触发

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {x:'100',y:'100'} 返回手指x,y在屏幕的绝对值
- 说明: 组件范围内按下即可触发
- 示例:

  ```javascript

  //组件范围内按下即可触发
  do_GestureView.on("touchDown",function(_data){
  	deviceone.print(JSON.stringify(_data),"touchDown事件返回值")
  })

  //返回值格式如下
  {
      "x":496.0684458414714,
      "y":646.5142899195353
  }

  ```

[回到顶部](#top)

>###### <span id=touchUp><font color ='#e96900'>**touchUp**</font></span>: 一旦按下，手指离开即触发，不论是否在组件范围内

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {x:'100',y:'100'} 返回手指x,y在屏幕的绝对值
- 说明: 一旦按下，手指离开即触发，不论是否在组件范围内
- 示例:

  ```javascript

  //一旦按下，手指离开即触发，不论是否在组件范围内
  do_GestureView.on("touchUp",function(_data){
  	deviceone.print(JSON.stringify(_data),"touchUp事件返回值")
  })

  //返回值格式如下
  {
    "x":496.0684458414714,
    "y":646.5142899195353
  }

  ```

[回到顶部](#top)

>###### <span id=longTouch><font color ='#e96900'>**longTouch**</font></span>: 长按触发该事件

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {x:'100',y:'100'} 返回手指x,y在屏幕的绝对值
- 说明: 长按触发该事件
- 示例:

  ```javascript

  //长按do_GestureView组件触发事件
  do_GestureView.on("longTouch",function(_data){
     //将do_Button_1移动到长按的位置
  	ui("do_Button_1").x  = _data.x;
  	ui("do_Button_1").y  = _data.y;
  	ui("do_Button_1").redraw();
  	deviceone.print(JSON.stringify(_data),"longTouch事件返回值")
  })

  //返回值格式如下
  {
    "x":448.1961144341363,
    "y":403.4637906392415
  }

  ```

[回到顶部](#top)

>###### <span id=fling><font color ='#e96900'>**fling**</font></span>: 手指在触摸屏上迅速移动，并松开的动作，松开时触发

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {velocityX:'100',velocityY:'100'} 返回手指在手指x,y方向滑动的速率，其中正值表示的是往下和往右、负值表示的是往上和往左。iOS的速率是固定值
- 说明: 手指在触摸屏上迅速移动，并松开的动作，松开时触发
- 示例:

  ```javascript

  //手指在触摸屏上迅速移动，并松开的动作，松开时触发
  do_GestureView.on("fling",function(_data){
  	deviceone.print(JSON.stringify(_data),"fling事件返回值")
  })

  //返回值格式如下
  {
      "velocityX":1932.673095703125,
      "velocityY":783.9417724609375
  }

  ```

[回到顶部](#top)

>###### <span id=move><font color ='#e96900'>**move**</font></span>: 手指在触摸屏上移动时触发

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {x:'100',y:'100'} 返回手指x,y在屏幕的绝对值
- 说明: 手指在触摸屏上移动时触发
- 示例:

  ```javascript

  //手指在触摸屏上移动时触发
  do_GestureView.on("move",function(_data){
    //将do_Button_1移动到手指移动位置，具体效果可以下载代码查看
  	ui("do_Button_1").x  = _data.x;
  	ui("do_Button_1").y  = _data.y;
  	ui("do_Button_1").redraw();
  	deviceone.print(JSON.stringify(_data),"move事件返回值")
  })

  //返回值格式如下
  {
      "x":530.6989034016927,
      "y":409.5346091588338
  }

  ```

#### <font color ='#40A977'>**5.**</font> 常见问题

- 1. iOS、Andriod手势与点击事件冲突问题。  
     原因：手势组件就是为了获得手势最高优先级的。手指滑动一下，不会触发touchUP事件。

#### <font color ='#40A977'>**6.**</font> 基本配置

[回到顶部](#top)
