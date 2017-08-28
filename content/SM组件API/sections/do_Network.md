---
title: do_Network 组件
---

### do_Network 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_Network)
 能获取当前手机端的网络状态,监听网络状态的变化

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#0092db'>同步方法</font>  |[getStatus](#getStatus)| 获取当前网络状态
<font color ='#0092db'>同步方法</font>  |[getIP](#getIP)| 获取移动终端ip地址
<font color ='#0092db'>同步方法</font>  |[getMACAddress](#getMACAddress)| 获取物理地址
<font color ='#0092db'>同步方法</font>  |[openWifiSetting](#openWifiSetting)| 打开无线网络连接界面
<font color ='#0092db'>同步方法</font>  |[isProxyUsed](#isProxyUsed)| 是否使用代理
<font color ='#0092db'>异步方法</font>  |[getWifiInfo](#getWifiInfo)| 获取wifi相关信息
<font color ='#e96900'>事件</font>  |[changed](#changed)| 网络状态发生变化的回调方法

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=getStatus><font color ='#0092db'>**getStatus**</font></span>: 获取当前网络状态

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 以下枚举类型的一种：'wifi'-wifi网络，'2G/3G/4G'-2G、3G或者4G，'none'-没有网络连接，'unknown'-未知网络连接
- 说明: 获取手机端当前处于的网络环境
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=getIP><font color ='#0092db'>**getIP**</font></span>: 获取移动终端ip地址

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 当前的ip地址
- 说明: 获取当前的ip地址
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=getMACAddress><font color ='#0092db'>**getMACAddress**</font></span>: 获取物理地址

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回当前设备的物理地址，windows平台返回的地址与直接在手机上查看的不一致，但也表示的是唯一地址；iOS平台不支持
- 说明: 当前设备的物理地址
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=openWifiSetting><font color ='#0092db'>**openWifiSetting**</font></span>: 打开无线网络连接界面

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 打开无线网络连接界面，选择网络连接，iOS平台10及以上系统无法使用该功能
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=isProxyUsed><font color ='#0092db'>**isProxyUsed**</font></span>: 是否使用代理

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: 使用代理返回true，没有使用返回false
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <span id=getWifiInfo><font color ='#0092db'>**getWifiInfo**</font></span>: 获取wifi相关信息

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回可连wifi列表及当前已连接wifi名称{'wifiNameList': [{'wifiName': '列表中的wifiName'}],'currentWifiName': '当前连接的wifi名称','routerMacAddress': '当前连接WiFi的路由器地址'}
- 说明: 获取wifi相关信息，可连wifi列表（iOS平台不支持）以及当前连接的wifi
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=changed><font color ='#e96900'>**changed**</font></span>: 网络状态发生变化的回调方法

- 返回值类型 : <font color ='#808000'>**sting**</font>
- 返回值描述: 返回以下枚举类型的一种：'wifi'-wifi网络，'2G/3G/4G'-2G、3G或者4G，'none'-没有网络连接，'unknown'-未知网络连接
- 说明: 网络状态发生变化的回调方法
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


