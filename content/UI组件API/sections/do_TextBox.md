---
title: do_TextBox 组件
---

### do_TextBox 组件

 支持平台: iOS7.0,Android4.0
 通常只能输入多行数据，当高度设置为-1时，默认会显示一行文字的高度

#### <font color ='#40A977'>**1.**</font> 属性

>###### <font color ='#42b983'>**cursorColor**</font>: 光标颜色

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 000000FF
- 说明 : 修改输入框光标颜色，暂只支持iOS平台

>###### <font color ='#42b983'>**enabled**</font>: 是否可编辑

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : true
- 说明 : 控制文本框是否为可编辑状态，为false时不可编辑

>###### <font color ='#42b983'>**text**</font>: 文本内容

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 : 获取或设置与此控件关联的文本

>###### <font color ='#42b983'>**fontColor**</font>: 字体颜色

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 000000FF
- 说明 : 设置字体显示颜色，值格式为：8位16进制字符，前6位是RGB颜色值，后两位是透明度（Alpha），例如：000000FF

>###### <font color ='#42b983'>**fontSize**</font>: 字体大小

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 17
- 说明 : 

>###### <font color ='#42b983'>**fontStyle**</font>: 字体风格

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : normal
- 说明 : 包含4种类型：normal：常规；bold：粗体；italic：斜体；bold_italic：粗斜体

>###### <font color ='#42b983'>**textFlag**</font>: 字体标示

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : normal
- 说明 : 包含3种类型：normal：常规；underline：下划线；strikethrough ：删除线

>###### <font color ='#42b983'>**hint**</font>: text为空提示文本

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 : 

>###### <font color ='#42b983'>**hintColor**</font>: 提示信息字体颜色

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 808080FF
- 说明 : text为空时显示的文字提示信息字体颜色，windows平台不支持

>###### <font color ='#42b983'>**maxLength**</font>: 可允许输入的最大长度

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 100
- 说明 : 

>###### <font color ='#42b983'>**maxLines**</font>: 最大行数

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 0
- 说明 : 最大行数，说明：此属性只有组件高度为-1时才生效；设置文本内容输入最大行数，如输入文本超过了最大行值则行数不再继续增加，同时可以通过上下滚动来查看输入的内容；当小于0时表示不限制行数；Windows平台不支持

>###### <font color ='#42b983'>**inputType**</font>: 输入类型

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : ENG
- 说明 : 输入类型，不设置这个属性的时候会使用系统默认键盘支持所有字符，可设置的值包括以下5种:
	
"ASC" ：支持ASCII的默认键盘

"PHONENUMBER" ：标准电话键盘，支持＋＊＃字符

"URL" ：URL键盘，支持.com按钮 只支持URL字符
		
"ENG" :英文键盘
"DECIMAL" :数字与小数点键盘（仅支持iOS平台）

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**setFocus**</font>: 设置焦点

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **value** |<font color ='#808000'>**boolean**</font> | 是 | false|为true时有焦点，false时无焦点
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 设置是否得到焦点，得到焦点时软键盘弹出，失去焦点时软键盘收起
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**setSelection**</font>: 设置光标位置

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **position** |<font color ='#808000'>**number**</font> | 是 | 0|表示在已有字符的第几个位置，从0开始，比如文本框内有5个字符，position设置为3，光标即在第4个字符之前
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

>###### <font color ='#e96900'>**textChanged**</font>: 文字变化时触发

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 
- 说明: 文字变化时触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**focusIn**</font>: 进入编辑状态

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回键盘高度，{keybordHeight:'25'}
- 说明: 进入编辑状态
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**focusOut**</font>: 离开编辑状态

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 
- 说明: 离开编辑状态
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


