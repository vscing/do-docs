---
title: do_Dialog 组件
---

### do_Dialog 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_Dialog)
 显示在屏幕上的窗口

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#0092db'>同步方法</font>  |[getData](#getData)| 获取数据
<font color ='#0092db'>同步方法</font>  |[close](#close)| 关闭窗口
<font color ='#0092db'>异步方法</font>  |[open](#open)| 打开窗口

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=getData><font color ='#0092db'>**getData**</font></span>: 获取数据

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 获取open方法的data参数保存的数据
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=close><font color ='#0092db'>**close**</font></span>: 关闭窗口

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **data** |<font color ='#808000'>**string**</font> | 否 | |在关闭窗口时data参数传递给open方法的回调函数
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <span id=open><font color ='#0092db'>**open**</font></span>: 打开窗口

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **path** |<font color ='#808000'>**string**</font> | 是 | |支持source和data目录
  **data** |<font color ='#808000'>**string**</font> | 否 | |传递到Dialog的数据，通过getData方法获取该数据
  **supportClickClose** |<font color ='#808000'>**Boolean**</font> | 否 | true|设置成true时可以通过点击窗口外页面其他空白处关闭当前窗口；为false时则不支持点击关闭
- 返回值类型 : <font color ='#808000'>**Sting**</font>
- 返回值描述: 返回close方法的data参数值
- 说明: 打开的窗口在屏幕中居中显示
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件


