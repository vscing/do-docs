---
title: do_AccelerometerSensor 组件
---

### do_AccelerometerSensor 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_AccelerometerSensor)
 Windows平台不支持

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#0092db'>同步方法</font>  |[getAccelerometerData](#getAccelerometerData)| 获取加速度
<font color ='#0092db'>同步方法</font>  |[start](#start)| 开始采集数据
<font color ='#0092db'>同步方法</font>  |[stop](#stop)| 停止采集数据
<font color ='#e96900'>事件</font>  |[shake](#shake)| 摇一摇
<font color ='#e96900'>事件</font>  |[change](#change)| 加速度变化触发

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=getAccelerometerData><font color ='#0092db'>**getAccelerometerData**</font></span>: 获取加速度

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {x:'x轴的加速度',y:'y轴的加速度',z:'z轴的加速度'}
- 说明: 手机绕三个方向运动的加速度
- 示例:

  ```javascript

  var getAccelerometerData = do_AccelerometerSensor.getAccelerometerData();
  deviceone.print(JSON.stringify(getAccelerometerData),"加速度");

  ```

  ```
  以下为上述代码返回的数据。
  {
    "x":0.6079864501953125,
    "y":-0.0974884033203125,
    "z":-0.8350982666015625
  }

  ```

[回到顶部](#top)

>##### <span id=start><font color ='#0092db'>**start**</font></span>: 开始采集数据

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明:
- 示例:

  ```javascript

  var do_AccelerometerSensor = sm("do_AccelerometerSensor");
  do_AccelerometerSensor.start();

  ```

[回到顶部](#top)

>##### <span id=stop><font color ='#0092db'>**stop**</font></span>: 停止采集数据

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明:
- 示例:

  ```javascript

  do_AccelerometerSensor.stop();

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=shake><font color ='#e96900'>**shake**</font></span>: 摇一摇

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述:
- 说明: 摇一摇
- 示例:

  ```javascript

  do_AccelerometerSensor.on("shake",function(data){
  	deviceone.print(JSON.stringify(data),"摇一摇");
  })

  ```

  ```

  以下为上述代码返回的数据。
  {
    "x":-2.0285797119140625,
    "y":-0.52130126953125,
    "z":-1.1815185546875
  }

  ```

[回到顶部](#top)

>###### <span id=change><font color ='#e96900'>**change**</font></span>: 加速度变化触发

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {x:'x轴的加速度',y:'y轴的加速度',z:'z轴的加速度'}
- 说明: 加速度变化触发
- 示例:

  ```javascript

  do_AccelerometerSensor.on("change",function(data){
  	deviceone.print(JSON.stringify(data),"加速度变化触发");
  })

  ```

  ```

  以下为上述代码返回的数据。
    {
      "x":0.0597076416015625,
      "y":-0.1566314697265625,
      "z":-0.9971771240234375
    }

  ```


[回到顶部](#top)
