---
title: do_Canvas 组件
---

  ### do_Canvas 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_Canvas)
 支持2D图形处理，可以画点，线，多边形，文字，图片。样式的修改必须在定义图形之前才会生效。

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#42b983'>属性</font>  |[strokeColor](#strokeColor)| 画笔颜色
<font color ='#42b983'>属性</font>  |[strokeWidth](#strokeWidth)| 画笔宽度
<font color ='#42b983'>属性</font>  |[strokeCap](#strokeCap)| 笔触样式
<font color ='#42b983'>属性</font>  |[isFull](#isFull)| 是否填充
<font color ='#0092db'>同步方法</font>  |[definePoint](#definePoint)| 定义点
<font color ='#0092db'>同步方法</font>  |[defineLine](#defineLine)| 定义线
<font color ='#0092db'>同步方法</font>  |[defineCircle](#defineCircle)| 定义圆
<font color ='#0092db'>同步方法</font>  |[defineOval](#defineOval)| 定义椭圆
<font color ='#0092db'>同步方法</font>  |[defineArc](#defineArc)| 定义弧
<font color ='#0092db'>同步方法</font>  |[defineRect](#defineRect)| 定义矩形
<font color ='#0092db'>同步方法</font>  |[defineText](#defineText)| 定义文字
<font color ='#0092db'>同步方法</font>  |[defineImage](#defineImage)| 定义图片
<font color ='#0092db'>同步方法</font>  |[paint](#paint)| 画
<font color ='#0092db'>同步方法</font>  |[clear](#clear)| 清空画布
<font color ='#0092db'>异步方法</font>  |[saveAsBitmap](#saveAsBitmap)| 保存为Bitmap

#### <font color ='#40A977'>**1.**</font> 属性

>###### <span id=strokeColor><font color ='#42b983'>**strokeColor**</font></span>: 画笔颜色

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 000000FF
- 说明 : 设置当前的画笔颜色，颜色值为8位16进制

  ```javascript

  var do_Canvas = ui("do_Canvas_1");

  do_Canvas.strokeColor = "D869D5FF";    //设置do_Canvas的画笔颜色为紫色

  ```

>###### <span id=strokeWidth><font color ='#42b983'>**strokeWidth**</font></span>: 画笔宽度

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 1
- 说明 : 设置画笔的宽度

  ```javascript

  do_Canvas.strokeWidth = 15;    //设置do_Canvas的画笔宽度为15

  ```
  左图为画笔颜色是黑色、宽度是5的效果图，右图为画笔颜色是紫色、宽度是15的效果图：
  <div>
  <img src="../../images/canvas_strokeColor.png" height="380" width="320" >

  <img src="../../images/canvas_strokeWidth.png" height="380" width="320" >

  </div>

>###### <span id=strokeCap><font color ='#42b983'>**strokeCap**</font></span>: 笔触样式

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 0
- 说明 : 支持0：正方形，1：圆，默认值为0

  ```javascript

  do_Canvas.strokeCap = 1;    //设置do_Canvas的笔触样式为圆

  ```
  左图为笔触样式是正方形的效果图，右图为笔触样式是圆的效果图：
  <div>
  <img src="../../images/canvas_strokeCapsquare.png" height="380" width="320" >

  <img src="../../images/canvas_strokeCapscircle.png" height="380" width="320" >

  </div>

>###### <span id=isFull><font color ='#42b983'>**isFull**</font></span>: 是否填充

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : true
- 说明 : 闭合图形是否填充内容。true:填充,false:不填充。

  ```javascript

  do_Canvas.isFull = false;    //设置do_Canvas为不填充

  ```
  左图为填充的效果图，右图为不填充的效果图：
  <div>
  <img src="../../images/canvas_isFulltrue.png" height="380" width="320" >

  <img src="../../images/canvas_isFullfalse.png" height="380" width="320" >

  </div>

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=definePoint><font color ='#0092db'>**definePoint**</font></span>: 定义点

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **points** |<font color ='#808000'>**object**</font> | 是 | |
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 传入点的坐标，支持画多个点。参数示例：
  ```

  [
      {
          "x":x坐标,
          "y":y坐标
      },
      {
          "x":x1坐标,
          "y":y1坐标
      }，
      ...
  ]

  ```

- 示例:

  ```javascript

  //定义画的多个点
  do_Canvas.definePoint({
  	  points : [ {
    		x : 400,
    		y : 250
    	}, {
    		x : 610,
    		y : 260
    	}, {
    		x : 500,
    		y : 300
    	}, {
    		x : 350,
    		y : 280
    	}, {
    		x : 520,
    		y : 400
    	}, {
    		x : 220,
    		y : 430
    	} ]
  });    
  do_Canvas.paint(); //调用paint方法把点画到画板上

  ```
  效果图如下：
  <img src="../../images/canvas_spot.png" width="330" height="380" />

[回到顶部](#top)

>##### <span id=defineLine><font color ='#0092db'>**defineLine**</font></span>: 定义线

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **start** |<font color ='#808000'>**object**</font> | 是 | |起始点坐标，如：{x:x坐标,y:y坐标}
  **end** |<font color ='#808000'>**object**</font> | 是 | |终点坐标，如：{x:x坐标,y:y坐标}
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 传入两点坐标，画一条起始点坐标和终点坐标的连线。
- 示例:

  ```javascript

  //定义画的线
  do_Canvas.defineLine({
    	start : {
    		x : 180,
    		y : 180
    	},
    	end : {
    		x : 400,
    		y : 450
    	}
  })
  do_Canvas.paint();

  ```
  效果图如下：
  <img src="../../images/canvas_line.png" width="330" height="380" />

[回到顶部](#top)

>##### <span id=defineCircle><font color ='#0092db'>**defineCircle**</font></span>: 定义圆

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **point** |<font color ='#808000'>**object**</font> | 是 | |圆心坐标，如：{x:x坐标,y:y坐标}
  **radius** |<font color ='#808000'>**number**</font> | 是 | |半径
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明:传入圆心坐标，画一个以point坐标为圆心radius值为半径的圆。
- 示例:

  ```javascript

  //定义画的圆形
  do_Canvas.defineCircle({
    	point : {
    		x : 350,
    		y : 250
    	},
    	radius : 100
  });
  do_Canvas.paint();

  ```
  效果图如下：
  <img src="../../images/canvas_circle.png" width="330" height="380" />

[回到顶部](#top)

>##### <span id=defineOval><font color ='#0092db'>**defineOval**</font></span>: 定义椭圆

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **start** |<font color ='#808000'>**object**</font> | 是 | |左上坐标，如：{x:x坐标,y:y坐标}
  **end** |<font color ='#808000'>**object**</font> | 是 | |右下坐标，如：{x:x坐标,y:y坐标}
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 通过左上坐标与右下坐标定义一个矩形，然后沿着矩形画内切椭圆
- 说明:
- 示例:

  ```javascript

  //定义画的椭圆
  do_Canvas.defineOval({
    	start : {
    		x : 220,
    		y : 200
    	},
    	end : {
    		x : 400,
    		y : 300
    	}
  });
  do_Canvas.paint();

  ```
  效果图如下：
  <img src="../../images/canvas_oval.png" width="330" height="380" />

[回到顶部](#top)

>##### <span id=defineArc><font color ='#0092db'>**defineArc**</font></span>: 定义弧

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **start** |<font color ='#808000'>**object**</font> | 是 | |左上坐标，如：{x:x坐标,y:y坐标}
  **end** |<font color ='#808000'>**object**</font> | 是 | |右下坐标，如：{x:x坐标,y:y坐标}
  **startAngle** |<font color ='#808000'>**number**</font> | 否 | 0|起始角度，0表示与x轴重合
  **sweepAngle** |<font color ='#808000'>**number**</font> | 否 | 90|默认为90，以起始角度开始，顺时针扫描90度
  **useCenter** |<font color ='#808000'>**boolean**</font> | 否 | true|如果为true，这个弧的区域就会包含中心点
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 画一个以左上坐标和右下坐标连线的中点为圆心的弧，startAngle是弧绕坐标原点（弧的圆心）顺时针旋转偏离x轴的度数，weepAngle是弧顺时针扫描的角度（即弧的圆心角度数）
- 说明:
- 示例:

  ```javascript

  //定义画的弧
  do_Canvas.defineArc({
    	start : {
    		x : 2,
    		y : 2
    	},
    	end : {
    		x : 500,
    		y : 460
    	},
    	startAngle : 0,
    	sweepAngle : 120,
    	useCenter : false  
  });
  do_Canvas.paint();

  ```
  左图为不包含中心点的弧，右图为包含中心点的弧：
  <div>
  <img src="../../images/canvas_arc.png" height="380" width="320" >

  <img src="../../images/canvas_arccenter.png" height="380" width="320" >

  </div>

[回到顶部](#top)

>##### <span id=defineRect><font color ='#0092db'>**defineRect**</font></span>: 定义矩形

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **start** |<font color ='#808000'>**object**</font> | 是 | |左上坐标，如：{x:x坐标,y:y坐标}
  **end** |<font color ='#808000'>**object**</font> | 是 | |右下坐标，如：{x:x坐标,y:y坐标}
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 通过左上坐标与右下坐标画一个矩形
- 说明:
- 示例:

  ```javascript

  //定义画的矩形
  do_Canvas.defineRect({
  		start : {
  			x : 200,
  			y : 330
  		},
  		end : {
  			x : 550,
  			y : 500
  		}
	});
  do_Canvas.paint();

  ```
  效果图如下：
  <img src="../../images/canvas_rect.png" width="330" height="380" />

[回到顶部](#top)

>##### <span id=defineText><font color ='#0092db'>**defineText**</font></span>: 定义文字

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **text** |<font color ='#808000'>**string**</font> | 是 | |画出来的文字内容
  **coord** |<font color ='#808000'>**object**</font> | 否 | {x:0,y:0}|从此坐标开始画，如：{x:x坐标,y:y坐标}
  **fontStyle** |<font color ='#808000'>**string**</font> | 否 | normal|包含4种类型：normal：常规，bold：粗体，italic：斜体，bold_italic：粗斜体（iOS平台不支持）
  **textFlag** |<font color ='#808000'>**string**</font> | 否 | normal|包含3种类型：normal：常规，underline ：下划线，strikethrough ：删除线
  **fontSize** |<font color ='#808000'>**number**</font> | 否 | 17|
  **textAlign** |<font color ='#808000'>**string**</font> | 否 | left|对齐方式为以下3种：left 左对齐（默认），center 居中，right 右对齐。
  **angle** |<font color ='#808000'>**number**</font> | 否 | 0|绕坐标原点顺时针旋转偏离x轴的角度，0表示与x轴重合
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 画出传入参数对应样式的文字
- 说明:
- 示例:

  ```javascript

  //定义画的文字
  do_Canvas.defineText({
  		text : "定义文字啦啦",
  		coord : {
  			x : 250,
  			y : 300
  		},
  		fontStyle : "italic",
  		textFlag : "strikethrough",
  		fontSize : 40,
  		textAlign : "left",
  		angle : 50
	});
  do_Canvas.paint();

  ```
  效果图如下：
  <img src="../../images/canvas_text.png" width="330" height="380" />

[回到顶部](#top)

>##### <span id=defineImage><font color ='#0092db'>**defineImage**</font></span>: 定义图片

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **source** |<font color ='#808000'>**string**</font> | 是 | |支持do_Bitmap对象或data://开头的图片路径
  **coord** |<font color ='#808000'>**object**</font> | 否 | {x:0,y:0}|从此坐标开始画，如：{x:x坐标,y:y坐标}
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 设置一张图片作为背景
- 说明:
- 示例:

  ```javascript

  // 定义画的do_Bitmap图片
  var bitmap = mm("do_Bitmap");
  bitmap.loadFile({
  	source : "http://photocdn.sohu.com/20161128/Img474303098.jpg"
  }, function(data, e) {
    	do_Canvas.defineImage({
      		source : bitmap,
      		coord : {
      			x : 300,
      			y : 200
      		}
    	});
  })
  do_Canvas.paint();

  ```
  效果图如下：
  <img src="../../images/canvas_picture.png" width="330" height="380" />

[回到顶部](#top)

>##### <span id=paint><font color ='#0092db'>**paint**</font></span>: 画

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 将当前定义的图形，在Canvas上画出来，未定义图形时没有效果。
- 示例:

  ```javascript

  //将当前do_Canvas定义的图形画出来，可以定义多个图形调用paint时会把已定义的图形都画出来
  //注意：先定义样式后定义图形，画出来的图形才会有对应的样式
  do_Canvas.paint();

  ```

[回到顶部](#top)

>##### <span id=clear><font color ='#0092db'>**clear**</font></span>: 清空画布

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 清空整个画布内容
- 示例:

  ```javascript

  //清空当前画布，同时会清空已定义的图形
  do_Canvas.clear();

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <span id=saveAsBitmap><font color ='#0092db'>**saveAsBitmap**</font></span>: 保存为Bitmap

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **bitmap** |<font color ='#808000'>**string**</font> | 是 | |bitmap对象
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 将整个view保存为一个Bitmap
- 示例:

  ```javascript

  var bitmap1 = mm("do_Bitmap");
  do_Canvas.saveAsBitmap(bitmap1, function(data, e) {
      deviceone.print(JSON.stringify(data))
  })

  ```

#### <font color ='#40A977'>**4.**</font> 事件

#### <font color ='#40A977'>**5.**</font> 常见问题

- 1. 魅族手机设置下划线或者删除线，同时设置align为right的时下划线和删除线会跑偏。  
     原因：魅族手机原生就有这个问题，无法修复。

#### <font color ='#40A977'>**6.**</font> 基本配置

[回到顶部](#top)
