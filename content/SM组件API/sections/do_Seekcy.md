---
title: do_Seekcy 组件
---

### do_Seekcy 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_Seekcy)
 

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#0092db'>同步方法</font>  |[startScan](#startScan)| 扫描寻息Beacon
<font color ='#0092db'>同步方法</font>  |[stopScan](#stopScan)| 停止扫描寻息Beacon
<font color ='#e96900'>事件</font>  |[result](#result)| 扫描到Beacon设备,每隔一段时间更新

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=startScan><font color ='#0092db'>**startScan**</font></span>: 扫描寻息Beacon

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {“state”}，state返回三种状态：0-状态正常；1-设备不支持；2-蓝牙没打开
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=stopScan><font color ='#0092db'>**stopScan**</font></span>: 停止扫描寻息Beacon

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


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=result><font color ='#e96900'>**result**</font></span>: 扫描到Beacon设备,每隔一段时间更新

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: [{"distance":"距离,单位米","mac":"mac地址","major":"主要值","minor":"次要值","power":"电量","rssi":"场强"}]
- 说明: 扫描到Beacon设备,每隔一段时间更新
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


