---
title: do_Canvas 组件
---

### do_Canvas 组件

 支持平台: iOS7.0,Android4.0
 支持2D图形处理，可以画点，线，多边形，文字，图片。样式的修改必须在定义图形之前才会生效

#### <font color ='#40A977'>**1.**</font> 属性

>###### <font color ='#42b983'>**strokeColor**</font>: 画笔颜色

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 000000FF
- 说明 : 设置当前的画笔颜色，颜色值为8位16进制

>###### <font color ='#42b983'>**strokeWidth**</font>: 画笔宽度

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 1
- 说明 : 设置画笔的宽度

>###### <font color ='#42b983'>**strokeCap**</font>: 笔触样式

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 0
- 说明 : 支持0：正方形,1：圆，默认值为0

>###### <font color ='#42b983'>**isFull**</font>: 是否填充

- 数据类型 : <font color ='#808000'>**Boolean**</font>
- 默认值 : true
- 说明 : 闭合图形是否填充内容，true：填充,false：不填充

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**definePoint**</font>: 定义点

- 参数:

  名称 | 类型 |是否必填|缺省值|说明
  ---- |-------------  |--------------|--------|------
  **points** |<font color ='#808000'>**object**</font> |  | 是|支持点的集合，如：[{x:x坐标,y:y坐标},{x:x1坐标,y:y1坐标}...]
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 支持画多点
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**defineLine**</font>: 定义线

- 参数:

  名称 | 类型 |是否必填|缺省值|说明
  ---- |-------------  |--------------|--------|------
  **start** |<font color ='#808000'>**object**</font> |  | 是|起始点坐标，如：{x:x坐标,x:y坐标}
  **end** |<font color ='#808000'>**object**</font> |  | 是|终点坐标，如：{x:x坐标,x:y坐标}
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 传入两点坐标，画一条直线
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**defineCircle**</font>: 定义圆

- 参数:

  名称 | 类型 |是否必填|缺省值|说明
  ---- |-------------  |--------------|--------|------
  **point** |<font color ='#808000'>**object**</font> |  | 是|圆心坐标，如：{x:x坐标,x:y坐标}
  **radius** |<font color ='#808000'>**number**</font> |  | 是|圆角半径
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**defineOval**</font>: 定义椭圆

- 参数:

  名称 | 类型 |是否必填|缺省值|说明
  ---- |-------------  |--------------|--------|------
  **start** |<font color ='#808000'>**object**</font> |  | 是|左上坐标，如：{x:x坐标,x:y坐标}
  **end** |<font color ='#808000'>**object**</font> |  | 是|右下坐标，如：{x:x坐标,x:y坐标}
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 通过左上坐标与右下坐标定义一个矩形，然后沿着矩形画内切椭圆
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**defineArc**</font>: 定义弧

- 参数:

  名称 | 类型 |是否必填|缺省值|说明
  ---- |-------------  |--------------|--------|------
  **start** |<font color ='#808000'>**object**</font> |  | 是|左上坐标，如：{x:x坐标,x:y坐标}
  **end** |<font color ='#808000'>**object**</font> |  | 是|右下坐标，如：{x:x坐标,x:y坐标}
  **startAngle** |<font color ='#808000'>**number**</font> | 0 | 否|如果为0默认与x轴重合
  **sweepAngle** |<font color ='#808000'>**number**</font> | 90 | 否|默认为90，以起始角度开始，顺时针扫描90度
  **useCenter** |<font color ='#808000'>**Boolean**</font> | true | 否|如果为true，这个弧的区域就会包含中心点
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**defineRect**</font>: 定义矩形

- 参数:

  名称 | 类型 |是否必填|缺省值|说明
  ---- |-------------  |--------------|--------|------
  **start** |<font color ='#808000'>**object**</font> |  | 是|左上坐标，如：{x:x坐标,x:y坐标}
  **end** |<font color ='#808000'>**object**</font> |  | 是|右下坐标，如：{x:x坐标,x:y坐标}
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 通过左上坐标与右下坐标定义一个矩形
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**defineText**</font>: 定义文字

- 参数:

  名称 | 类型 |是否必填|缺省值|说明
  ---- |-------------  |--------------|--------|------
  **text** |<font color ='#808000'>**string**</font> |  | 是|
  **coord** |<font color ='#808000'>**object**</font> | {x:0,y:0} | 否|从此坐标开始画，如：{x:x坐标,x:y坐标}
  **fontStyle** |<font color ='#808000'>**string**</font> | normal | 否|包含4种类型：normal：常规bold：粗体italic：斜体bold_italic：粗斜体（iOS平台不支持）
  **textFlag** |<font color ='#808000'>**string**</font> | normal | 否|包含3种类型：normal：常规underline ：下划线strikethrough ：删除线
  **fontSize** |<font color ='#808000'>**number**</font> | 17 | 否|
  **textAlign** |<font color ='#808000'>**string**</font> | left | 否|对齐方式为以下3种：left 左对齐（默认）；center 居中；right 右对齐。
  **angle** |<font color ='#808000'>**number**</font> | 0 | 否|如果为0默认与x轴重合
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 通过左上坐标与右下坐标定义一个矩形
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**defineImage**</font>: 定义图片

- 参数:

  名称 | 类型 |是否必填|缺省值|说明
  ---- |-------------  |--------------|--------|------
  **source** |<font color ='#808000'>**string**</font> |  | 是|支持do_Bitmap对象或data://开头的路径的图片地址
  **coord** |<font color ='#808000'>**object**</font> | {x:0,y:0} | 否|从此坐标开始画，如：{x:x坐标,x:y坐标}
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 设置一张图片作为背景
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**paint**</font>: 画

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 在Canvas上画出来
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**clear**</font>: 清空画布

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

>##### <font color ='#0092db'>**saveAsBitmap**</font>: 保存为Bitmap

- 参数:

  名称 | 类型 |是否必填|缺省值|说明
  ---- |-------------  |--------------|--------|------
  **bitmap** |<font color ='#808000'>**string**</font> |  | 是|
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 将整个view保存为一个Btimap
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件


