---
title: do_ALayout 组件
---

### do_ALayout 组件

 支持平台: iOS7.0,Android4.0
 UI组件，绝对布局(Absolute Layout),通过设置x,y来设置控件的绝对位置。这是DeviceOne平台提供的一个核心组件也是最重要的组件之一。
 绝对布局使用很简单，它内部的所有组件的布局都是绝对坐标值，不过这个坐标值是相对ALayout来说的，不是相对整个屏幕。
 如下图，按钮的x，y坐标都是100，是相对于按钮所在的ALayout的左上角
 ![](../../images/alayout.png)

#### <font color ='#40A977'>**1.**</font> 属性

>###### <font color ='#42b983'>**enabled**</font>: 是否可点击

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : true
- 说明 : 缺省为true，如果enable为true，则ALayout是可以点击的;否则不可点击,相应的事件也都不会触发.

>###### <font color ='#42b983'>**bgImage**</font>: 背景图片

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 :
- 说明 : 设置layout的背景图片，支持data://和source://两种方式；文件格式说明参考[文件管理](../../../应用开发/sections/文件管理)

>###### <font color ='#42b983'>**bgImageFillType**</font>: 背景图片填充方式

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : fillxy
- 说明 : 背景图片填充方式，缺省为fillxy。
    * fillxy:表示无论图片大小，图片会自动拉伸平铺满整个layout
    * repeatxy:表示图片不会有任何自动拉伸，根据layout大小会重复很多个图片

>###### <font color ='#42b983'>**isStretch**</font>: 是否自动拉伸

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : true
- 说明 : 通常ALayout包括ALayout内的所有组件都是按照设计器里设计的分辨率映射到手机屏幕的分辨率，按比例缩放的。为了确保不变形，可以通过设置这个属性来控制。详细可参考[屏幕适配](../../../应用开发/sections/屏幕适配)

>###### <font color ='#42b983'>**layoutAlign**</font>: 对齐方式

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : MiddelCenter
- 说明 : 这个属性只有当isStretch为false的时候才有意义。正如isStretch属性描述，如果设计器设计的区域分辨率宽高比和运行的手机宽高比不一致的时候，通过设置isStretch为false可以确保ALayout比例不变形，但是有可能会有空白区域，这个属性就是设置这个空白区的停靠方式。总共有如下几种对齐方式：
  * TopLeft：垂直居上，水平居左
  * TopCenter：垂直居上，水平居中
  * TopRight:垂直居上，水平居右
  * MiddleLeft:垂直居中，水平居左
  * MiddleCenter:垂直水平都居中
  * MiddleRight:垂直居中，水平居右
  * BottomLeft:垂直居下，水平居左
  * BottomCenter:垂直居下，水平居中
  * BottomRight:垂直居下，水平居右

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**add**</font>: 插入一个UI

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |------|------|------|------
  **id** |<font color ='#808000'>**string**</font> | 是||插入的ui组件在父容器的唯一标识
  **path** |<font color ='#808000'>**string**</font> | 是||插入的UI文件路径，支持data://和source://
  **x** |<font color ='#808000'>**string**</font> | 否||插入的ui组件相对ALayout的x 坐标,如果没有设置,则是这个ui组件旧的x坐标
  **y** |<font color ='#808000'>**string**</font> | 否||插入的ui组件相对ALayout的y 坐标,如果没有设置,则是这个ui组件旧的y坐标
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回这个ui文件对应的根节点view的地址
- 说明:
  * 可以在ALayout控件内在用户指定的x,y坐标上动态插入新的ui文件,实际是add这个ui文件的根节点对应的ui组件.
  * 这个ui文件可以有自己的脚本代码，但是和这个ui的所在Page共享一个[作用域](../../../应用开发/sections/数据共享和传递).详细用法包括插入的ui和主ui之间的数据交互参考[例子](https://github.com/do-api/docs-example/tree/master/source/view/do_ALayout)
  * 目前并不支持动态add一个ui对象,只支持add一个ui文件,ui文件本质是一个json字符串,你可以通过网络或其它方式动态生成这个json字符串,然后写入一个临时的ui文件,然后再add.
  * add之后的ui可以通过UI组件的基类方法[remove](../index.md)来删除,对应的ui资源会清除,但是add的ui文件对应的ui.js的js资源并不会清空. 如果需要不断的add和remove,可以尝试不使用remove,而是设置visiable为true和false来隐藏和显示.
- 示例:

  ```javascript
  var layout = ui("ALayout_1");

  // 把header.ui的根节点（是一个id为root的ALayout）加到当前index.ui的0，0位置
  // 并且重新给它命名一个新的唯一标示id "header_id", 这个id不要和index.ui里已有的ui组件的id重复
  var addedheader = layout.add("header_id", "source://view/do_ALayout/header.ui", 0, 0);

  // 获取header.ui的根节点对象（是一个id为root的ALayout），但是我们不能通过
  // var header = ui("root");来获取这个对象，因为root这个id的作用域是在header.ui,而不是在index.ui.js
  // 正确的写法是有2种，第一是：
  var header1 = ui("header_id");
  // 第二是：
  var header2 = ui(addedheader);
  // 判断这二个对象是否相同，可以通过getAddress方法
  nf.toast(header1.getAddress() == header2.getAddress());

  // 进一步我们还可以获取到header.ui根节点之下的子节点，比如statusbar是header.ui最上面的一部分组件的id
  var statusbar = ui(addedheader + ".statusbar");
  statusbar.bgColor = "FF0000FF";
  // 我们并不推荐在index.ui里直接获取header.ui 的子对象，这不符合降低耦合度的原则

  // index.ui不能直接调用header.ui里的函数，因为它们处于不同的js运行环境
  // 要实现这二者之间的数据交换，可以通过二种方式
  // 第一:通过数据bind，在header.ui.js里setmapping,然后通过binddata给header赋值
  var hashdata = mm("do_HashData");
  header1.bindData(hashdata);

  hashdata.addData({
  	"title_value" : "我是首页",
  	"menu_bg_value" : "FF0000FF"
  })
  header1.refreshData();

  // 第二：通过消息机制，订阅和触发消息都在page对象，因为header.ui和index.ui在同一page下
  page.on("click_menu", function(data) {
  	  nf.alert(data);
  })


  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**getChildren**</font>: 获取子view的id

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回一个JSON数组，类似['do_Button_1','do_Button_2']
- 说明: 获取当前组件内所有第一层子view的id<br>
  如果想遍历所有子view,可以判断子view的类型,如果子view是布局组件,可以继续getChildren
- 示例:

  ```javascript
  //获取所有子view的id
  var children = layout.getChildren();
  deviceone.print(children,typeof(children));
  deviceone.print(ui(children[0]).text,typeof(children[0]));

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <font color ='#e96900'>**touch**</font>: 点击事件

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述:
- 说明: 按下并在alayout范围抬起，触发该事件; enabled为false的时候无效
- 示例:

  ```javascript
   layout.on("touch",function(){
     deviceone.print("touch 触发")
   })

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**touchDown**</font>: 按下事件

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述:
- 说明: alayout范围内按下即可触发;必须先订阅toch事件才会有效果;enabled为false的时候无效
- 示例:

  ```javascript
  layout.on("touch",function(){
  	//do nothing
  })

  layout.on("touchDown",function(){
      deviceone.print("touchDown 触发")
  })

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**touchUp**</font>: 弹起事件

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述:
- 说明: 一旦按下，手指离开即触发，不论是否在alayout范围内;必须先订阅toch事件才会有效果;enabled为false的时候无效
- 示例:

  ```javascript
  layout.on("touch",function(){
  	//do nothing
  })

  layout.on("touchUp",function(){
      deviceone.print("touchUp 触发")
  })

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**longTouch**</font>: 长按事件

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述:
- 说明: 长按事件;必须先订阅toch事件才会有效果;enabled为false的时候无效
- 示例:

  ```javascript
  layout.on("touch",function(){
  	//do nothing
  })

  layout.on("longTouch",function(){
      deviceone.print("longTouch 触发")
  })

  ```

[回到顶部](#top)
