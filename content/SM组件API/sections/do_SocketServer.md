---
title: do_SocketServer 组件
---

### do_SocketServer 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_SocketServer)
 通过Socket建立网络连接，进行通信，TCP协议

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#0092db'>同步方法</font>  |[startListen](#startListen)| 开启监听
<font color ='#0092db'>同步方法</font>  |[stopListen](#stopListen)| 结束监听
<font color ='#0092db'>异步方法</font>  |[send](#send)| 发送数据
<font color ='#e96900'>事件</font>  |[receive](#receive)| 接收数据
<font color ='#e96900'>事件</font>  |[listen](#listen)| 监听事件
<font color ='#e96900'>事件</font>  |[error](#error)| 监听异常

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=startListen><font color ='#0092db'>**startListen**</font></span>: 开启监听

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **serverPort** |<font color ='#808000'>**string**</font> | 否 | 9999|
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: 开启监听是否成功
- 说明: 开启监听后客户端才能进行连接
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=stopListen><font color ='#0092db'>**stopListen**</font></span>: 结束监听

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 结束监听
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <span id=send><font color ='#0092db'>**send**</font></span>: 发送数据

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **type** |<font color ='#808000'>**string**</font> | 是 | |如果发送的数据是字符串,type指定字符串的编码方式,支持UTF-8,GBK;如果发送的是16进制字符串,type为HEX;如果发送的是文件,type为file
  **content** |<font color ='#808000'>**string**</font> | 是 | |如果发送的是文件，content指定文件的全路径
  **clientIP** |<font color ='#808000'>**string**</font> | 否 | |要发送的客户端IP,可以为空,为空时发送给所有的客户端
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: 数据是否发送成功
- 说明: 向客户端发送数据,如果clientIP和clientPort指定有值,则发送给对应的客户端,否则发送给所有连接到该服务端的客户端
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=receive><font color ='#e96900'>**receive**</font></span>: 接收数据

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回值为Node类型,格式为{receiveData:'aa', client:'192.168.1.1:8888'}
- 说明: 接收数据
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <span id=listen><font color ='#e96900'>**listen**</font></span>: 监听事件

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 如果有客户端连接上该服务端,则触发该事件,并且返回该客户端的ip和端口号,格式为'192.168.0.95:8080'
- 说明: 监听事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <span id=error><font color ='#e96900'>**error**</font></span>: 监听异常

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 监听成功后，并且当前已经有客户端连接，断开网络或网络切换时触发该事件（error事件触发并不会影响当前的监听，只是会将当前已连接的客户端移除）
- 说明: 监听异常
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


