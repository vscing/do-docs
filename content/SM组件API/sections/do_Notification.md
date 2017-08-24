---
title: do_Notification 组件
---

### do_Notification 组件

 支持平台: iOS7.0,Android4.0
 各种方式提醒和通知用户

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**toast**</font>: 弹出toast窗口

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **text** |<font color ='#808000'>**string**</font> | 否 | |
  **x** |<font color ='#808000'>**number**</font> | 否 | |
  **y** |<font color ='#808000'>**number**</font> | 否 | |
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 支持类似Android的toast的方式，弹出一个提示框，但是很短时间内会自动消隐，x和y都不赋值，即显示默认位置
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <font color ='#0092db'>**alert**</font>: 弹出alert窗口

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **text** |<font color ='#808000'>**string**</font> | 否 | |alert窗口的正文
  **title** |<font color ='#808000'>**string**</font> | 否 | |alert窗口的标题
  **buttontext** |<font color ='#808000'>**string**</font> | 否 | 确定|按钮的正文
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 通过alert来提示用户，alert是模态的，只有一个确定按钮
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**confirm**</font>: 弹出confirm窗口

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **text** |<font color ='#808000'>**string**</font> | 否 | |confirm窗口的正文
  **title** |<font color ='#808000'>**string**</font> | 否 | |confirm窗口的标题
  **button1text** |<font color ='#808000'>**string**</font> | 否 | 确定|左边按钮1的正文
  **button2text** |<font color ='#808000'>**string**</font> | 否 | 取消|右边按钮2的正文
- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 1 表示点击了button1按钮
2 表示点击了button2按钮
- 说明: confirm窗口有2个按钮，可以自定义按钮的文本内容
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件


