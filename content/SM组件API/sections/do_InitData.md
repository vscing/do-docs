---
title: do_InitData 组件
---

### do_InitData 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_InitData)
 DeviceOne定义了自己的文件URI，用户可以利用InitData类来处理initdata://开头的只读目录区文件，目前暂时不支持中文目录和中文文件名

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#0092db'>同步方法</font>  |[dirExist](#dirExist)| 判断目录是否存在
<font color ='#0092db'>同步方法</font>  |[fileExist](#fileExist)| 判断文件是否存在
<font color ='#0092db'>同步方法</font>  |[readFileSync](#readFileSync)| 读取文件内容
<font color ='#0092db'>异步方法</font>  |[getFiles](#getFiles)| 获取文件列表
<font color ='#0092db'>异步方法</font>  |[getDirs](#getDirs)| 获取目录列表
<font color ='#0092db'>异步方法</font>  |[readFile](#readFile)| 读取文件内容
<font color ='#0092db'>异步方法</font>  |[zip](#zip)| 压缩文件或目录
<font color ='#0092db'>异步方法</font>  |[zipFiles](#zipFiles)| 压缩多个文件
<font color ='#0092db'>异步方法</font>  |[unzip](#unzip)| 解压缩文件
<font color ='#0092db'>异步方法</font>  |[copy](#copy)| 拷贝文件
<font color ='#0092db'>异步方法</font>  |[copyFile](#copyFile)| 拷贝文件

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=dirExist><font color ='#0092db'>**dirExist**</font></span>: 判断目录是否存在

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **path** |<font color ='#808000'>**string**</font> | 是 | |只能是initdata://打头
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: 返回true为存在，false为不存在
- 说明: 判断指定目录是否存在
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=fileExist><font color ='#0092db'>**fileExist**</font></span>: 判断文件是否存在

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **path** |<font color ='#808000'>**string**</font> | 是 | |只能是initdata://打头
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: 返回true为存在，false为不存在
- 说明: 判断指定文件是否存在
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=readFileSync><font color ='#0092db'>**readFileSync**</font></span>: 读取文件内容

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **path** |<font color ='#808000'>**string**</font> | 是 | |文件名，只能是initdata://打头
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回读取到的指定文件的内容
- 说明: 获取指定文件的内容的同步方法；使用需谨慎，若读取的数据较多会导致UI卡顿
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <span id=getFiles><font color ='#0092db'>**getFiles**</font></span>: 获取文件列表

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **path** |<font color ='#808000'>**string**</font> | 是 | |只能是initdata://打头
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回是一个JSON Array，里面是文件名的列表，比如["1.txt","2.png",...]直接返回path下的文件路径
- 说明: 获取指定目录下所有文件列表
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=getDirs><font color ='#0092db'>**getDirs**</font></span>: 获取目录列表

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **path** |<font color ='#808000'>**string**</font> | 是 | |只能是initdata://打头
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回是一个JSON Array，里面是文件目录的列表，比如["1","2",...]直接返回path下的目录路径
- 说明: 获取指定目录下所有目录列表
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=readFile><font color ='#0092db'>**readFile**</font></span>: 读取文件内容

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **path** |<font color ='#808000'>**string**</font> | 是 | |文件名，只能是initdata://打头
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回读取到的指定文件的内容
- 说明: 获取指定文件的内容
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=zip><font color ='#0092db'>**zip**</font></span>: 压缩文件或目录

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **source** |<font color ='#808000'>**string**</font> | 是 | |只能是initdata://打头
  **target** |<font color ='#808000'>**string**</font> | 是 | |压缩后文件名，需要具体指定到文件名，只能是data://打头
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: true/false表明压缩是否成功
- 说明: 将指定的路径或文件压缩成zip文件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=zipFiles><font color ='#0092db'>**zipFiles**</font></span>: 压缩多个文件

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **source** |<font color ='#808000'>**object**</font> | 是 | |可支持压缩不在同一目录下的文件，只需指定文件路径，只能是initdata://打头
  **target** |<font color ='#808000'>**string**</font> | 是 | |压缩后文件名，需要具体指定到文件名，只能是data://打头
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: true/false表明压缩是否成功
- 说明: 将指定的一个或多个文件压缩成zip文件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=unzip><font color ='#0092db'>**unzip**</font></span>: 解压缩文件

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **source** |<font color ='#808000'>**string**</font> | 是 | |解压压缩文件名，只能是initdata://打头
  **target** |<font color ='#808000'>**string**</font> | 是 | |只能是data://打头
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: true/false表明解压缩是否成功
- 说明: 将指定的zip文件解压到指定的路径
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=copy><font color ='#0092db'>**copy**</font></span>: 拷贝文件

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **source** |<font color ='#808000'>**object**</font> | 是 | |可支持单独拷贝一个文件，或好几个文件同时拷贝，只能是initdata://打头
  **target** |<font color ='#808000'>**string**</font> | 是 | |拷贝的路径，只能是data://打头
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: true/false表明拷贝是否成功
- 说明: 将指定的一个或多个文件拷贝到一个目录下
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=copyFile><font color ='#0092db'>**copyFile**</font></span>: 拷贝文件

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **source** |<font color ='#808000'>**string**</font> | 是 | |只支持单独拷贝一个文件，需要为全路径，只能是initdata://打头
  **target** |<font color ='#808000'>**string**</font> | 是 | |拷贝后的目标文件，需要为全路径，只能是data://打头
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: true/false表明拷贝是否成功
- 说明: 拷贝指定文件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件


