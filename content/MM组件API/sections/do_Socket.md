---
title: do_Socket 组件
---

### do_Socket 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_Socket)
 通过Socket建立网络连接，进行通信

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#0092db'>同步方法</font>  |[close](#close)| 关闭连接
<font color ='#0092db'>异步方法</font>  |[connect](#connect)| 连接
<font color ='#0092db'>异步方法</font>  |[send](#send)| 发送数据
<font color ='#e96900'>事件</font>  |[receive](#receive)| 接收数据
<font color ='#e96900'>事件</font>  |[error](#error)| 链接异常

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=close><font color ='#0092db'>**close**</font></span>: 关闭连接

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: 无
- 说明: 关闭链接
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <span id=connect><font color ='#0092db'>**connect**</font></span>: 连接

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **ip** |<font color ='#808000'>**string**</font> | 是 | |
  **port** |<font color ='#808000'>**string**</font> | 是 | |
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: 是否连接成功
- 说明: 与socket服务端建立连接
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=send><font color ='#0092db'>**send**</font></span>: 发送数据

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **type** |<font color ='#808000'>**string**</font> | 是 | |如果发送的数据是字符串,type指定字符串的编码方式,支持UTF-8,GBK;如果发送的是16进制字符串,type为HEX;如果发送的是文件,type为file
  **content** |<font color ='#808000'>**string**</font> | 是 | |如果发送的是文件，content指定文件的全路径
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: 数据是否发送成功
- 说明: 向服务端发送数据
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=receive><font color ='#e96900'>**receive**</font></span>: 接收数据

- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 接收到的16进制数据
- 说明: 接收数据
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <span id=error><font color ='#e96900'>**error**</font></span>: 链接异常

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 连接成功后断开网络或服务器停止服务时触发，返回错误信息msg
- 说明: 链接异常
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


