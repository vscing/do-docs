---
title: UI 组件
---

### UI 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/UI)
 所有UI组件的基类(父类),所有UI组件都继承这个组件的属性，事件，方法。所谓UI组件就是可以在设计器可视化布局的组件。<br />注意：定义自己的组件不能使用和基类名字一样的的属性、事件和方法。<br /><br />UI组件不能直接实例化，通常是从ui文件里根据组件的id获取到对象，类似getElementById，获取实例的方法是ui()函数，比如<br /><pre class="brush: js;toolbar:false;">
var button1 = ui("do_Button_id1")；
</pre><br /><br />关于UI组件和ui函数的说明也可以参考<a href="http://doc.deviceone.net/web/doc/detail_course/modules.htm">文档</a><br />

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#42b983'>属性</font>  |[id](#id)| UI组件的ID
<font color ='#42b983'>属性</font>  |[x](#x)| x坐标值
<font color ='#42b983'>属性</font>  |[y](#y)| y坐标值
<font color ='#42b983'>属性</font>  |[width](#width)| Number
<font color ='#42b983'>属性</font>  |[height](#height)| Number
<font color ='#42b983'>属性</font>  |[visible](#visible)| 是否可见
<font color ='#42b983'>属性</font>  |[bgColor](#bgColor)| 背景颜色
<font color ='#42b983'>属性</font>  |[tag](#tag)| UI组件的tag
<font color ='#42b983'>属性</font>  |[margin](#margin)| 外边距
<font color ='#42b983'>属性</font>  |[type](#type)| 类型ID
<font color ='#42b983'>属性</font>  |[border](#border)| 边框
<font color ='#42b983'>属性</font>  |[alpha](#alpha)| 组件透明度
<font color ='#0092db'>同步方法</font>  |[getType](#getType)| 获取类型
<font color ='#0092db'>同步方法</font>  |[getAddress](#getAddress)| 获取地址
<font color ='#0092db'>同步方法</font>  |[getRect](#getRect)| 获取UI矩形
<font color ='#0092db'>同步方法</font>  |[off](#off)| 取消订阅
<font color ='#0092db'>同步方法</font>  |[fire](#fire)| 触发消息
<font color ='#0092db'>同步方法</font>  |[get](#get)| 获取属性值
<font color ='#0092db'>同步方法</font>  |[set](#set)| 设置属性
<font color ='#0092db'>同步方法</font>  |[bindData](#bindData)| 绑定
<font color ='#0092db'>同步方法</font>  |[setMapping](#setMapping)| 设置和数据源的映射关系
<font color ='#0092db'>同步方法</font>  |[redraw](#redraw)| 重画组件
<font color ='#0092db'>同步方法</font>  |[remove](#remove)| 删除自身
<font color ='#0092db'>同步方法</font>  |[refreshData](#refreshData)| 刷新数据
<font color ='#0092db'>异步方法</font>  |[on](#on)| 订阅消息
<font color ='#0092db'>异步方法</font>  |[animate](#animate)| 动画
<font color ='#0092db'>异步方法</font>  |[show](#show)| 组件显示动画
<font color ='#0092db'>异步方法</font>  |[hide](#hide)| 组件隐藏动画
<font color ='#e96900'>事件</font>  |[dataRefreshed](#dataRefreshed)| 当对象获取到数据会触发,详细的文档参考<a href="http://doc.deviceone.net/web/doc/detail_course/databind.htm">数据绑定</a>

#### <font color ='#40A977'>**1.**</font> 属性

>###### <span id=id><font color ='#42b983'>**id**</font></span>: UI组件的ID

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 : 

>###### <span id=x><font color ='#42b983'>**x**</font></span>: x坐标值

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 0
- 说明 : 基于父容器的x轴坐标位置

>###### <span id=y><font color ='#42b983'>**y**</font></span>: y坐标值

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 0
- 说明 : 基于父容器的y轴坐标位置

>###### <span id=width><font color ='#42b983'>**width**</font></span>: Number

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 100
- 说明 : 组件的宽度

>###### <span id=height><font color ='#42b983'>**height**</font></span>: Number

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 80
- 说明 : 组件的高度

>###### <span id=visible><font color ='#42b983'>**visible**</font></span>: 是否可见

- 数据类型 : <font color ='#808000'>**Boolean**</font>
- 默认值 : true
- 说明 : 

>###### <span id=bgColor><font color ='#42b983'>**bgColor**</font></span>: 背景颜色

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 00000000
- 说明 : 颜色值 8位16进制

>###### <span id=tag><font color ='#42b983'>**tag**</font></span>: UI组件的tag

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 : 

>###### <span id=margin><font color ='#42b983'>**margin**</font></span>: 外边距

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 0,0,0,0
- 说明 : 和父容器（必须是LinearLayout）的上，右，下，左边距

>###### <span id=type><font color ='#42b983'>**type**</font></span>: 类型ID

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 : 不可修改，通过getType()方法获取

>###### <span id=border><font color ='#42b983'>**border**</font></span>: 边框

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 : 属性值格式有两种，一种是“颜色，宽度，圆角”，比如'FF9999FF,1,20'，其中这个属性如果为空，则没有border效果；另一种是“颜色，宽度，[左上圆角,右上圆角,右下圆角,左下圆角]”，可单独设置四个角的圆角效果；windows平台不支持；若该属性设置在ImageVIew上，则只支持四个角相同，否则只取第一个值作为四边的圆角

>###### <span id=alpha><font color ='#42b983'>**alpha**</font></span>: 组件透明度

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 1
- 说明 : 设置组件透明度，若组件为一个容器类组件，则里面所有子组件的透明度一起变化，范围为0~1；当跟bgColor的透明度冲突时以后设置的为准

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=getType><font color ='#0092db'>**getType**</font></span>: 获取类型

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 类型ID
- 说明: 获取组件类型ID，用于判断一个对象的类型。比如<br /><br /><pre class="brush: js;toolbar:false;">
var button = ui("do_Button_id1");
deviceone.print(button.getType()=="do_Button");
</pre>
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=getAddress><font color ='#0092db'>**getAddress**</font></span>: 获取地址

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 组件地址
- 说明: 获取组件地址,这个地址是用来区分一个组件的不同对象实例<br />注意：这个地址是原生地址，在js里打印会发现是一个带@符号的特殊字符串，比如<br /><br /><pre class="brush: js;toolbar:false;">
var button1 = mm("do_Button");
deviceone.print(button1.getAddress());//值是类似\"@abcdefg\" 之类的字符串
var button2 = mm(button1.getAddress());//根据地址获取对象，这里button1和button2指向同样的对象
</pre><br />
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=getRect><font color ='#0092db'>**getRect**</font></span>: 获取UI矩形

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 组件矩形｛x:Number,y:Number,width:Number,height:Number｝
- 说明: 获取UI组件在设备上显示的矩形真实大小，包括x，y，width，height。这几个值和UI对应的x,y,width,height属性的值有可能不一致
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=off><font color ='#0092db'>**off**</font></span>: 取消订阅

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **name** |<font color ='#808000'>**string**</font> | 是 | |
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 取消订阅消息,所有MM对象可以订阅消息也可以取消订阅，<br />订阅可以重复，触发一次就会触发所有的订阅，取消订阅执行一次就把所有订阅都取消了。
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=fire><font color ='#0092db'>**fire**</font></span>: 触发消息

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **name** |<font color ='#808000'>**string**</font> | 是 | |
  **data** |<font color ='#808000'>**string**</font> | 否 | |
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 消息机制的详细说明可以参考<a href="http://doc.deviceone.net/web/doc/detail_course/event_message.htm">文档</a>
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=get><font color ='#0092db'>**get**</font></span>: 获取属性值

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **data** |<font color ='#808000'>**object**</font> | 是 | |一组属性名对应的JSON Array对象
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回属性的一个json node格式，其中key是属性名，value是属性值
- 说明: 除了单独获取一个属性值外，可以通过这个方法获取一个UI组件的多个属性的属性值，比如<br /><br /><pre class="brush: js;toolbar:false;">
	var button = ui("btn_hello");
	button.x = 100;
	button.height = 200;
	button.text = "test";
	var feature_name = [ "x", "height", "text" ];
	var feature_value = button.get(feature_name);
	deviceone.print(JSON.stringify(feature_value));//打印出{"x":100,"height":200,"text":"test"}
</pre>
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=set><font color ='#0092db'>**set**</font></span>: 设置属性

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **data** |<font color ='#808000'>**object**</font> | 否 | |多个属性名和它的值合并的json node
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 除了单独获取一个属性值外，可以通过这个方法获取一个UI组件的多个属性的属性值，比如<br /><br /><pre class="brush: js;toolbar:false;">
	var button = ui("btn_hello");
	button.x = 100;
	button.height = 200;
	button.text = "test";
	var feature_name = [ "x", "height", "text" ];
	var feature_value = button.get(feature_name);
	deviceone.print(JSON.stringify(feature_value));//打印出{"x":100,"height":200,"text":"test"}
</pre>
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=bindData><font color ='#0092db'>**bindData**</font></span>: 绑定

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **data** |<font color ='#808000'>**string**</font> | 是 | |这个data只能是HashData和ListData的实例
  **mapping** |<font color ='#808000'>**object**</font> | 否 | |可以同时映射多个数据值到不同的属性上
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 利用HashData和ListData绑定对象到一个数据源，详细的文档参考<a href="http://doc.deviceone.net/web/doc/detail_course/databind.htm">数据绑定</a> 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=setMapping><font color ='#0092db'>**setMapping**</font></span>: 设置和数据源的映射关系

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **data** |<font color ='#808000'>**object**</font> | 否 | |可以同时映射多个数据值到不同的属性上
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: bind方法可以指定mapping，而这个方法是设置缺省的映射关系，如果bind方法传递的mapping参数为空，则使用这个缺省的映射关系.详细的文档参考<a href="http://doc.deviceone.net/web/doc/detail_course/databind.htm">数据绑定</a>
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=redraw><font color ='#0092db'>**redraw**</font></span>: 重画组件

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 重画组件，当组件的x，y、width，height, visible或者margin修改的时候，需要调用自身的redraw方法才能生效。<br />还有一些组件在一些特殊情况下,比如添加，删除一个子View或修改了内容，都有可能需要调用redraw重画。<br />这样设计的好处在于，如果一个父View里面有多个子View，每个子View都做了这几个属性的修改，然后再调用父View的redraw方法，比每一个组件自动的重新绘制，可以节省很多重绘制的次数，提高效率。比如<br /><br /><pre class="brush: js;toolbar:false;">
var child1 = ui("child_view_id1");
var child2 = ui("child_view_id2");
var child3 = ui("child_view_id3");
child1.x = child1.x+10;
child2.width = 22;
child3.visible = false;
parent.redraw();//parent是child1,child2,child3的父容器
</pre>
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=remove><font color ='#0092db'>**remove**</font></span>: 删除自身

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 把自身从父容器中删除
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=refreshData><font color ='#0092db'>**refreshData**</font></span>: 刷新数据

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 详细的文档参考<a href="http://doc.deviceone.net/web/doc/detail_course/databind.htm">数据绑定</a>
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <span id=on><font color ='#0092db'>**on**</font></span>: 订阅消息

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **name** |<font color ='#808000'>**string**</font> | 是 | |
  **data** |<font color ='#808000'>**string**</font> | 否 | |回调函数function(data,e,self),第二个参数e.data就是这个值
  **delay** |<font color ='#808000'>**number**</font> | 否 | -1|如果值小于或等于0就直接响应事件
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 每一个组件都可以有自己的消息中心，可一订阅这个组件的消息
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=animate><font color ='#0092db'>**animate**</font></span>: 动画

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **animation** |<font color ='#808000'>**string**</font> | 否 | |参数是model组件Animation一个实例的地址
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 每一个UI组件都支持一些属性变化的动画效果
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=show><font color ='#0092db'>**show**</font></span>: 组件显示动画

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **animationType** |<font color ='#808000'>**string**</font> | 否 | |目前支持以下几种：
'slide_l2r': 从左至右滑出
'slide_r2l': 从右至左滑出
'slide_b2t': 从底至上滑出
'slide_t2b': 从上至底滑出
'expand_l2r': 从左至右展开
'expand_t2b': 从上至底展开
'fadein' : 淡入淡出

  **animationTime** |<font color ='#808000'>**number**</font> | 否 | 300|单位为毫秒
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: UI组件被加载后可通过show方法增加动画来显示，若UI组件已是显示状态，再调该方法没有动画效果，默认没有动画
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=hide><font color ='#0092db'>**hide**</font></span>: 组件隐藏动画

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **animationType** |<font color ='#808000'>**string**</font> | 否 | |目前支持以下几种：
'slide_l2r': 从左至右滑出
'slide_r2l': 从右至左滑出
'slide_b2t': 从底至上滑出
'slide_t2b': 从上至底滑出
'collapse_r2l': 从右至左合拢
'collapse_b2t': 从底至上合拢
'fadeout' : 淡入淡出

  **animationTime** |<font color ='#808000'>**number**</font> | 否 | 300|单位为毫秒
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: UI组件被加载后可通过show方法增加动画来隐藏，若UI组件已是隐藏状态，再调该方法没有动画效果；默认没有动画效果
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=dataRefreshed><font color ='#e96900'>**dataRefreshed**</font></span>: 当对象获取到数据会触发,详细的文档参考<a href="http://doc.deviceone.net/web/doc/detail_course/databind.htm">数据绑定</a>

- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回获取到的数据
- 说明: 当对象获取到数据会触发,详细的文档参考<a href="http://doc.deviceone.net/web/doc/detail_course/databind.htm">数据绑定</a>
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


