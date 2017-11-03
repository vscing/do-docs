---
title: do_ListData 组件
---

### do_ListData 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_ListData)
 ListData作为一个内存数据源 ,可以参考ListView的bindItems方法。也可以作为ListView，GridView的Item的数据集。它本质上是一个可变数组,可以增删改查.

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#0092db'>同步方法</font>  |[getCount](#getCount)| 获取数量
<font color ='#0092db'>同步方法</font>  |[getData](#getData)| 获取多条数据
<font color ='#0092db'>同步方法</font>  |[getOne](#getOne)| 获取某一行数据
<font color ='#0092db'>同步方法</font>  |[getRange](#getRange)| 获取多条数据
<font color ='#0092db'>同步方法</font>  |[addData](#addData)| 增加数据
<font color ='#0092db'>同步方法</font>  |[addOne](#addOne)| 插入一条数据
<font color ='#0092db'>同步方法</font>  |[removeAll](#removeAll)| 清空数据
<font color ='#0092db'>同步方法</font>  |[removeRange](#removeRange)| 删除指定行数据
<font color ='#0092db'>同步方法</font>  |[removeData](#removeData)| 删除特定行的对象
<font color ='#0092db'>同步方法</font>  |[updateOne](#updateOne)| 更新一条数据

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=getCount><font color ='#0092db'>**getCount**</font></span>: 获取数量

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 元素个数
- 说明:
- 示例:

  ```javascript
  var count = do_ListData.getCount();

  ```

[回到顶部](#top)

>##### <span id=getData><font color ='#0092db'>**getData**</font></span>: 获取多条数据

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **indexs** |<font color ='#808000'>**object**</font> | 是 | |表示需要得到的索引队列;如[0,2,3,4,6]
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 行数据
- 说明: indexs数组中的每一个值表示要读取的索引位置，从0开始;其它越界的索引位置都返回null
- 示例:

  ```javascript
  var data1 = do_ListData.getData()

  ```

[回到顶部](#top)

>##### <span id=getOne><font color ='#0092db'>**getOne**</font></span>: 获取某一行数据

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **index** |<font color ='#808000'>**number**</font> | 是 | |
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 行数据
- 说明: 根据index获取特定行的数据，从0开始; 如果index参数小于0则取数组第一个元素；如果 index参数越界，则返回数组最后一个元素（如果数据源为空则返回null）
- 示例:

  ```javascript
  var data2 = do_ListData.getone(0)

  ```

[回到顶部](#top)

>##### <span id=getRange><font color ='#0092db'>**getRange**</font></span>: 获取多条数据

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **fromIndex** |<font color ='#808000'>**number**</font> | 是 | |从0开始，fromIndex必须小于或等于toIndex
  **toIndex** |<font color ='#808000'>**number**</font> | 否 | |截止索引位置(可选项)，从0开始; 如果为空，则表示数组的最后一个元素位置
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 从起始索引到截止索引，获取多条数据
- 示例:

  ```javascript
  var datas = do_ListData.getRange({fromIndex:0,toIndex:2})

  ```

[回到顶部](#top)

>##### <span id=addData><font color ='#0092db'>**addData**</font></span>: 增加数据

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **data** |<font color ='#808000'>**object**</font> | 是 | |要插入的数据
  **index** |<font color ='#808000'>**number**</font> | 否 | |表示要添加的位置，从0开始; 如果 index参数为空或者越界, 就添加到数组最后面
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 在list增加一个或多个数据，index是可选参数，如果该参数不填表示插入到队列最尾
- 示例:

  ```javascript
  var data3 = {}
  do_ListData.addData()

  ```

[回到顶部](#top)

>##### <span id=addOne><font color ='#0092db'>**addOne**</font></span>: 插入一条数据

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **data** |<font color ='#808000'>**object**</font> | 是 | |向数据集添加一条数据，该数据可为String,Number,Boolean, Array<String|Number|Boolean>, Object<String|Number|Boolean>.(能够被JSON.stringify序列化的类型)
  **index** |<font color ='#808000'>**number**</font> | 否 | |插入索引
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 在list增加一条数据，index是可选参数，表示要添加的位置，从0开始; 如果 index参数为空或者越界, 就添加到数组最后面
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=removeAll><font color ='#0092db'>**removeAll**</font></span>: 清空数据

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 清除所有数据
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=removeRange><font color ='#0092db'>**removeRange**</font></span>: 删除指定行数据

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **fromIndex** |<font color ='#808000'>**number**</font> | 是 | |从0开始，fromIndex必须小于或等于toIndex
  **toIndex** |<font color ='#808000'>**number**</font> | 否 | |表示要删除的位置，从0开始; 如果为空或者越界，则表示数组的最后一个元素位置
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 从起始索引到截止索引删除多条数据
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=removeData><font color ='#0092db'>**removeData**</font></span>: 删除特定行的对象

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **indexs** |<font color ='#808000'>**object**</font> | 是 | |
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 根据多个index删除多条数据
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=updateOne><font color ='#0092db'>**updateOne**</font></span>: 更新一条数据

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **index** |<font color ='#808000'>**number**</font> | 是 | |
  **data** |<font color ='#808000'>**string**</font> | 是 | |
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 更新特定行的数据，index表示要修改的位置，从0开始; 如果index参数为空或者越界就什么都不改
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件
