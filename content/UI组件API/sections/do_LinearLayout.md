---
title: do_LinearLayout 组件
---

### do_LinearLayout 组件

 支持平台: iOS7.0,Android4.0
 线性布局，是DeviceOne提供的最基础的布局组件之一.
 意思就是里面的组件按线性排列，可以上下，可以左右排列。里面所有的子view的x，y没有意义，因为它们是一个接一个，无缝的拼接在一起。
 LinearLayout很少设置固定的高度和宽度，它最大的优势是可以动态根据内容来变化width和height,自适应大小，强制性地使视图扩展以便显示其全部内容，当height=-1时，表示自动高度，整个layout的高度是所有内部子控件的高之和。如果是横向布局的话，当width=-1时，所有内部组件横向方向顺序排列，宽度是所有子控件宽度之和.
 ![](../../images/linearlayout.png)

#### <font color ='#40A977'>**1.**</font> 属性

>###### <font color ='#42b983'>**direction**</font>: 布局方向

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : vertical
- 说明 : 支持2种方向布局，只允许修改ui文件里的属性,不能通过js代码动态修改：
  * horizontal：横向布局,从左到右布局
  * vertical：纵向布局,从上到下布局

>###### <font color ='#42b983'>**padding**</font>: 内边距

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 0,0,0,0
- 说明 : 0,0,0,0 分别表示上，右，下，左的内边距，通常只用于height和width为-1的情况.
margin是所有ui都具有的公共属性，但是它只能在Linearlayout里有效，所以在这里一起提一下。
padding就是在LinearLayout的内边距，margin就是LinearLayout里的一个子view和相邻的组件的距离，比如：
![](../../images/margin_padding.png)

>###### <font color ='#42b983'>**enabled**</font>: 是否可点击

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : true
- 说明 : 缺省为'true'，如果enable为true，则Layout是可以点击的，touch事件才有意义，否则不可点击

>###### <font color ='#42b983'>**bgImage**</font>: 背景图片

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 :
- 说明 : 可设置本地文件：支持data://和source://两种方式。文件格式说明参考[文件管理](../../../应用开发/sections/文件管理)

>###### <font color ='#42b983'>**bgImageFillType**</font>: 背景图片填充方式

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : fillxy
- 说明 : 背景图片填充方式，缺省为fillxy：
  * fillxy：拉伸图片（不按比例）以填充layout的宽高
  * repeatxy：按原图大小重复填充

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**add**</font>: 插入一个UI

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **id** |<font color ='#808000'>**string**</font> | 是 | |作为一个在父容器的唯一标识
  **path** |<font color ='#808000'>**string**</font> | 是 | |插入的ui对应的文件路径，支持data://和source://目录。
  **target** |<font color ='#808000'>**string**</font> | 否 | |要插入目标组件模块的id或者地址，插入的ui加在该组件的右面或者下面，不赋值表示加在LinearLayout最上面或左边。
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回这个ui文件对应的根节点view的地址
- 说明:

  * 可以在LinearLayout控件内某个相对位置上动态插入新的ui文件,实际是add这个ui文件的根节点对应的ui组件.
  * 这个ui文件可以有自己的脚本代码，但是和这个ui的所在Page共享一个[作用域](../../../应用开发/sections/数据共享和传递).详细用法包括插入的ui和主ui之间的数据交互参考[例子](https://github.com/do-api/docs-example/tree/master/source/view/do_LinearLayout)
  * 目前并不支持动态add一个ui对象,只支持add一个ui文件,ui文件本质是一个json字符串,你可以通过网络或其它方式动态生成这个json字符串,然后写入一个临时的ui文件,然后再add.
  * add之后的ui可以通过UI组件的基类方法[remove](../index.md)来删除,对应的ui资源会清除,但是add的ui文件对应的ui.js的js资源并不会清空. 如果需要不断的add和remove,可以尝试不使用remove,而是设置visiable为true和false来隐藏和显示.
- 示例:

  ```javascript
  add.on("touch", function() {
  	// 插入到“第二个组件”下
  	// add函数返回是新加ui的地址，
  	// add 的参数1是表示加进来的ui在index.ui里的唯一标示，必须和index.ui其他view的id不一样
  	var newui = linearlayout.add("added_ui_id" + i, "source://view/do_LinearLayout/test.ui",
  			"do_Button_1");
  	// ui("added_ui_id" + i)===ui(newui)

  	// label是新加进去来的ui文件里的一个子view,可以通过这种方式获取到子view的对象
  	var label = ui(newui + ".do_Label_1");
  	label.text = "我是add进来的" + i;

  	newui = ui("added_ui_id" + i);
  	newui.width = newui.width + 10 * i;
  	i++;

  });

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**getChildren**</font>: 获取子view的id

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回一个JSON数组，类似['do_Button_1','do_Button_2']
- 说明: 获取当前组件内所有第一层子view的id
- 示例:

  ```javascript
  //获取所有子view的id
  var children = linearlayout.getChildren();
  deviceone.print(children,typeof(children));
  deviceone.print(ui(children[0]).text,typeof(children[0]));

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <font color ='#e96900'>**touch**</font>: 点击触发

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述:
- 说明: enabled为false的时候无效
- 示例:

  ```javascript
  linearlayout.on("touch",function(){
  	deviceone.print("touch 触发")
  })

  ```

[回到顶部](#top)
