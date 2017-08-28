---
title: do_Algorithm 组件
---

### do_Algorithm 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_Algorithm)
 包含一些常用的算法实现，包括md5算法、3DES算法、sha1安全哈希算法和Base64算法

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#0092db'>同步方法</font>  |[base64Sync](#base64Sync)| Base64算法
<font color ='#0092db'>同步方法</font>  |[des3Sync](#des3Sync)| 3DES算法
<font color ='#0092db'>同步方法</font>  |[md5Sync](#md5Sync)| md5算法
<font color ='#0092db'>同步方法</font>  |[sha1Sync](#sha1Sync)| 安全哈希算法
<font color ='#0092db'>异步方法</font>  |[md5](#md5)| md5算法
<font color ='#0092db'>异步方法</font>  |[des3](#des3)| 3DES算法
<font color ='#0092db'>异步方法</font>  |[sha1](#sha1)| 安全哈希算法
<font color ='#0092db'>异步方法</font>  |[base64](#base64)| Base64算法
<font color ='#0092db'>异步方法</font>  |[hex2Str](#hex2Str)| 十六进制转字符串
<font color ='#0092db'>异步方法</font>  |[hex2Binary](#hex2Binary)| 十六进制转二进制
<font color ='#0092db'>异步方法</font>  |[xml2Json](#xml2Json)| xml转Json

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=base64Sync><font color ='#0092db'>**base64Sync**</font></span>: Base64算法

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **type** |<font color ='#808000'>**string**</font> | 否 | encode|目前支持两种类型，'encode'为编码、'decode'为解码
  **source** |<font color ='#808000'>**string**</font> | 否 | |
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回base64后的值
- 说明: 同步的Base64算法，只支持字符串的处理
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=des3Sync><font color ='#0092db'>**des3Sync**</font></span>: 3DES算法

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **key** |<font color ='#808000'>**string**</font> | 是 | |3DES算法的key值，不支持小于24位
  **type** |<font color ='#808000'>**string**</font> | 否 | encrypt|目前支持两种类型，'encrypt'为加密、'decrypt'为解密
  **source** |<font color ='#808000'>**string**</font> | 否 | |
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回des3后的值
- 说明: windows平台不支持
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=md5Sync><font color ='#0092db'>**md5Sync**</font></span>: md5算法

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **value** |<font color ='#808000'>**string**</font> | 否 | |
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回md5后的值，使用的是32位小写加密方式
- 说明: 同步md5算法，只支持字符串的处理
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=sha1Sync><font color ='#0092db'>**sha1Sync**</font></span>: 安全哈希算法

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **type** |<font color ='#808000'>**string**</font> | 否 | lowercase|目前支持两种类型，'uppercase'为加密后返回大写字母、'lowercase'为加密后返回小写字母
  **value** |<font color ='#808000'>**string**</font> | 否 | |
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回SHA1加密后的值
- 说明: 主要适用于数字签名标准
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <span id=md5><font color ='#0092db'>**md5**</font></span>: md5算法

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **type** |<font color ='#808000'>**string**</font> | 否 | string|目前支持两种类型，'string'为字符串类型、'file'为文件类型
  **value** |<font color ='#808000'>**string**</font> | 否 | |如果type为'string'类型，是一个字符串的值；如果为'file'类型，这就是一个文件的路径，只支持data://数据区目录
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回md5后的值，使用的是32位小写加密方式
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=des3><font color ='#0092db'>**des3**</font></span>: 3DES算法

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **key** |<font color ='#808000'>**string**</font> | 是 | |3DES算法的key值
  **type** |<font color ='#808000'>**string**</font> | 否 | encrypt|目前支持两种类型，'encrypt'为加密、'decrypt'为解密
  **source** |<font color ='#808000'>**string**</font> | 否 | |
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回des3后的值
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=sha1><font color ='#0092db'>**sha1**</font></span>: 安全哈希算法

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **type** |<font color ='#808000'>**string**</font> | 否 | lowercase|目前支持两种类型，'uppercase'为加密后返回大写字母、'lowercase'为加密后返回小写字母
  **value** |<font color ='#808000'>**string**</font> | 否 | |
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回SHA1加密后的值
- 说明: 主要适用于数字签名标准
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=base64><font color ='#0092db'>**base64**</font></span>: Base64算法

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **type** |<font color ='#808000'>**string**</font> | 否 | encode|目前支持两种类型，'encode'为编码、'decode'为解码
  **sourceType** |<font color ='#808000'>**string**</font> | 否 | string|支持两种'string':字符串类型、 'file'：文件类型,如果是file类型的话，encode是把一个file读出内容编码为base64字符串，如果是decode的时候是把一个base64字符串解码为一个data://temp/随机名字的文件
  **source** |<font color ='#808000'>**string**</font> | 否 | |
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回base64后的值
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=hex2Str><font color ='#0092db'>**hex2Str**</font></span>: 十六进制转字符串

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **source** |<font color ='#808000'>**string**</font> | 是 | |用十六进制字符串表示的数据
  **encoding** |<font color ='#808000'>**string**</font> | 否 | utf-8|指定编码格式，默认使用utf-8格式
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回转换之后的字符串
- 说明: 把十六进制数据按特定编码格式转成字符串
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=hex2Binary><font color ='#0092db'>**hex2Binary**</font></span>: 十六进制转二进制

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **source** |<font color ='#808000'>**string**</font> | 是 | |用十六进制字符串表示的数据
  **path** |<font color ='#808000'>**string**</font> | 是 | |要保存的二进制文件全路径,支持data://
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: 返回转换是否成功，true为成功，false失败
- 说明: 把十六进制数据转换成二进制并保存成文件放在指定目录下
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=xml2Json><font color ='#0092db'>**xml2Json**</font></span>: xml转Json

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **source** |<font color ='#808000'>**string**</font> | 是 | |
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回转换之后的字符串
- 说明: 把xml格式转换成标准Json格式
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件


