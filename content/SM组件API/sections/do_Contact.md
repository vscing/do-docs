---
title: do_Contact 组件
---

### do_Contact 组件

* 支持平台: iOS7.0,Android4.0
针对通讯录的增删查改

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <font color ='#0092db'>**getDataById**</font>: 获取通讯录联系人信息

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **id** |<font color ='#808000'>**string**</font> |  | 是||
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 根据联系人id查询的联系人信息，{'id':'1001','name':'','phone':['phone1','phone2'...],'email':['email1','email2'...]}
- 说明: 根据id获取通讯录联系人信息
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**getData**</font>: 获取通讯录联系人信息

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **value** |<font color ='#808000'>**string**</font> |  | 否||根据条件来模糊查询，目前支持的字段名称有：name(姓名)，phone(电话)，email(电子邮件)
  **types** |<font color ='#808000'>**object**</font> |  | 否||支持['name','phone','email']，如果参数为空则按全条件查询
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 根据参数值，返回查询的联系人信息列表，[{'id':'1001','name':'','phone':['phone1','phone2'...],'email':['email1','email2'...]},{'id':'1002','name':'','phone':['phone1','phone2'...],'email':['email1','email2'...]}...]
- 说明: 根据name，phone，email的值来查询通讯录联系人信息，如果参数value为空，就获取所有联系人信息，支持模糊查询
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**addData**</font>: 添加联系人信息

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **paras** |<font color ='#808000'>**object**</font> |  | 是||如：[{'name':'张三','phone':'13922864549','email':'xxx@deviceone.com'}]，目前支持的字段名称有：name(姓名)，phone(电话)，email(邮箱)
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回添加一组联系人的唯一标识
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**updateData**</font>: 修改联系人信息

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **id** |<font color ='#808000'>**string**</font> |  | 是||要修改联系人的唯一标识
  **paras** |<font color ='#808000'>**object**</font> |  | 是||如：{'name':'张三','phone':'13922864549','email':'xxx@deviceone.com'}，目前支持的字段名称有：name(姓名)，phone(电话)，email(邮箱)
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: true：成功，false：失败
- 说明: 由于权限问题，windows平台不支持该方法
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**deleteData**</font>: 删除联系人信息

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **id** |<font color ='#808000'>**object**</font> |  | 否||如果值为空(不是空数组)，就删除所有，否则就按照数组中的唯一标识依次删除
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: true：成功，false：失败
- 说明: 由于权限问题，windows平台不支持该方法
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件


