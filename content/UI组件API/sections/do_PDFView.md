---
title: do_PDFView 组件
---

### do_PDFView 组件

* 支持平台: iOS7.0,Android4.0
PDF阅读器，不支持windows平台

#### <font color ='#40A977'>**1.**</font> 属性

>###### <font color ='#42b983'>**url**</font>: 打开的pdf文件路径

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 : 支持data://与source://目录

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**getPageCount**</font>: 总共页数以及当前页数

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {'total':100,'current':2}
- 说明: 返回总共页数以及当前页数
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**next**</font>: 下一页

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**prev**</font>: 上一页

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**jump**</font>: 跳转到指定页

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **page** |<font color ='#808000'>**number**</font> |  | 否||
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

>###### <font color ='#e96900'>**pageChanged**</font>: 页面切换时触发

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {'total':100,'current':2}
- 说明: 页面切换时触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


