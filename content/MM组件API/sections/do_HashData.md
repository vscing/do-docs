---
title: do_HashData 组件
---

### do_HashData 组件

 支持平台: iOS7.0,Android4.0
 HashData作为一个内存数据源，可以给UIModule作为bindData的数据源。可以参考UIModule的bindData方法。它本质上是一个可变key-value键值对,可以增删改查.

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**getCount**</font>: 获取元素个数

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 元素个数
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**addOne**</font>: 增加一条数据

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **key** |<font color ='#808000'>**string**</font> |  | 是||key相同时会覆盖之前的值
  **value** |<font color ='#808000'>**string**</font> |  | 是||向数据集添加一条数据，该数据可为String,Number,Boolean, Array<String|Number|Boolean>, Object<String|Number|Boolean>.(能够被JSON.stringify序列化的类型)
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**addData**</font>: 增加数据

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **data** |<font color ='#808000'>**object**</font> |  | 是||要插入的数据
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 向数据集添加数据
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**getOne**</font>: 获取某一行数据

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **key** |<font color ='#808000'>**string**</font> |  | 是||
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: value值
- 说明: 根据key获取对应值，若没找到返回null
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**getData**</font>: 获取数据

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **keys** |<font color ='#808000'>**object**</font> |  | 是||
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回对应的value集合
- 说明: 根据keys获取多条数据，若没找到返回null
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**getAll**</font>: 获取全部数据

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 无
- 说明: 获取所有数据，若没找到返回null
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**removeOne**</font>: 删除某一行数据

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **key** |<font color ='#808000'>**string**</font> |  | 是||
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 根据key删除特定数据
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**removeData**</font>: 根据keys删除多条数据

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **keys** |<font color ='#808000'>**object**</font> |  | 是||
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**removeAll**</font>: 清空数据

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 清除所有数据
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件


