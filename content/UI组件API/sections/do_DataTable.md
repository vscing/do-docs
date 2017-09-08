---
title: do_DataTable 组件
---

### do_DataTable 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_DataTable)
 类似于Excel表格，展示对应的二维数据表，可以支持自定义的样式设置,可支持上下左右滑动查看，也可支持固定列的锁定。当表头列数与数据列数无法匹配时，确定显示列数的顺序为：1.HeaderData、2.HeaderStyle、3.RowData

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#42b983'>属性</font>  |[isHeaderVisible](#isHeaderVisible)| 是否显示表头
<font color ='#42b983'>属性</font>  |[freezeColumn](#freezeColumn)| 冻结的列个数
<font color ='#0092db'>同步方法</font>  |[setHeaderStyle](#setHeaderStyle)| 设置表头样式
<font color ='#0092db'>同步方法</font>  |[setHeaderData](#setHeaderData)| 设置表头数据
<font color ='#0092db'>同步方法</font>  |[setRowStyle](#setRowStyle)| 设置数据样式
<font color ='#0092db'>同步方法</font>  |[setRowData](#setRowData)| 设置表格数据
<font color ='#0092db'>同步方法</font>  |[setCellDatas](#setCellDatas)| 设置单元格属性
<font color ='#e96900'>事件</font>  |[longTouch](#longTouch)| 长按单元格触发
<font color ='#e96900'>事件</font>  |[touch](#touch)| 点击单元格触发

#### <font color ='#40A977'>**1.**</font> 属性

>###### <span id=isHeaderVisible><font color ='#42b983'>**isHeaderVisible**</font></span>: 是否显示表头

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : true
- 说明 : 如果显示表头的话，表头是不会随表格上下滑动的时候滑动的
- 示例 :

```javascript

  // 实例化
  var do_DataTable = ui("do_DataTable_1");

  //表头不显示
  do_DataTable.isHeaderVisible = false;

  //表头显示
  do_DataTable.isHeaderVisible = true;

```
>###### <span id=freezeColumn><font color ='#42b983'>**freezeColumn**</font></span>: 冻结的列个数

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 1
- 编辑类型 : 只允许设计区内修改。
- 说明 : 只允许从左到右数起的列被冻结，左右滑动的时候固定不动

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=setHeaderStyle><font color ='#0092db'>**setHeaderStyle**</font></span>: 设置表头样式

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **width** |<font color ='#808000'>**string**</font> | 否 | 100|可以全局设置，如：100; 也可以支持对每列设置，格式为一个JsonArray，如：[100,50,40,50]，需与表头列数对应
  **height** |<font color ='#808000'>**string**</font> | 否 | 80|
  **bgColor** |<font color ='#808000'>**string**</font> | 否 | 00000000|设置背景显示颜色，值格式为：8位16进制字符，前6位是RGB颜色值，后两位是透明度（Alpha），例如：000000FF
  **fontColor** |<font color ='#808000'>**string**</font> | 否 | 000000FF|设置字体显示颜色，值格式为：8位16进制字符，前6位是RGB颜色值，后两位是透明度（Alpha），例如：000000FF
  **fontStyle** |<font color ='#808000'>**string**</font> | 否 | normal|包含4种类型：normal：常规bold：粗体italic：斜体bold_italic：粗斜体（iOS平台不支持）
  **textFlag** |<font color ='#808000'>**string**</font> | 否 | normal|包含3种类型：normal：常规underline ：下划线strikethrough ：删除线
  **fontSize** |<font color ='#808000'>**number**</font> | 否 | 17|
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明:
- 示例:

  ```javascript

  //1.宽度格式为JsonArray格式
  //（设置表头每列宽度不一,高度80,背景红色,字体蓝色,斜体,常规字体大小26）
  do_DataTable.setHeaderStyle(
    [
      "70",
      "100",
      "100",
      "100",
      "100",
      "100",
      "100",
      "100"
    ],
    "80",
    "FF0000FF",
    "FFFFFFFF",
    "italic",
    "normal",
    26
  );
do_DataTable.setRowData([]); //所有的样式设置完必须再掉一次setRowData


  //宽度格式为字符串格式
  //设置表头每列宽度100,高度100,背景透明度为50的红色,字体为蓝色,粗斜体,删除线,字体大小26）
  do_DataTable.setHeaderStyle(
    "100",
    "80",
    "FF000050",
    "0080FFFF",
    "bold_italic",
    "strikethrough",
    26
  );
do_DataTable.setRowData([]);//所有的样式设置完必须再掉一次setRowData

  ```

[回到顶部](#top)

>##### <span id=setHeaderData><font color ='#0092db'>**setHeaderData**</font></span>: 设置表头数据

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **data** |<font color ='#808000'>**object**</font> | 是 | |无
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明:格式如下：
  ```
  ["姓名","性别","年龄"...]

  ```

- 示例:

  ```javascript

  do_DataTable.setHeaderData([
      "课程",
      "周一",
      "周二",
      "周三",
      "周四",
      "周五",
      "周六",
      "周天"
  ]);
	do_DataTable.setRowData([]);//所有的样式设置完必须再掉一次setRowData

  ```

[回到顶部](#top)

>##### <span id=setRowStyle><font color ='#0092db'>**setRowStyle**</font></span>: 设置数据样式

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **height** |<font color ='#808000'>**string**</font> | 否 | 80|
  **bgColor** |<font color ='#808000'>**object**</font> | 否 | [“00000000”]|设置背景显示颜色，值格式为：8位16进制字符，前6位是RGB颜色值，后两位是透明度（Alpha），例如：000000FF，可以支持2个颜色，也可以支持一个颜色，2个颜色比如[“000000FF”,“FFFFFFFF”]表示奇数偶数行的背景色是可以不同的
  **fontColor** |<font color ='#808000'>**string**</font> | null | 000000FF|设置字体显示颜色，值格式为：8位16进制字符，前6位是RGB颜色值，后两位是透明度（Alpha），例如：000000FF
  **fontStyle** |<font color ='#808000'>**string**</font> | null | normal|包含4种类型：normal：常规bold：粗体italic：斜体bold_italic：粗斜体（iOS平台不支持）
  **textFlag** |<font color ='#808000'>**string**</font> | null | normal|包含3种类型：normal：常规underline ：下划线strikethrough ：删除线
  **fontSize** |<font color ='#808000'>**number**</font> | null | 17|
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明:注：设置数据样式后，需要在重新设置表格数据,即调用do_DataTable.setRowData()设置数据，否则设置样式会不起作用;
- 示例:

  ```javascript

  do_DataTable.setRowStyle("80", ["0080FFFF","FF0000FF"], "FFFFFFFF", "normal", "normal",30);
	var lists = [
     		[ "1", "班级会", "数学", "数学", "化学", "音乐", "化学","物理" ],
     		[ "2", "语文", "语文", "地理", "数学", "美术", "生物","数学" ],
     		[ "3", "英语", "体育", "生物", "美术", "体育", "语文","英语" ],
     		[ "4", "物理", "化学", "历史", "体育", "语文", "物理","地理" ],
     		[ "午休", "", "", "", "", "", "","" ],
     		[ "1", "英语", "体育", "生物", "美术", "体育", "语文","英语" ],
     		[ "2", "物理", "化学", "历史", "体育", "语文", "物理","地理" ]
 	    ];
	do_DataTable.setRowData(lists);    

  ```
  下图是上述示例设置表格数据的展示效果。

  <img src="../../images/datatable_setRowData.png" height="380" width="330" >

[回到顶部](#top)

>##### <span id=setRowData><font color ='#0092db'>**setRowData**</font></span>: 设置表格数据

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **data** |<font color ='#808000'>**string**</font> | 是 | |数据可以是data://目录文件，也可以是一个JSON array二维表格式字符串
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明:格式如下：
  ```
  [
    [r1c1,r1c2,r1c3...],
    [r2c1,r2c2,r2c3...],
  ...
  ]

  ```

- 示例:

  ```javascript

  var lists = [
     		[ "1", "班级会", "数学", "数学", "化学", "音乐", "化学","物理" ],
     		[ "2", "语文", "语文", "地理", "数学", "美术", "生物","数学" ],
     		[ "3", "英语", "体育", "生物", "美术", "体育", "语文","英语" ],
     		[ "4", "物理", "化学", "历史", "体育", "语文", "物理","地理" ],
     		[ "午休", "", "", "", "", "", "","" ],
     		[ "1", "英语", "体育", "生物", "美术", "体育", "语文","英语" ],
     		[ "2", "物理", "化学", "历史", "体育", "语文", "物理","地理" ]
     	];
do_DataTable.setRowData(lists);    

  ```

[回到顶部](#top)

>##### <span id=setCellDatas><font color ='#0092db'>**setCellDatas**</font></span>: 设置单元格属性

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **data** |<font color ='#808000'>**object**</font> | 是 | |是一个数组
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明:注：其中row,column都从0开始,代表第一行第一列,以此类推。格式如下：
  ```

  [
    {
        row: 第几行,
        column: 第几列,
        text: 文本内容,
        style: {
            bgColor: '背景颜色',
            fontColor: '字体颜色',
            fontStyle: '字体风格',
            textFlag: '字体标示',
            fontSize: '字体大小'
        }
    },
    {
        ...
    }
  ]

  ```

- 示例:

  ```javascript

  do_DataTable.setCellDatas([
       {
           row: 0,
           column: 0,
           text: "第一行第一列",
           style: {
               bgColor: "FF8040FF",
               fontColor: "0080FFFF",
               fontStyle: "normal",
               textFlag: "strikethrough",
               fontSize: "20"
           }
       },
       {
           row: 1,
           column: 1,
           text: "第二行第二列",
           style: {
               bgColor: "FF8040FF",
               fontColor: "0080FFFF",
               fontStyle: "bold",
               textFlag: "normal",
               fontSize: "25"
           }
       }
   ])

  ```
  下图是上述示例设置表格数据的展示效果。

  <img src="../../images/datatable_setCellDatas.png" height="380" width="330" >

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=longTouch><font color ='#e96900'>**longTouch**</font></span>: 长按单元格触发

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 当前单元格的位置（不含表头）{row:第几行,column:第几列}
- 说明: 长按单元格触发
- 示例:

  ```javascript

  do_DataTable.on("longTouch", function(data) {
  	deviceone.print(JSON.stringify(data));
  })

  ```

  ```

  长按第一行第一列的情况下返回的数据：
    {
        "row":0,
        "column":0
    }

  ```

[回到顶部](#top)

>###### <span id=touch><font color ='#e96900'>**touch**</font></span>: 点击单元格触发

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 当前单元格的位置（不含表头）{row:第几行,column:第几列}
- 说明: 点击单元格触发
- 示例:

  ```javascript

  do_DataTable.on("touch", function(data) {
  	deviceone.print(JSON.stringify(data));
  })

  ```

  ```

  点击第二行第二列的情况下返回的数据：
    {
        "row":1,
        "column":1
    }

  ```

#### <font color ='#40A977'>**5.**</font> 常见问题
- 1.所有的样式设置完必须再掉一次setRowData

 原因：原生无法修复问题

#### <font color ='#40A977'>**6.**</font> 基本配置

[回到顶部](#top)
