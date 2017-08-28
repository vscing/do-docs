---
title: do_SQLite 组件
---

### do_SQLite 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_SQLite)
 提供SQLite3数据库的访问接口

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#0092db'>同步方法</font>  |[open](#open)| 打开数据库
<font color ='#0092db'>同步方法</font>  |[close](#close)| 关闭数据库
<font color ='#0092db'>同步方法</font>  |[executeSync](#executeSync)| 同步执行SQL语句
<font color ='#0092db'>同步方法</font>  |[executeSync1](#executeSync1)| 同步执行SQL语句
<font color ='#0092db'>同步方法</font>  |[querySync](#querySync)| 执行SQL查询语句
<font color ='#0092db'>异步方法</font>  |[execute](#execute)| 异步执行SQL语句
<font color ='#0092db'>异步方法</font>  |[execute1](#execute1)| 异步执行SQL语句
<font color ='#0092db'>异步方法</font>  |[query](#query)| 执行SQL查询语句

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=open><font color ='#0092db'>**open**</font></span>: 打开数据库

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **path** |<font color ='#808000'>**string**</font> | 是 | |
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: 无
- 说明: 打开一个本地数据库链接，只支持data://的路径或者:memory:，其中:memory:表示内存数据库
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=close><font color ='#0092db'>**close**</font></span>: 关闭数据库

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: 无
- 说明: 关闭数据库链接
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=executeSync><font color ='#0092db'>**executeSync**</font></span>: 同步执行SQL语句

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **sql** |<font color ='#808000'>**string**</font> | 是 | |
  **bind** |<font color ='#808000'>**object**</font> | 否 | |是一个数组，里面每一项对应一个sql语句中的？占位符，支持三种类型：string、Number、Boolean
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: 执行是否成功
- 说明: 用于执行任意的单条SQL语句
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=executeSync1><font color ='#0092db'>**executeSync1**</font></span>: 同步执行SQL语句

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **sqls** |<font color ='#808000'>**object**</font> | 是 | |要执行的多条SQL语句，用逗号隔开的JSON Array；如['insert into...','insert into...']
  **isTransaction** |<font color ='#808000'>**Boolean**</font> | 是 | false|设置是否支持事务，默认false为不支持
- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 当前影响行数
- 说明: 用于执行任意的多条SQL语句
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=querySync><font color ='#0092db'>**querySync**</font></span>: 执行SQL查询语句

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **sql** |<font color ='#808000'>**string**</font> | 是 | |
  **bind** |<font color ='#808000'>**object**</font> | 否 | |是一个数组，里面每一项对应一个sql语句中的？占位符，支持三种类型：string、Number、Boolean
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回的每一个元素都是json node，node的每一个节点都是column名比如[ {column1:'value1',clolumn2:'value2'},{column1:'value1',clolumn2:'value2'},...]
- 说明: 用于执行查询语句的同步方法；使用需谨慎，若查询的数据较多会导致UI卡顿
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <span id=execute><font color ='#0092db'>**execute**</font></span>: 异步执行SQL语句

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **sql** |<font color ='#808000'>**string**</font> | 是 | |
  **bind** |<font color ='#808000'>**object**</font> | 否 | |是一个数组，里面每一项对应一个sql语句中的？占位符，支持三种类型：string、Number、Boolean
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: 执行是否成功
- 说明: 用于执行任意的单条SQL语句
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=execute1><font color ='#0092db'>**execute1**</font></span>: 异步执行SQL语句

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **sqls** |<font color ='#808000'>**object**</font> | 是 | |要执行的多条SQL语句，用逗号隔开的JSON Array；；如['insert into...','insert into...']
  **isTransaction** |<font color ='#808000'>**Boolean**</font> | 是 | false|设置是否支持事务，默认false为不支持
- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 当前影响行数
- 说明: 用于执行任意的多条SQL语句
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=query><font color ='#0092db'>**query**</font></span>: 执行SQL查询语句

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **sql** |<font color ='#808000'>**string**</font> | 是 | |
  **bind** |<font color ='#808000'>**object**</font> | 否 | |是一个数组，里面每一项对应一个sql语句中的？占位符，支持三种类型：string、Number、Boolean
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回的每一个元素都是json node，node的每一个节点都是column名比如[ {column1:'value1',clolumn2:'value2'},{column1:'value1',clolumn2:'value2'},...]
- 说明: 用于执行查询语句
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件


