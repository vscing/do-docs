---
title: SM 组件
---

### SM 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/SM)
 所有单例组件的基类(父类),所有单例组件都继承这个组件的属性，事件，方法。
注意：定义自己的组件不能使用和基类名字一样的的属性、事件和方法。

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#0092db'>同步方法</font>  |[getType](#getType)| 获取类型
<font color ='#0092db'>同步方法</font>  |[getAddress](#getAddress)| 获取地址
<font color ='#0092db'>同步方法</font>  |[off](#off)| 取消订阅
<font color ='#0092db'>同步方法</font>  |[fire](#fire)| 触发消息
<font color ='#0092db'>异步方法</font>  |[on](#on)| 订阅消息

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=getType><font color ='#0092db'>**getType**</font></span>: 获取类型

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 类型ID
- 说明: 获取组件类型ID，用于判断一个对象的类型。比如

<pre class="brush: js;toolbar:false;">deviceone.print(sm("do_Global").getType()==="do_Global")</pre>
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=getAddress><font color ='#0092db'>**getAddress**</font></span>: 获取地址

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 组件地址,这个地址是用来区分一个组件的不同对象实例，但是SM组件是单例的，所以在任何地方获取SM对象的地址都是相同的。
注意：这个地址是原生地址，在js里打印会发现是一个带@符号的特殊字符串，比如

<pre class="brush: js;toolbar:false;">deviceone.print(sm("do_Global").getAddress());//值是类似"@abcdefg" 之类的字符串</pre>
- 说明: 获取组件地址
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
- 说明: 取消订阅消息,所有SM对象可以订阅消息也可以取消订阅，但是注意SM对象是单例，不会自动取消订阅，只能调用off方法去取消。

订阅可以重复，触发一次就会触发所有的订阅，取消订阅执行一次就把所有订阅都取消了。
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

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <span id=on><font color ='#0092db'>**on**</font></span>: 订阅消息

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **name** |<font color ='#808000'>**string**</font> | 是 | |
  **data** |<font color ='#808000'>**string**</font> | 否 | |回调函数function(data,e),第二个参数e.data就是这个值
  **delay** |<font color ='#808000'>**number**</font> | 否 | -1|如果值小于或等于0就直接响应事件
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 每一个组件都可以有自己的消息中心，可以订阅这个组件的自定义消息，消息机制的详细说明可以参考<a href="http://doc.deviceone.net/web/doc/detail_course/event_message.htm">文档</a>
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件


