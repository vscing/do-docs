---
title: do_Device 组件
---

### do_Device 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_Device)
 设备辅助功能，获取设备系统相关信息、提示音、震动、闪光灯、截屏等

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#0092db'>同步方法</font>  |[vibrate](#vibrate)| 振动
<font color ='#0092db'>同步方法</font>  |[beep](#beep)| 系统通知提示音
<font color ='#0092db'>同步方法</font>  |[flash](#flash)| 开关闪光灯
<font color ='#0092db'>同步方法</font>  |[getInfo](#getInfo)| 获取设备信息
<font color ='#0092db'>同步方法</font>  |[getAllAppInfo](#getAllAppInfo)| 获取应用信息
<font color ='#0092db'>同步方法</font>  |[getLocale](#getLocale)| 获取系统环境
<font color ='#0092db'>同步方法</font>  |[home](#home)| 应用退到后台
<font color ='#0092db'>同步方法</font>  |[setScreenAutoDarken](#setScreenAutoDarken)| 控制锁屏
<font color ='#0092db'>同步方法</font>  |[getBattery](#getBattery)| 获取电量
<font color ='#0092db'>同步方法</font>  |[getLocationPermission](#getLocationPermission)| 获取当前应用的位置权限
<font color ='#0092db'>异步方法</font>  |[screenShot](#screenShot)| 截屏
<font color ='#0092db'>异步方法</font>  |[srceenShotAsBitmap](#srceenShotAsBitmap)| 截屏
<font color ='#0092db'>异步方法</font>  |[getGPSInfo](#getGPSInfo)| 获取设备GPS信息
<font color ='#0092db'>异步方法</font>  |[getRingerMode](#getRingerMode)| 获取设备声音状态

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=vibrate><font color ='#0092db'>**vibrate**</font></span>: 振动

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **duration** |<font color ='#808000'>**number**</font> | 否 | 1000|振动持续时间，单位是毫秒，iOS平台不支持设置振动时间
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 触发设备振动，缺省是一秒
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=beep><font color ='#0092db'>**beep**</font></span>: 系统通知提示音

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 播放系统通知提示音
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=flash><font color ='#0092db'>**flash**</font></span>: 开关闪光灯

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **status** |<font color ='#808000'>**string**</font> | 是 | |闪光灯状态，支持两种状态：on（开启）、off（关闭）
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 开关手机系统闪光灯
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=getInfo><font color ='#0092db'>**getInfo**</font></span>: 获取设备信息

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回值是一个JSON键值对，键值分别为“设备信息名称”和“设备信息值”，比如{ "OS":"Android",    "OSVersion":"4.1",    .....}不同的操作系统可能有少部分信息获取不到，另外deviceId：设备唯一标识（当获取不到设备的deviceID时返回设备的MAC地址做为唯一ID），deviceName：设备名称，OS：操作系统版本，OSVersion：操作系统版本号，sdkVersion：获取手机操作系统SDK版本号，resolutionH：水平分辨率，resolutionV：垂直分辨率，dpiH：水平像素密度，dpiV：垂直像素密度，screenH：水平屏幕宽度（dip），screenV：垂直屏幕宽度（dip），phoneType：手机机型（Android返回0：NONE、1：GSM、2：CMDA、3：SIP），phoneNumber：手机号码，communicationType：运营商类型，simSerialNumber：SIM卡的序列号，IMSI：IMSI（国际移动用户识别码）
- 说明: 获取设备相关信息，如：唯一设备ID、设备名称、系统类型、系统版本号、分辨率大小、IMSI等
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=getAllAppInfo><font color ='#0092db'>**getAllAppInfo**</font></span>: 获取应用信息

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: [{'name':'app的名称'，'pname':'app的包名','isSystem':'是否为系统应用，0 不是，1 是','traffic':'app使用的流量，单位byte'},...]
- 说明: 获取当前系统所以应用相关信息，暂时只支持获取每个应用流量使用信息（仅Android支持）
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=getLocale><font color ='#0092db'>**getLocale**</font></span>: 获取系统环境

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: [{'country':'系统国家','language':'当前语言']
- 说明: 获取当前系统设置的国家和语言
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=home><font color ='#0092db'>**home**</font></span>: 应用退到后台

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 模仿iOS系统中点击home键的效果，让应用退到后台，仅支持android平台
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=setScreenAutoDarken><font color ='#0092db'>**setScreenAutoDarken**</font></span>: 控制锁屏

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **isAuto** |<font color ='#808000'>**Boolean**</font> | 否 | true|为true时与系统设置保持一致，到了系统设置的自动锁屏时间则自动熄灭屏幕并锁屏；为false时则屏幕常亮，且不锁屏
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 控制系统锁屏
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=getBattery><font color ='#0092db'>**getBattery**</font></span>: 获取电量

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 返回电量百分比
- 说明: 获取当前设备电量信息
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=getLocationPermission><font color ='#0092db'>**getLocationPermission**</font></span>: 获取当前应用的位置权限

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 返回-2，系统版本小于iOS8，方法不可用；-1，当前应用没有开启位置权限；0，位置权限->使用应用期间；1，位置权限为始终；2，位置权限为永不
- 说明: iOS8.0以后，如果应用开启了位置权限授权，调用该方法可获取应用的的具体位置权限
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <span id=screenShot><font color ='#0092db'>**screenShot**</font></span>: 截屏

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **rect** |<font color ='#808000'>**string**</font> | 否 | |参数格式为 0,0,300,200，分别表示 x,y,width,height，当不填写该参数时截取当前屏幕的全部内容
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回截屏图片保存的地址，是一个data://temp/do_Device目录下一个图片文件，文件名是日期+时间
- 说明: 截取当前屏幕显示内容
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=srceenShotAsBitmap><font color ='#0092db'>**srceenShotAsBitmap**</font></span>: 截屏

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **bitmap** |<font color ='#808000'>**string**</font> | 是 | |
  **rect** |<font color ='#808000'>**string**</font> | 否 | |参数格式为 0,0,300,200，分别表示 x,y,width,height，当不填写该参数时截取当前屏幕的全部内容
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 截取当前屏幕显示内容
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=getGPSInfo><font color ='#0092db'>**getGPSInfo**</font></span>: 获取设备GPS信息

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: [{'state':'当前设备GPS状态']，其中state为0表示关闭，为1表示打开
- 说明: 获取设备的GPS信息
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=getRingerMode><font color ='#0092db'>**getRingerMode**</font></span>: 获取设备声音状态

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {'mode':'当前设备声音状态'}，其中mode为0表示静音模式，为1表示正常模式
- 说明: 有两个值,分别是静音模式还是正常模式
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件


