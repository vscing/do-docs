---
title: do_DataTable 组件
---

### do_DataTable 组件

 支持平台: iOS7.0,Android4.0
 类似于Excel表格，展示对应的二维数据表，可以支持自定义的样式设置,可支持上下左右滑动查看，也可支持固定列的锁定。当表头列数与数据列数无法匹配时，确定显示列数的顺序为：1.HeaderData、2.HeaderStyle、3.RowData

#### <font color ='#40A977'>**1.**</font> 属性

>###### <font color ='#42b983'>**isHeaderVisible**</font>: 是否显示表头

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : true
- 说明 : 如果显示表头的话，表头是不会随表格上下滑动的时候滑动的

>###### <font color ='#42b983'>**freezeColumn**</font>: 冻结的列个数

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 1
- 说明 : 只允许从左到右数起的列被冻结，左右滑动的时候固定不动

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**setHeaderStyle**</font>: 设置表头样式

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **width** |<font color ='#808000'>**string**</font> | 否 | 100|可以全局设置，如：100; 也可以支持对每列设置，格式为一个JsonArray，如：[100,50,40,50]，需与表头列数对应
  **height** |<font color ='#808000'>**string**</font> | 否 | 80|
  **bgColor** |<font color ='#808000'>**string**</font> | 否 | 00000000|设置背景显示颜色，值格式为：8位16进制字符，前6位是RGB颜色值，后两位是透明度（Alpha），例如：000000FF
  **fontColor** |<font color ='#808000'>**string**</font> | null | 000000FF|设置字体显示颜色，值格式为：8位16进制字符，前6位是RGB颜色值，后两位是透明度（Alpha），例如：000000FF
  **fontStyle** |<font color ='#808000'>**string**</font> | null | normal|包含4种类型：normal：常规bold：粗体italic：斜体bold_italic：粗斜体（iOS平台不支持）
  **textFlag** |<font color ='#808000'>**string**</font> | null | normal|包含3种类型：normal：常规underline ：下划线strikethrough ：删除线
  **fontSize** |<font color ='#808000'>**number**</font> | null | 17|
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**setHeaderData**</font>: 设置表头数据

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **data** |<font color ='#808000'>**object**</font> | 是 | |格式如下：[“姓名”,“性别”,“年龄”...]
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**setRowStyle**</font>: 设置数据样式

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
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**setRowData**</font>: 设置表格数据

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **data** |<font color ='#808000'>**string**</font> | 是 | |数据可以是data://目录文件，也可以是 一个JSON array二维表格式字符串，格式如下：[[r1c1,r1c2,r1c3...],[r2c1,r2c2,r2c3...]...]
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**setCellDatas**</font>: 设置单元格属性

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **data** |<font color ='#808000'>**object**</font> | 是 | |是一个数组，包含[{row:第几行,column:第几列,text:文本内容,style:{bgColor:'背景颜色',fontColor:'字体颜色',fontStyle:'字体风格',textFlag:'字体标示',fontSize:'字体大小'}},{...}]
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <font color ='#e96900'>**longTouch**</font>: 长按单元格触发

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 当前单元格的位置（不含表头）{row:第几行,column:第几列}
- 说明: 长按单元格触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**touch**</font>: 点击单元格触发

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 当前单元格的位置（不含表头）{row:第几行,column:第几列}
- 说明: 点击单元格触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


