---
title: do_RichLabel 组件
---

### do_RichLabel 组件

 支持平台: iOS7.0,Android4.0
 富文本标签框，用于显示HTML标签内容，设置字体大小、高亮、超链接，默认只支持HTML一些基础标签。<br /><br />支持自定义a标签点击事件，href要以#打头，点击时会触发linkTouch事件，例如：&lt;a href=#my&gt;DeviceOne&lt;a&gt;其他情况则不触发事件；<br /><br />如a标签href属性内容以http:或者https开头，会自动使用外部浏览器打开；以mail:打头，会自动使用外部邮箱打开；如果是tel:打头，会自动使用电话拨号打开<br /><br />Android要支持的标签更少一点，另外不支持css，总之不能把这个组件当成Webview组件来加载任意的html。<br /><br />只支持加载html内容，不支持直接加载一个html文件。<br /><br />Android下支持width，height都为-1，根据内容自动适应大小，ios只支持height为-1.<br />

#### <font color ='#40A977'>**1.**</font> 属性

>###### <font color ='#42b983'>**maxHeight**</font>: 最大高度

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 
- 说明 : label的height为－1的时候，label会根据text内容自动适配变高，但是不会高于maxHeight

>###### <font color ='#42b983'>**maxWidth**</font>: 最大宽度

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 
- 说明 : 设置文本框显示最大宽度值，只有在设置width属性值为-1时有效，否则不起作用；iOS平台不支持宽度设置为-1

>###### <font color ='#42b983'>**text**</font>: 文本显示内容

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 :  显示标签文本，说明：设置HTML标签显示富文本内容

#### <font color ='#40A977'>**2.**</font> 同步方法

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <font color ='#e96900'>**linkTouch**</font>: 链接点击事件

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 有时候用户需要在点击label里的某一段文字触发一个自定义的动作，比如&lt;a href='#aaa' id='xx'&gt; 点击我&lt;/a&gt; ，注意href的值必须是#开始<br />则用户点击“点击我”这个link的时候会触发一个linkTouch事件，返回的data是一个JSON对象类型<br /><br />{value:'点击我' href:'#aaa', id:'xx'}<br /><br />用户可以根据href的值不同case做不同的操作<br /><br /><pre class="brush: js;toolbar:false;">
//text的值是<a href="#my">自定义事件</a>
//通过linkTouch和回调回来的d来确定richlabel里的自定义点击事件
label.on("linkTouch",function(d){
	nf.alert("自定义事件:"+JSON.stringify(d));
});
</pre><br /><br />
- 说明: 链接点击事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


