---
title: do_IndexListView 组件
---

### do_IndexListView 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_IndexListView)
 IndexListView实际上是一个界面右边带索引的ListView，可以绑定一个HashData数据源，按下滑动右边的索引，可以快速定位到该索引下的首条数据，主要应用于通讯录，歌曲播放器等界面

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#42b983'>属性</font>  |[indexBarColors](#indexBarColors)| 索引颜色
<font color ='#42b983'>属性</font>  |[selectedColor](#selectedColor)| Cell选中的背景颜色
<font color ='#42b983'>属性</font>  |[templates](#templates)| Cell对应的模板UI文件组
<font color ='#0092db'>同步方法</font>  |[bindItems](#bindItems)| 绑定item的数据
<font color ='#0092db'>同步方法</font>  |[refreshItems](#refreshItems)| 刷新item数据
<font color ='#e96900'>事件</font>  |[touch](#touch)| 点击cell触发
<font color ='#e96900'>事件</font>  |[longTouch](#longTouch)| 长按cell触发

#### <font color ='#40A977'>**1.**</font> 属性

>###### <span id=indexBarColors><font color ='#42b983'>**indexBarColors**</font></span>: 索引颜色

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 00000000,C0C0C0,000000,00000000
- 编辑类型 : 只允许设计区内修改
- 说明 : 包含四个颜色，分别是索引列表背景色、按下索引背景色、索引文本颜色、滑块颜色，中间用逗号隔开，仅android平台支持

>###### <span id=selectedColor><font color ='#42b983'>**selectedColor**</font></span>: Cell选中的背景颜色

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : ffffff00
- 说明 : 设置IndexListView 的按下选择颜色，如果在模板中设置了最底层ALayout的背景颜色，该属性将不起作用

>###### <span id=templates><font color ='#42b983'>**templates**</font></span>: Cell对应的模板UI文件组

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 无
- 编辑类型 : 只允许设计区内修改
- 说明 : 一个IndexListView可以有多个cell模板，这个属性包含多个source://开头的ui文件，中间用逗号隔开，格式类似如下：“source://view/cell1.ui,source://view/cell2.ui,source://view/cell3.ui”

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=bindItems><font color ='#0092db'>**bindItems**</font></span>: 绑定item的数据

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **data** |<font color ='#808000'>**object**</font> | 是 | |data里每个分组下第一条数据表示分组信息，不可点击
  **indexs** |<font color ='#808000'>**object**</font> | 否 | |一个数组列表，按照此列表显示列表数据，可以为空，为空就按照HashData‘随机’显示列表数据
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 为IndeListView绑定数据源，只支持HashData实例，其中每组第一条数据表示分组信息，不可点击。data参数格式如下：

  ```

  {
    "A":[
        {         //第一条数据表示分组信息，不可点击
            "template":0,
            "text":"A"
        },
        {
            "template":1,
            "tex":"a1"
        }
    ],
    "B":[
        {       //第一条数据表示分组信息，不可点击
            "template":0,
            "text":"B"
        },
        {
            "template":1,
            "tex":"b1"
        }
    ],
    ...
  }

  ```
  indexs参数格式如下：

  ```

  [
      "A",
      "B",
      "C",
      "E",
      "F",
      ...
  ]

  ```

- 示例:

  ```javascript

  var do_HashData = mm("do_HashData"); //实例化绑定的HashData数据源
  var index_arr = [];
  var _datas = {  //定义绑定的数组，即bindItems方法里的data参数
  	"A" : [ {
  		"template" : 0,
  		"text" : "A"
  	}, {
  		"template" : 1,
  		"Id" : "admin",
  		"icon" : "source://view/do_IndexListView/image/default.png",
  		"_choose" : "source://view/do_IndexListView/image/choose.png",
  		"text" : "管理员",
  		"Code" : "admin"
  	} ],
  	"B" : [ {
  		"template" : 0,
  		"text" : "B"
  	}, {
  		"template" : 1,
  		"Id" : "532c53ccc8ac4a12842436c39c1a1961",
  		"icon" : "source://view/do_IndexListView/image/default.png",
  		"_choose" : "source://view/do_IndexListView/image/choose.png",
  		"text" : "标签1",
  		"Code" : "12"
  	} ],
  	"J" : [ {
  		"template" : 0,
  		"text" : "J"
  	}, {
  		"template" : 1,
  		"Id" : "552ae6b3e15443acb89864db790dbab0",
  		"icon" : "source://view/do_IndexListView/image/default.png",
  		"_choose" : "source://view/do_IndexListView/image/choose.png",
  		"text" : "技术2",
  		"Code" : "6"
  	}, {
  		"template" : 1,
  		"Id" : "58b1149567794a0dac5b6ac15eeb17ef",
  		"icon" : "source://view/do_IndexListView/image/default.png",
  		"_choose" : "source://view/do_IndexListView/image/choose.png",
  		"text" : "技术1",
  		"Code" : "5"
  	} ]
  };
	for (var key in _datas){
		index_arr.push(key);   //处理绑定的索引数组即bindItems方法里的indexs参数
	}
	do_HashData.removeAll();
	do_HashData.addData(_datas);
	ui("do_IndexListView_1").bindItems(do_HashData,index_arr);
	ui("do_IndexListView_1").refreshItems();  //绑定数据后刷新

  ```
  绑定数据刷新后效果图如下：          
  <img src="../../images/IndexListView_binditem.png" height="350" width="330" >

[回到顶部](#top)

>##### <span id=refreshItems><font color ='#0092db'>**refreshItems**</font></span>: 刷新item数据

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 动态修改HashData数据源后，需要调用此方法才能正确显示数据
- 示例:刷新item数据，示例代码见上边bindItems示例代码里


[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=touch><font color ='#e96900'>**touch**</font></span>: 点击cell触发

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回data中的groupID和group下的数据index，比如{'groupID':'A','index':'2'}
- 说明: 点击cell触发
- 示例:

  ```javascript

  ui("do_IndexListView_1").on("touch","","1000",function(_data){
  	deviceone.print(JSON.stringify(_data),"点击事件")
  })
  //返回值如下
  {
    "groupID":"B",
    "index":1
  }

  ```

[回到顶部](#top)

>###### <span id=longTouch><font color ='#e96900'>**longTouch**</font></span>: 长按cell触发

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回data中的groupID和group下的数据index，比如{'groupID':'A','index':'2'}
- 说明: 长按cell触发
- 示例:

  ```javascript

  ui("do_IndexListView_1").on("longTouch",function(_data){
  	deviceone.print(JSON.stringify(_data),"长按事件")
  })
  //返回值如下
  {
    "groupID":"A",
    "index":1
  }

  ```

#### <font color ='#40A977'>**5.**</font> 常见问题


#### <font color ='#40A977'>**6.**</font> 基本配置

#### <font color ='#40A977'>**7.**</font> 更多示例

  - [仿微信主界面示例](https://github.com/do-project/code4do/tree/master/weixin)

[回到顶部](#top)
