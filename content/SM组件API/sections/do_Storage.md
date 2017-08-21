---
title: do_Storage 组件
---

### do_Storage 组件

 支持平台: iOS7.0,Android4.0
 DeviceOne定义了自己的文件URI，用户可以利用Storage类来处理各种文件操作，用户可对data://目录进行读写操作（缺省为utf-8格式）。目前暂时不支持中文目录和中文文件名

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**dirExist**</font>: 判断目录是否存在

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **path** |<font color ='#808000'>**string**</font> |  | 是||
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: 返回true为存在，false为不存在
- 说明: 判断指定目录是否存在
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**fileExist**</font>: 判断文件是否存在

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **path** |<font color ='#808000'>**string**</font> |  | 是||
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: 返回true为存在，false为不存在
- 说明: 判断指定文件是否存在
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**readFileSync**</font>: 读取文件内容

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **path** |<font color ='#808000'>**string**</font> |  | 是||文件名
  **isSecurity** |<font color ='#808000'>**Boolean**</font> | false | 否|false|是否以加密方式读取文件，若文件是以加密方式写的，该参数不设置为true则无法读取；如果操作的是data://security目录，则该属性无效，默认解密
  **encoding** |<font color ='#808000'>**string**</font> | utf-8 | 否|utf-8|读文件的编码格式，暂只支持utf-8和gbk两种
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回读取到的指定文件的内容
- 说明: 获取指定文件的内容的同步方法；使用需谨慎，若读取的数据较多会导致UI卡顿
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**getFileSize**</font>: 获取文件大小

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **path** |<font color ='#808000'>**string**</font> |  | 是||
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回获取到的文件大小，单位为字节，若path为一个目录或不存在的文件，则返回0
- 说明: 获取指定文件的大小
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <font color ='#0092db'>**getFiles**</font>: 获取文件列表

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **path** |<font color ='#808000'>**string**</font> |  | 是||
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回是一个JSON Array，里面是文件名的列表，比如["1.txt","2.png",...]直接返回path下的文件路径
- 说明: 获取指定目录下所有文件列表
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**getDirs**</font>: 获取目录列表

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **path** |<font color ='#808000'>**string**</font> |  | 是||
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回是一个JSON Array，里面是文件目录的列表，比如["1","2",...]直接返回path下的目录路径
- 说明: 获取指定目录下所有目录列表
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**deleteDir**</font>: 删除目录

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **path** |<font color ='#808000'>**string**</font> |  | 是||
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: true或者false表明删除目录是否存在，即要删除的文件是否不存在，不存在会返回true
- 说明: 删除指定目录以及这个目录下所有目录和文件，
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**deleteFile**</font>: 删除文件

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **path** |<font color ='#808000'>**string**</font> |  | 是||文件名
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: true或者false表明删除文件是否存在，即要删除的文件是否不存在，不存在会返回true
- 说明: 删除指定文件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**readFile**</font>: 读取文件内容

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **path** |<font color ='#808000'>**string**</font> |  | 是||文件名
  **isSecurity** |<font color ='#808000'>**Boolean**</font> | false | 否|false|是否以加密方式读取文件，如果操作的是data://security目录，则该属性无效，默认解密
  **encoding** |<font color ='#808000'>**string**</font> | utf-8 | 否|utf-8|读文件的编码格式，暂只支持utf-8和gbk两种
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回读取到的指定文件的内容
- 说明: 获取指定文件的内容
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**writeFile**</font>: 写文件

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **path** |<font color ='#808000'>**string**</font> |  | 是||文件名
  **data** |<font color ='#808000'>**string**</font> |  | 是||要写入的文件内容字符串
  **isSecurity** |<font color ='#808000'>**Boolean**</font> | false | 否|false|是否以加密方式写文件，如果操作的是data://security目录，则该属性无效，默认加密
  **encoding** |<font color ='#808000'>**string**</font> | utf-8 | 否|utf-8|写文件的编码格式，暂只支持utf-8和gbk两种
  **isAppend** |<font color ='#808000'>**Boolean**</font> | false | 否|false|是否以追加方式写文件，如果操作的是data://security目录或isSecurity=true，则该属性无效，默认不追加
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: true/false表明写文件是否成功
- 说明: 把指定字符串写入指定文件，完全覆盖
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**zip**</font>: 压缩文件或目录

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **source** |<font color ='#808000'>**string**</font> |  | 是||
  **target** |<font color ='#808000'>**string**</font> |  | 是||压缩后文件名，需要具体指定到文件名
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: true/false表明压缩是否成功
- 说明: 将指定的路径或文件压缩成zip文件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**zipFiles**</font>: 压缩多个文件

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **source** |<font color ='#808000'>**object**</font> |  | 是||可支持压缩不在同一目录下的文件，只需指定文件路径
  **target** |<font color ='#808000'>**string**</font> |  | 是||压缩后文件名，需要具体指定到文件名
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: true/false表明压缩是否成功
- 说明: 将指定的一个或多个文件压缩成zip文件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**unzip**</font>: 解压缩文件

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **source** |<font color ='#808000'>**string**</font> |  | 是||解压压缩文件名
  **target** |<font color ='#808000'>**string**</font> |  | 是||不支持data://security目录
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: true/false表明解压缩是否成功
- 说明: 将指定的zip文件解压到指定的路径
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**copy**</font>: 拷贝文件

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **source** |<font color ='#808000'>**object**</font> |  | 是||可支持单独拷贝一个文件，或好几个文件同时拷贝
  **target** |<font color ='#808000'>**string**</font> |  | 是||拷贝的路径
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: true/false表明拷贝是否成功
- 说明: 将指定的一个或多个文件拷贝到一个目录下
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**copyFile**</font>: 拷贝文件

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **source** |<font color ='#808000'>**string**</font> |  | 是||只支持单独拷贝一个文件，需要为全路径
  **target** |<font color ='#808000'>**string**</font> |  | 是||拷贝后的目标文件，需要为全路径，不支持data://security目录
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: true/false表明拷贝是否成功
- 说明: 拷贝指定文件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件


