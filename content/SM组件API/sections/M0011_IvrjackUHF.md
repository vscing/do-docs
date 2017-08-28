---
title: M0011_IvrjackUHF 组件
---

### M0011_IvrjackUHF 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/M0011_IvrjackUHF)
 

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#0092db'>同步方法</font>  |[open](#open)| 打开设备
<font color ='#0092db'>同步方法</font>  |[close](#close)| 关闭设备
<font color ='#0092db'>异步方法</font>  |[startScan](#startScan)| 开始扫描
<font color ='#0092db'>异步方法</font>  |[stopScan](#stopScan)| 停止扫描
<font color ='#0092db'>异步方法</font>  |[read](#read)| 读取标签内容
<font color ='#e96900'>事件</font>  |[result](#result)| 
<font color ='#e96900'>事件</font>  |[scan](#scan)| 

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=open><font color ='#0092db'>**open**</font></span>: 打开设备

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 初始化设备，打开设备
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=close><font color ='#0092db'>**close**</font></span>: 关闭设备

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <span id=startScan><font color ='#0092db'>**startScan**</font></span>: 开始扫描

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 返回设备状态码，0表示成功
- 说明: 扫描设备标签，扫描到标签会触发scan事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=stopScan><font color ='#0092db'>**stopScan**</font></span>: 停止扫描

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 返回设备状态码，0表示成功
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=read><font color ='#0092db'>**read**</font></span>: 读取标签内容

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **epc** |<font color ='#808000'>**string**</font> | 是 | |标签地址，如：'E2005114 59000020 0002A6DA'
  **area** |<font color ='#808000'>**number**</font> | 否 | 0|要读的区域，取值只可以是0（代表EPC区），1（代表USER区），2（代表RFU区），3（代表TID区）
  **address** |<font color ='#808000'>**string**</font> | 否 | 0|读取数据的起始地址
  **count** |<font color ='#808000'>**string**</font> | 否 | 1|读取数据的长度（以 word 为单位，1word=2byte），如：1 2， 01 02，a b，0a 0b，1a ab 等均为 1 个 word。2 个 word 即 11 2a ef 3d，以此类推
  **password** |<font color ='#808000'>**string**</font> | 否 | 00000000|访问口令，8位数字，如果是未锁定分区请务必填00000000。
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回{“result”:读取结果}
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=result><font color ='#e96900'>**result**</font></span>: 

- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 设备相关事件，0表示设备打开成功
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <span id=scan><font color ='#e96900'>**scan**</font></span>: 

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回一次扫描到的标签列表，{epc:'E2005114 59000020 0002A6DA'}
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


