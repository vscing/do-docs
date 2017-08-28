---
title: do_Bluetooth 组件
---

### do_Bluetooth 组件

 支持平台: iOS,Android 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_Bluetooth)
 使用中心蓝牙与外围设备进行数据传输,设备必须支持蓝牙(BLE全称为Bluetooth Low Energy)4.0,注：Android系统必须4.3以上；不支持windows平台，iOS系统必须8.0以上

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#0092db'>同步方法</font>  |[stopScan](#stopScan)| 停止扫描
<font color ='#0092db'>同步方法</font>  |[close](#close)| 关闭蓝牙连接
<font color ='#0092db'>同步方法</font>  |[enable](#enable)| 打开手机蓝牙
<font color ='#0092db'>同步方法</font>  |[disable](#disable)| 关闭手机蓝牙
<font color ='#0092db'>异步方法</font>  |[open](#open)| 打开蓝牙连接
<font color ='#0092db'>异步方法</font>  |[startScan](#startScan)| 开始扫描
<font color ='#0092db'>异步方法</font>  |[connect](#connect)| 连接外围设备
<font color ='#0092db'>异步方法</font>  |[write](#write)| 写入数据
<font color ='#0092db'>异步方法</font>  |[read](#read)| 读取数据
<font color ='#0092db'>异步方法</font>  |[registerListener](#registerListener)| 注册监听
<font color ='#e96900'>事件</font>  |[characteristicChanged](#characteristicChanged)| 特征改变
<font color ='#e96900'>事件</font>  |[scan](#scan)| 搜索外围设备
<font color ='#e96900'>事件</font>  |[connectionStateChange](#connectionStateChange)| 连接状态改变

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=stopScan><font color ='#0092db'>**stopScan**</font></span>: 停止扫描

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 停止扫描设备
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=close><font color ='#0092db'>**close**</font></span>: 关闭蓝牙连接

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 关闭后需要重新打开蓝牙
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=enable><font color ='#0092db'>**enable**</font></span>: 打开手机蓝牙

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: true成功，false失败
- 说明: iOS平台不支持
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=disable><font color ='#0092db'>**disable**</font></span>: 关闭手机蓝牙

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: true成功，false失败
- 说明: iOS平台不支持
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <span id=open><font color ='#0092db'>**open**</font></span>: 打开蓝牙连接

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 0表示成功，1表示设备不支持BLE功能，2表示设备不支持蓝牙，3表示蓝牙没打开
- 说明: 打开设备蓝牙连接
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=startScan><font color ='#0092db'>**startScan**</font></span>: 开始扫描

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: true成功，false失败
- 说明: 扫描BLE外围设备，扫描到设备会触发scan事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=connect><font color ='#0092db'>**connect**</font></span>: 连接外围设备

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **address** |<font color ='#808000'>**string**</font> | 是 | |BLE终端设备mac地址/IOS对应设备UUID
- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: true成功false失败
- 说明: 根据指定唯一标识（MAC/UUID）连接BLE终端蓝牙设备，连接成功，发现该设备支持的服务
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=write><font color ='#0092db'>**write**</font></span>: 写入数据

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **data** |<font color ='#808000'>**string**</font> | 是 | |写入数据（不进行任何处理）
  **sUUID** |<font color ='#808000'>**string**</font> | 是 | |写入服务UUID
  **cUUID** |<font color ='#808000'>**string**</font> | 是 | |写入特征UUID
  **length** |<font color ='#808000'>**string**</font> | 否 | 20|设备一次性写入多少个字节，Android平台最大字节数为20
  **type** |<font color ='#808000'>**string**</font> | 否 | string|支持：binary 二进制数据(用十六进制字符串表示)，string 字符串。默认支持UTF-8编码
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 往BLE终端蓝牙模块服务特征写入数据，该特征需具备WRITE权限
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=read><font color ='#0092db'>**read**</font></span>: 读取数据

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **sUUID** |<font color ='#808000'>**string**</font> | 是 | |服务UUID
  **cUUID** |<font color ='#808000'>**string**</font> | 是 | |特征UUID
- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 0:成功;-1:失败;1:设备不支持;2:服务没找到;3:特征没有找到
- 说明: 读取BLE终端蓝牙模块服务特征数据，该特征需具备READ权限，调用这个方法会触发characteristicChanged事件，在事件中通过uuid区别是特征通知或者主动read触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=registerListener><font color ='#0092db'>**registerListener**</font></span>: 注册监听

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **sUUID** |<font color ='#808000'>**string**</font> | 是 | |服务UUID
  **cUUID** |<font color ='#808000'>**string**</font> | 是 | |特征UUID
- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 0:成功;-1:失败;1:设备不支持;2:服务没找到;3:特征没有找到
- 说明: 注册可以监听的特征,当特征改变的时候,会触发characteristicChanged事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=characteristicChanged><font color ='#e96900'>**characteristicChanged**</font></span>: 特征改变

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 收到BLE终端服务特征写入数据时触发该事件{特征uuid:'28923DE7-2E5D-4E81-8264-86BE1B9C4B51',value:'hello'}
- 说明: 特征改变
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <span id=scan><font color ='#e96900'>**scan**</font></span>: 搜索外围设备

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 搜索到外围设备触发该事件，{address:'Android(设备MAC B4:99:4C:25:29:51)'/'IOS(设备UUID)',name:'device1',RSSI:'接收的信号强度指示,单位dBm,127是保留值，标示无效'}
- 说明: 搜索外围设备
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <span id=connectionStateChange><font color ='#e96900'>**connectionStateChange**</font></span>: 连接状态改变

- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 监听连接状态，当连接状态发生变化触发该事件，0：断开、1：连接
- 说明: 连接状态改变
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


