---
title: do_UdpSocket 组件
---

### do_UdpSocket 组件

 支持平台: iOS7.0,Android4.0
 通过Socket建立网络连接，遵循UDP协议，进行通信

#### <font color ='#40A977'>**1.**</font> 属性

>###### <font color ='#42b983'>**localPort**</font>: 本地端口号

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 8888
- 说明 : 跟服务端交互使用,服务端发送消息会根据客户端的ip和端口号发送,客户端根据端口号生成socket实例

>###### <font color ='#42b983'>**serverIP**</font>: 服务端地址

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 : 

>###### <font color ='#42b983'>**serverPort**</font>: 服务端端口号

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 : 

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**open**</font>: 打开连接

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 设置过localPort属性,执行此方法取后才能发送数据
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**close**</font>: 关闭连接

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 关闭链接
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <font color ='#0092db'>**send**</font>: 发送数据

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **type** |<font color ='#808000'>**string**</font> |  | 是||如果发送的数据是字符串,type指定字符串的编码方式,支持UTF-8,GBK;如果发送的是16进制字符串,type为HEX;如果发送的是文件,type为file
  **content** |<font color ='#808000'>**string**</font> |  | 是||如果发送的是文件，content指定文件的全路径，iOS平台最大支持9k大小文件
- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: 数据是否发送成功
- 说明: 向服务端发送数据
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件

>###### <font color ='#e96900'>**receive**</font>: 接收数据

- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 接收到的16进制数据
- 说明: 接收数据
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


