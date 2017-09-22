---
title: do_PDFView 组件
---

### do_PDFView 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_PDFView)
 PDF阅读器，不支持windows平台

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#42b983'>属性</font>  |[url](#url)| 打开的pdf文件路径
<font color ='#0092db'>同步方法</font>  |[getPageCount](#getPageCount)| 总共页数以及当前页数
<font color ='#0092db'>同步方法</font>  |[next](#next)| 下一页
<font color ='#0092db'>同步方法</font>  |[prev](#prev)| 上一页
<font color ='#0092db'>同步方法</font>  |[jump](#jump)| 跳转到指定页
<font color ='#e96900'>事件</font>  |[pageChanged](#pageChanged)| 页面切换时触发

#### <font color ='#40A977'>**1.**</font> 属性

>###### <span id=url><font color ='#42b983'>**url**</font></span>: 打开的pdf文件路径

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 :
- 说明 : 支持data://与source://目录
- 示例:

  ```javascript

  var do_PDFView = ui("do_PDFView_1");  //实例化
  do_PDFView.url = "source://view/do_PDFView/text.pdf";

  ```

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=getPageCount><font color ='#0092db'>**getPageCount**</font></span>: 总共页数以及当前页数

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述:
    ```

    {
      "total": "100",
      "current":"2"
    }

    ```

- 说明: 返回总共页数以及当前页数
- 示例:

  ```javascript

  do_PDFView.getPageCount();

  ```

[回到顶部](#top)

>##### <span id=next><font color ='#0092db'>**next**</font></span>: 下一页

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明:
- 示例:

  ```javascript

  do_PDFView.next();

  ```

[回到顶部](#top)

>##### <span id=prev><font color ='#0092db'>**prev**</font></span>: 上一页

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明:
- 示例:

  ```javascript

  do_PDFView.prev();

  ```

[回到顶部](#top)

>##### <span id=jump><font color ='#0092db'>**jump**</font></span>: 跳转到指定页

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **page** |<font color ='#808000'>**number**</font> | 否 | |
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明:
- 示例:

  ```javascript

  var page_count = 3;   
  do_PDFView.jump(page_count);    //number类型

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=pageChanged><font color ='#e96900'>**pageChanged**</font></span>: 页面切换时触发

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述:
    ```

    {
      "total": "100",
      "current":"2"
    }

    ```

- 说明: 页面切换时触发
- 示例:

  ```javascript

  do_PDFView.on("pageChanged", function(data) {
  	deviceone.print(JSON.stringify(data));
  })

  ```

[回到顶部](#top)
