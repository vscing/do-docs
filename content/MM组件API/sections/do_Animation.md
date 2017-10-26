---
title: do_Animation 组件
---

### do_Animation 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/MM/do_Animation)
 所有UI组件缩放，移动，透明度变化，旋转都支持动画效果。这个类就是用来定义动画所有属性值的集合，作为UI的animate方法的参数

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#42b983'>属性</font>  |[fillAfter](#fillAfter)| 是否保持动画的最后一帧在View上面
<font color ='#0092db'>同步方法</font>  |[alpha](#alpha)| 透明度动画
<font color ='#0092db'>同步方法</font>  |[transfer](#transfer)| 位移动画
<font color ='#0092db'>同步方法</font>  |[scale](#scale)| 缩放动画
<font color ='#0092db'>同步方法</font>  |[rotate](#rotate)| 旋转动画

#### <font color ='#40A977'>**1.**</font> 属性

>###### <span id=fillAfter><font color ='#42b983'>**fillAfter**</font></span>: 是否保持动画的最后一帧在View上面

- 数据类型 : <font color ='#808000'>**Boolean**</font>
- 默认值 :
- 说明 : 是否保持动画的最后一帧在View上面

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=alpha><font color ='#0092db'>**alpha**</font></span>: 透明度动画

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **data** |<font color ='#808000'>**object**</font> | 是 | |这是一个JSON node节点，包含多个参数，参数集合如下：
{
    'delay':'动画延迟时间（毫秒）',
    'duration':'动画过渡时间（毫秒）',
    'curve':'动画曲线类型四种情况：1.'EaseInOut'动画启动时候慢，中间快，结束的时候慢、2.'EaseIn'动画启动的时候慢、3.'EaseOut'动画结束的时候慢、4.'Linear'动画速度不变',
    'repeatCount':'动画重复次数，默认不重复，为-1时无限重复'
    'autoReverse':'是否自动动画反转',
    'alphaFrom':'起始透明值，取值0-1，0表示透明',
    'alphaTo':'结束透明值，取值0-1，0表示透明'
}


  **id** |<font color ='#808000'>**string**</font> | 否 | |每次调用这个函数都会创建一个新的动画属性集合，如果动画id一样，则会覆盖旧的动画属性值
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 设置透明动画的参数
- 示例:

  ```javascript
  do_Animation.alpha({
		delay:300,
		duration:2000,
		curve:4,
		repeatCount:2,
		autoReverse:true,
		alphaFrom:1,
		alphaTo:0
	}, "_a1");

  ```

[回到顶部](#top)

>##### <span id=transfer><font color ='#0092db'>**transfer**</font></span>: 位移动画

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **data** |<font color ='#808000'>**object**</font> | 是 | |这是一个JSON node节点的参数集合，包含以下参数：
{
    'delay':'动画延迟时间（毫秒）',
    'duration':'动画过渡时间（毫秒）',
    'curve':'动画曲线类型四种情况：1.'EaseInOut'动画启动时候慢，中间快，结束的时候慢、2.'EaseIn'动画启动的时候慢、3.'EaseOut'动画结束的时候慢、4.'Linear'动画速度不变',
    'repeatCount':'动画重复次数，默认不重复，为-1时无限重复'
    'autoReverse':'是否自动动画反转',
    'fromX':'起始x坐标',
    'fromY':'起始y坐标'，
    'toX':'结束x坐标',
    'toY':'结束y坐标'
}，其中fromx,fromy,tox,toy都是相对于当前组件的位置的值，而不是绝对值，比如100，表示当前坐标值加100，而不是绝对坐标100
  **id** |<font color ='#808000'>**string**</font> | 否 | |每次调用这个函数都会创建一个新的动画属性集合，如果动画id一样，则会覆盖旧的动画属性值
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: UI组件移动动画，从起点坐标到终点坐标
- 示例:

  ```javascript
  do_Animation.transfer({
		delay:1000,
		duration:2000,
		curve:4,
		repeatCount:2,
		autoReverse:true,
		fromX:0,
		fromY:60,
		toX:60,
		toY:120
	}, "_t1");

  ```

[回到顶部](#top)

>##### <span id=scale><font color ='#0092db'>**scale**</font></span>: 缩放动画

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **data** |<font color ='#808000'>**object**</font> | 是 | |这是一个JSON node节点的参数集合，包含以下参数：
{
    'delay':'动画延迟时间（毫秒）',
    'duration':'动画过渡时间（毫秒）',
    'curve':'动画曲线类型四种情况：1.'EaseInOut'动画启动时候慢，中间快，结束的时候慢、2.'EaseIn'动画启动的时候慢、3.'EaseOut'动画结束的时候慢、4.'Linear'动画速度不变',
    'repeatCount':'动画重复次数，默认不重复，为-1时无限重复'
    'autoReverse':'是否自动动画反转',
    'scaleFromX':'起始x的伸缩比例',
    'scaleFromY':'起始y的伸缩比例',
    'scaleToX':'结束x的伸缩比例',
    'scaleToY':'结束y的伸缩比例',
    'pivotX':'缩放起点x坐标，取值0-1',
    'pivotY':'缩放起点y坐标，取值0-1'
}


  **id** |<font color ='#808000'>**string**</font> | 否 | |每次调用这个函数都会创建一个新的动画属性集合，如果动画id一样，则会覆盖旧的动画属性值
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 设置UI组件按照比例缩放动画效果属性集合
- 示例:

  ```javascript
  do_Animation.scale({
		delay:300,
		duration:2000,
		curve:4,
		repeatCount:2,
		autoReverse:true,
		scaleFromX:1,
		scaleFromY:1,
		scaleToX:60,
		scaleToY:120,
		pivotX:0.2,
		pivotY:0.5
	}, "_s1");

  ```

[回到顶部](#top)

>##### <span id=rotate><font color ='#0092db'>**rotate**</font></span>: 旋转动画

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **data** |<font color ='#808000'>**object**</font> | 是 | |这是一个JSON node节点的参数集合，包含以下参数：
{
    'delay':'动画延迟时间（毫秒）',
    'duration':'动画过渡时间（毫秒）',
    'curve':'动画曲线类型四种情况：1.'EaseInOut'动画启动时候慢，中间快，结束的时候慢、2.'EaseIn'动画启动的时候慢、3.'EaseOut'动画结束的时候慢、4.'Linear'动画速度不变',
    'repeatCount':'动画重复次数，默认不重复，为-1时无限重复'
    'autoReverse':'是否自动动画反转',
    'fromDegree':'起始旋转角度，取值是±360',
    'toDegree':'结束旋转角度，取值是±360',
    'pivotX':'旋转中心点x坐标',
    'pivotY':'旋转中心点y坐标'
，其中pivotX、pivotY这两个值的取值范围为0-1，如果不设置表示旋转中心点是组件的右上角，设置成0.5选装中心点即为组件的中心点，设置成1旋转中心点是组件的右下角}
  **id** |<font color ='#808000'>**string**</font> | 否 | |每次调用这个函数都会创建一个新的动画属性集合，如果动画id一样，则会覆盖旧的动画属性值
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 设置UI组件旋转动画的属性集
- 示例:

  ```javascript
  do_Animation.rotate({
		delay:300,
		duration:2000,
		curve:4,
		repeatCount:2,
		autoReverse:true,
		fromDegree:0,
		fromDegree:60,
		pivotX:0.5,
		pivotY:1

	}, "_r1");

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件
