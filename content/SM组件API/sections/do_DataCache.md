---
title: do_DataCache 组件
---

### do_DataCache 组件

 支持平台: iOS7.0,Android4.0
 缓存一些数据到本地文件，即使程序退出再进入还能获取到值，要确保设置的value值不要过大

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**saveData**</font>: 写数据

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **key** |<font color ='#808000'>**string**</font> | 是 | |
  **value** |<font color ='#808000'>**string**</font> | 是 | |
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: true/false表明写数据是否成功
- 说明: 把数据写入缓存，不建议存入大文件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**hasData**</font>: 是否有数据

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **key** |<font color ='#808000'>**string**</font> | 是 | |
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: true有数据，false没有
- 说明: 判断是否有数据
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**removeData**</font>: 删除数据

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **key** |<font color ='#808000'>**string**</font> | 是 | |
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: true/false表明删除是否成功
- 说明: 清楚某个key的数据
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**loadData**</font>: 读数据

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **key** |<font color ='#808000'>**string**</font> | 是 | |
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回读取的数据值
- 说明: 把数据从缓存取出
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**removeAll**</font>: 删除全部数据

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: true为成功，false为失败
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件


