---
title: do_AssistiveTouch 组件
---

### do_AssistiveTouch 组件

* 支持平台: iOS7.0,Android4.0
可用于模拟类似iOS设备的AssistiveTouch按钮，支持自定义样式和大小；android平台需要通过订阅page组件的pause和result事件来控制组件的显示和隐藏

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**showView**</font>: 显示辅助按钮

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **location** |<font color ='#808000'>**string**</font> |  | 是||x,y，中间用逗号隔开
  **image** |<font color ='#808000'>**string**</font> |  | 是||图片地址，支持source://、data://路径
  **isMove** |<font color ='#808000'>**Boolean**</font> | true | 否|true|view是否支持移动，缺省支持
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 可设置view的样式、位置和是否移动
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**hideView**</font>: 隐藏辅助按钮

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

>###### <font color ='#e96900'>**touch**</font>: 点击view触发

- 返回值类型 : <font color ='#808000'>****</font>
- 返回值描述: 
- 说明: 点击view触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


