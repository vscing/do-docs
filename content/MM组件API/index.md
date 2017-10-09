---
title: MM 组件
---

### MM 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/MM)
 所有多例组件的基类(父类),所有多例组件都继承这个组件的属性，事件，方法。所谓多例就是可以一个组件多次实例化，可以构建多个对象，这些对象是有作用域区分的，关于作用域的结束参考<a href="http://doc.deviceone.net/web/doc/detail_course/data_save_transfer.htm">文档</a><br />注意：定义自己的组件不能使用和基类名字一样的的属性、事件和方法。<br /><br />创建实例或者获取实例的方法是mm()函数，这个函数有三个参数(MM类型,MM的标示id,MM的作用域)，比如<br /><pre class="brush: js;toolbar:false;">
//表示在app作用域内创建一个do_Animation对象
var animation1 = mm('do_Animation','id1','app')；

//表示在app作用域里返回id为id1的do_Animation的组件，这里animation2==animation1
var animation2 = mm('do_Animation','id1','app')；
</pre><br /><br />表示在app作用域内创建一个do_Animation对象，再执行同样一句代码就不再表示创建新的，而是直接返回旧的，其中MM的作用域参数是一个枚举类型，目前包括两种'app'，'page'，如果不设置值则表示page作用域，mm函数后2个参数是可选参数，第一个是必填参数，关于MM类和mm函数的说明也可以参考<a href="http://doc.deviceone.net/web/doc/detail_course/modules.htm">文档</a><br />

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#0092db'>同步方法</font>  |[getType](#getType)| 获取类型
<font color ='#0092db'>同步方法</font>  |[getAddress](#getAddress)| 获取地址
<font color ='#0092db'>同步方法</font>  |[off](#off)| 取消订阅
<font color ='#0092db'>同步方法</font>  |[fire](#fire)| 触发消息
<font color ='#0092db'>同步方法</font>  |[get](#get)| 获取属性值
<font color ='#0092db'>同步方法</font>  |[set](#set)| 设置属性
<font color ='#0092db'>同步方法</font>  |[bindData](#bindData)| 绑定
<font color ='#0092db'>同步方法</font>  |[setMapping](#setMapping)| 设置和数据源的映射关系
<font color ='#0092db'>同步方法</font>  |[refreshData](#refreshData)| 刷新数据
<font color ='#0092db'>同步方法</font>  |[loadSync](#loadSync)| 加载配置文件或者字符串
<font color ='#0092db'>同步方法</font>  |[release](#release)| 释放MM对象
<font color ='#0092db'>异步方法</font>  |[on](#on)| 订阅消息
<font color ='#0092db'>异步方法</font>  |[load](#load)| 加载配置文件或者字符串
<font color ='#e96900'>事件</font>  |[dataRefreshed](#dataRefreshed)| 当对象获取到数据会触发,详细的文档参考<a href="http://doc.deviceone.net/web/doc/detail_course/databind.htm">数据绑定</a>

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=getType><font color ='#0092db'>**getType**</font></span>: 获取类型

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 类型ID
- 说明: 获取组件类型ID，用于判断一个对象的类型。比如<br /><pre class="brush: js;toolbar:false;">
var http = mm("do_Http");
deviceone.print(http.getType()=="do_Http");
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
var http1 = mm("do_Http");
deviceone.print(http1.getAddress());//值是类似\"@abcdefg\" 之类的字符串
var http2 = mm(http1.getAddress());//根据地址获取对象，这里http1和http2指向同样的对象
</pre><br />
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
- 返回值描述: 返回属性的一个JSON Object格式，其中key是属性名，value是属性值
- 说明: 除了单独获取一个属性值外，可以通过这个方法获取一个MM组件的多个属性的属性值，比如<br /><br /><pre class="brush: js;toolbar:false;">
	var http1 = mm("do_Http");
	http1.url = "http://www.baidu.com";
	http1.method = "GET";
	http1.timeout = 30000;
	var feature_name = ["url","method","timeout"];
	var feature_value = http1.get(feature_name);
	deviceone.print(JSON.stringify(feature_value));//打印出{"url":"http://www.baidu.com","method":"GET","timeout":30000}
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
  **data** |<font color ='#808000'>**object**</font> | 否 | |多个属性名和它的值合并的JSON Object对象
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 除了单独设置一个属性值外，可以通过这个方法设置一个MM组件的多个属性的属性值，比如
<pre class="brush: js;toolbar:false;">
	var http1 = mm("do_Http");
	var values = {
		"url" : "http://www.baidu.com",
		"method" : "GET",
		"timeout" : 30000
	}
	http1.set(values);
	deviceone.print(http1.url);
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
  **data** |<font color ='#808000'>**string**</font> | 是 | |这个data只能是do_HashData和do_ListData的实例
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
- 说明: bind方法可以指定mapping，而这个方法是设置缺省的映射关系，如果bind方法传递的mapping参数为空，则使用这个缺省的映射关系.<br />详细的文档参考<a href="http://doc.deviceone.net/web/doc/detail_course/databind.htm">数据绑定</a>
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

>##### <span id=loadSync><font color ='#0092db'>**loadSync**</font></span>: 加载配置文件或者字符串

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **source** |<font color ='#808000'>**string**</font> | 是 | |
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 通过加载一个json文件或json字符串来构建Model实例的数据
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=release><font color ='#0092db'>**release**</font></span>: 释放MM对象

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 调用该方法可将一个MM对象彻底释放
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
- 说明: 每一个组件都可以有自己的消息中心，可以订阅这个组件的自定义消息，消息机制的详细说明可以参考<a href="http://doc.deviceone.net/web/doc/detail_course/event_message.htm">文档</a>
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=load><font color ='#0092db'>**load**</font></span>: 加载配置文件或者字符串

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **source** |<font color ='#808000'>**string**</font> | 是 | |
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 通过加载一个json文件或字符串来构建Model实例的数据
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


