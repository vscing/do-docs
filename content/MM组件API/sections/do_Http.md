---
title: do_Http 组件
---

### do_Http 组件

* 支持平台: iOS7.0,Android4.0
支持http/https请求服务

#### <font color ='#40A977'>**1.**</font> 属性

>###### <font color ='#42b983'>**method**</font>: 请求方式

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : get
- 说明 : http请求方式 GET/POST/PUT/PATCH/DELETE

>###### <font color ='#42b983'>**url**</font>: 地址

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 : 发送服务器请求地址

>###### <font color ='#42b983'>**timeout**</font>: 请求超时

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 5000
- 说明 : 请求服务器超时时间,单位是毫秒

>###### <font color ='#42b983'>**contentType**</font>: 内容类型

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : application/x-www-form-urlencoded
- 说明 : request时该属性默认值为application/x-www-form-urlencoded，upload和form时的默认值为multipart/form-data

>###### <font color ='#42b983'>**body**</font>: 请求数据

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 : 请求数据，method为get、delete时不支持

>###### <font color ='#42b983'>**responseEncoding**</font>: 字符集格式

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : utf-8
- 说明 : 设置服务端返回内容的解码格式，通常与服务端开发人员约定，当属性有值时优先以该属性值格式解码，当不设置该属性时以默认值utf-8格式解码。Android平台支持utf-8、GBK；iOS平台支持utf-8、GBK、GB2312、BIG5；windows支持utf-8、GBK、GB2312；除此之外不支持的都以默认utf-8解析

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**request**</font>: 发送请求

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**download**</font>: 下载

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **path** |<font color ='#808000'>**string**</font> |  | 是||下载到本地的文件的全路径，只支持data://
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 下载文件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**download1**</font>: 下载

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **path** |<font color ='#808000'>**string**</font> |  | 是||下载到本地的文件的全路径，只支持data://
  **taskId** |<font color ='#808000'>**string**</font> |  | 是||下载的任务ID
  **isBreakpoint** |<font color ='#808000'>**Boolean**</font> | true | 否|true|支持断点下载，下次下载相同Url文件会从上次停止的位置继续下载；iOS平台不支持设置为false
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 下载文件，支持断点续传，当下载中断，对相同url重新调用download1方法即可实现续传
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**stopDownload**</font>: 停止下载

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **taskId** |<font color ='#808000'>**string**</font> |  | 是||下载的任务ID
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 停止下载
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**upload**</font>: 上传

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **path** |<font color ='#808000'>**string**</font> |  | 是||需要上传的源文件地址，可以是data://目录，Android 还支持 sdcard:// 打头的目录
  **name** |<font color ='#808000'>**string**</font> | file | 否|file|(表单方式的上传)定义input元素的名称
  **filename** |<font color ='#808000'>**string**</font> |  | 否||文件上传到服务器的名称
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 上传文件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**setRequestHeader**</font>: 设置请求头

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **key** |<font color ='#808000'>**string**</font> |  | 是||
  **value** |<font color ='#808000'>**string**</font> |  | 是||
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**getResponseHeader**</font>: 获取请求头

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **key** |<font color ='#808000'>**string**</font> |  | 否||为空时返回所有的responseHeader
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回最后一次成功返回的http respose的header里某项或所有属性的值
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**form**</font>: 上传表单

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **data** |<font color ='#808000'>**object**</font> |  | 是||需要上传的数据内容，如{'files':[{'key':'file1','value':'data://1.png'}...],'texts':[{'key':'text1','value':'data://1.png'}...]}，其中标识key只能是texts或者files，为text时value表示字符串值；为file时value表示需要上传的源文件地址，可以是data://目录，Android 还支持 sdcard:// 打头的目录
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 支持同时上传多个文件和字符串，contentType固定为multipart/form-data，无需再设置
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**setRedirect**</font>: 设置重定向

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **isSetRedirect** |<font color ='#808000'>**Boolean**</font> | true | 否|true|为true时表示自动重定向，为false时表示不重定向，直接返回3xx请求
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 设置是否自动执行http重定向（响应状态码为3xx的请求）
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <font color ='#e96900'>**progress**</font>: 响应请求事件

- 返回值类型 : <font color ='#808000'>**Node**</font>
- 返回值描述: 返回值包含五个节点{currentSize:'1221',totalSize:'23234245',currentFileSize:'',index:'',taskId:''}单位为kB，其中currentFileSize和index只有调用form方法时返回，分别为当前正在上传文件大小和所在files数据数组中索引，除断点下载其他请求不会返回tastID，断点下载不返回index
- 说明: 响应请求事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**success**</font>: 请求成功事件

- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回http接收到的数据
- 说明: 请求成功事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**fail**</font>: 请求出错事件

- 返回值类型 : <font color ='#808000'>**Node**</font>
- 返回值描述: 返回值包含两个节点{status:'http错误码' ,message:'错误的信息'}
- 说明: 请求出错事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**result**</font>: 请求结束事件

- 返回值类型 : <font color ='#808000'>**Node**</font>
- 返回值描述: 返回值包含两个节点{status:'http状态码' ,data:'服务端返回信息',taskId:''}，除断点下载其他请求不会返回tastID
- 说明: 请求结束事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


