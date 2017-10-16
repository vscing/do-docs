---
title: do_RichLabel 组件
---

### do_RichLabel 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_RichLabel)
 富文本标签框，用于显示HTML标签内容，设置字体大小、高亮、超链接，默认只支持HTML一些基础标签。支持自定义a标签点击事件，href要以#打头点击时会触发linkTouch事件，例如：&lt;a href=#my&gt;DeviceOne&lt;a&gt;其他情况则不触发事件；如a标签href属性内容以http:或者https开头，会自动使用外部浏览器打开；以mail:打头，会自动使用外部邮箱打开；如果是tel:打头，会自动使用电话拨号打开；如果是sms:打头，会自动使用短信打开。Android要支持的标签更少一点，另外不支持css，总之不能把这个组件当成Webview组件来加载任意的html。只支持加载html内容，不支持直接加载一个html文件。Android下支持width，height都为-1，根据内容自动适应大小，ios只支持height为-1。

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#42b983'>属性</font>  |[maxHeight](#maxHeight)| 最大高度
<font color ='#42b983'>属性</font>  |[maxWidth](#maxWidth)| 最大宽度
<font color ='#42b983'>属性</font>  |[text](#text)| 文本显示内容
<font color ='#e96900'>事件</font>  |[linkTouch](#linkTouch)| 链接点击事件

#### <font color ='#40A977'>**1.**</font> 属性

>###### <span id=maxHeight><font color ='#42b983'>**maxHeight**</font></span>: 最大高度

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 :
- 编辑类型 : 只允许设计区内修改
- 说明 : label的height为－1的时候，label会根据text内容自动适配变高，但是不会高于maxHeight

>###### <span id=maxWidth><font color ='#42b983'>**maxWidth**</font></span>: 最大宽度

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 :
- 编辑类型 : 只允许设计区内修改
- 说明 : 设置文本框显示最大宽度值，只有在设置width属性值为-1时有效，否则不起作用；iOS平台不支持宽度设置为-1

>###### <span id=text><font color ='#42b983'>**text**</font></span>: 文本显示内容

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 :
- 说明 :  显示标签文本，说明：设置HTML标签显示富文本内容
- 示例 :

  ```javascript

    //实例化三个do_RichLabel组件
    var do_RichLabel_1 = ui("do_RichLabel_1");
    var do_RichLabel_2 = ui("do_RichLabel_2");
    var do_RichLabel_3 = ui("do_RichLabel_3");


    do_RichLabel_1.text = "<a href=\"http://www.deviceone.net\">Visit DeviceOne</a><h1>ljlkjljk</h1><a href = \"mailto:12345@126.com\">12345@126.com</a> jjjjjj <a href = \"tel:10086\">tel:10086</a> ddffeeff <a href = \"sms:10086\">sms:10086</a>";
    do_RichLabel_2.text = "<font color=red>This is a page with lots of URLs.</font> <a href=\"http://droidyue.com\">droidyue.com</a> "
    		+ "This left is a very good blog. There are so many great blogs there. You can find what you want in that blog."
    		+"<a href='#aaa' id='linktouch'> 点击我</a>";
    do_RichLabel_3.text = "<img src='http://www.w3school.com.cn/i/eg_tulip.jpg'  alt='上海鲜花港' /><img src='source://view/do_RichLabel/2.jpg'  alt='img1' />";


  ```
  三个do_RichLabel的效果图如下：

  <div align="center">

  <img src="../../images/do_RichLabel.png" height="330" width="310" >

  </div>

[回到顶部](#top)

#### <font color ='#40A977'>**2.**</font> 同步方法

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=linkTouch><font color ='#e96900'>**linkTouch**</font></span>: 链接点击事件

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 有时候用户需要在点击label里的某一段文字触发一个自定义的动作，比如&lt;a href='#aaa' id='xx'&gt; 点击我&lt;/a&gt; ，注意href的值必须是#开始。用户点击“点击我”这个link的时候会触发一个linkTouch事件，返回的data是一个JSON对象类型{value:'点击我' href:'#aaa', id:'xx'}。用户可以根据href的值不同case做不同的操作。
- 说明: 链接点击事件
- 示例:

  ```javascript

    //通过linkTouch和回调回来的d来确定richlabel里的自定义点击事件
    do_RichLabel_1.on("linkTouch",function(data){
    	deviceone.print(JSON.stringify(data),"linkTouch事件")
    })

    //返回值示例如下：
    {
        "text":"点击我",
        "href":"#aaa",
        "id":"linktouch"
    }


  ```

  
#### <font color ='#40A977'>**5.**</font> 常见问题

#### <font color ='#40A977'>**6.**</font> 基本配置

[回到顶部](#top)
