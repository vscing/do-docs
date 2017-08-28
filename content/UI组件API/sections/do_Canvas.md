---
title: do_Canvas 组件
---

### do_Canvas 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_Canvas)
 支持2D图形处理，可以画点，线，多边形，文字，图片。样式的修改必须在定义图形之前才会生效

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

>###### <span id=strokeWidth><font color ='#42b983'>**strokeWidth**</font></span>: 画笔宽度

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 1
- 说明 : 设置画笔的宽度

>###### <span id=strokeCap><font color ='#42b983'>**strokeCap**</font></span>: 笔触样式

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 0
- 说明 : 支持0：正方形,1：圆，默认值为0

>###### <span id=isFull><font color ='#42b983'>**isFull**</font></span>: 是否填充

- 数据类型 : <font color ='#808000'>**Boolean**</font>
- 默认值 : true
- 说明 : 闭合图形是否填充内容，true：填充,false：不填充

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=definePoint><font color ='#0092db'>**definePoint**</font></span>: 定义点

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **points** |<font color ='#808000'>**object**</font> | 是 | |支持点的集合，如：[{x:x坐标,y:y坐标},{x:x1坐标,y:y1坐标}...]
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 支持画多点
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=defineLine><font color ='#0092db'>**defineLine**</font></span>: 定义线

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **start** |<font color ='#808000'>**object**</font> | 是 | |起始点坐标，如：{x:x坐标,x:y坐标}
  **end** |<font color ='#808000'>**object**</font> | 是 | |终点坐标，如：{x:x坐标,x:y坐标}
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 传入两点坐标，画一条直线
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=defineCircle><font color ='#0092db'>**defineCircle**</font></span>: 定义圆

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **point** |<font color ='#808000'>**object**</font> | 是 | |圆心坐标，如：{x:x坐标,x:y坐标}
  **radius** |<font color ='#808000'>**number**</font> | 是 | |圆角半径
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=defineOval><font color ='#0092db'>**defineOval**</font></span>: 定义椭圆

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **start** |<font color ='#808000'>**object**</font> | 是 | |左上坐标，如：{x:x坐标,x:y坐标}
  **end** |<font color ='#808000'>**object**</font> | 是 | |右下坐标，如：{x:x坐标,x:y坐标}
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 通过左上坐标与右下坐标定义一个矩形，然后沿着矩形画内切椭圆
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=defineArc><font color ='#0092db'>**defineArc**</font></span>: 定义弧

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **start** |<font color ='#808000'>**object**</font> | 是 | |左上坐标，如：{x:x坐标,x:y坐标}
  **end** |<font color ='#808000'>**object**</font> | 是 | |右下坐标，如：{x:x坐标,x:y坐标}
  **startAngle** |<font color ='#808000'>**number**</font> | 否 | 0|如果为0默认与x轴重合
  **sweepAngle** |<font color ='#808000'>**number**</font> | 否 | 90|默认为90，以起始角度开始，顺时针扫描90度
  **useCenter** |<font color ='#808000'>**Boolean**</font> | 否 | true|如果为true，这个弧的区域就会包含中心点
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=defineRect><font color ='#0092db'>**defineRect**</font></span>: 定义矩形

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **start** |<font color ='#808000'>**object**</font> | 是 | |左上坐标，如：{x:x坐标,x:y坐标}
  **end** |<font color ='#808000'>**object**</font> | 是 | |右下坐标，如：{x:x坐标,x:y坐标}
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 通过左上坐标与右下坐标定义一个矩形
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=defineText><font color ='#0092db'>**defineText**</font></span>: 定义文字

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **text** |<font color ='#808000'>**string**</font> | 是 | |
  **coord** |<font color ='#808000'>**object**</font> | 否 | {x:0,y:0}|从此坐标开始画，如：{x:x坐标,x:y坐标}
  **fontStyle** |<font color ='#808000'>**string**</font> | 否 | normal|包含4种类型：normal：常规bold：粗体italic：斜体bold_italic：粗斜体（iOS平台不支持）
  **textFlag** |<font color ='#808000'>**string**</font> | 否 | normal|包含3种类型：normal：常规underline ：下划线strikethrough ：删除线
  **fontSize** |<font color ='#808000'>**number**</font> | 否 | 17|
  **textAlign** |<font color ='#808000'>**string**</font> | 否 | left|对齐方式为以下3种：left 左对齐（默认）；center 居中；right 右对齐。
  **angle** |<font color ='#808000'>**number**</font> | 否 | 0|如果为0默认与x轴重合
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 通过左上坐标与右下坐标定义一个矩形
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=defineImage><font color ='#0092db'>**defineImage**</font></span>: 定义图片

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **source** |<font color ='#808000'>**string**</font> | 是 | |支持do_Bitmap对象或data://开头的路径的图片地址
  **coord** |<font color ='#808000'>**object**</font> | 否 | {x:0,y:0}|从此坐标开始画，如：{x:x坐标,x:y坐标}
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 设置一张图片作为背景
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=paint><font color ='#0092db'>**paint**</font></span>: 画

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 在Canvas上画出来
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=clear><font color ='#0092db'>**clear**</font></span>: 清空画布

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 清空整个画布内容
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <span id=saveAsBitmap><font color ='#0092db'>**saveAsBitmap**</font></span>: 保存为Bitmap

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **bitmap** |<font color ='#808000'>**string**</font> | 是 | |
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 将整个view保存为一个Btimap
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件


