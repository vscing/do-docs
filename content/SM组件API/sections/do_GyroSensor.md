---
title: do_GyroSensor 组件
---

### do_GyroSensor 组件

 支持平台: iOS7.0,Android4.0
 绕x/y/z三轴旋转的三个角度取值范围为 ±180，其中角度的正负遵循右手原则，即右手大拇指伸直，其余四指握拳，大拇指指向数轴，手指指向的方向为正，相反为负。Windows平台不支持

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**getGyroData**</font>: 获取角度

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {x:'绕x轴旋转的角度’,y:’绕y轴旋转的角度’,z:’绕z轴旋转的角度’}
- 说明: 手机绕三个方向旋转的角度值
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**start**</font>: 开始采集数据

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**stop**</font>: 停止采集数据

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**getAccelerometerData**</font>: 获取加速度

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {x:'x轴的加速度',y:'y轴的加速度',z:'z轴的加速度'}
- 说明: 手机绕三个方向运动的加速度
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <font color ='#e96900'>**change**</font>: 加速度变化触发

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {x:'绕x轴旋转的角度’,y:’绕y轴旋转的角度’,z:’绕z轴旋转的角度’}
- 说明: 加速度变化触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


