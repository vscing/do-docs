---
title: do_SwitchView 组件
---

### do_SwitchView 组件

 支持平台: iOS7.0,Android4.0
 SwitchView 是一个带有开关选择的UI组件，只有（开，关）两种状态，点击或拽动改变状态，该组件的样式是跟随系统，各平台显示效果不完全一样 ，可以应用于是否记住密码场景和一些具有布尔类型的配置页面

#### <font color ='#40A977'>**1.**</font> 属性

>###### <font color ='#42b983'>**checked**</font>: 是否选中

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : false
- 说明 : 设置当前状态，默认为不选中状态

>###### <font color ='#42b983'>**shape**</font>: 组件形状

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : circle
- 说明 : 设置组件形状，有两种形状，rect矩形，circle圆形

>###### <font color ='#42b983'>**colors**</font>: 组件状态颜色

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 00FF00,888888,FFFFFF
- 说明 : SwitchView 各种状态的颜色：open的背景颜色值，close的背景颜色值，slider的背景颜色值， 默认值为：“00FF00,888888,FFFFFF”

#### <font color ='#40A977'>**2.**</font> 同步方法

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <font color ='#e96900'>**changed**</font>: 开关状态触发

- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: 当前状态
- 说明: 开关状态触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


