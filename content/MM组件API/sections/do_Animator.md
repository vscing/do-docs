---
title: do_Animator 组件
---

### do_Animator 组件

 支持平台: iOS7.0,Android4.0
 控制UI组件动画的状态变化，每个状态点都支持对应5种属性的变化:x, y, width,height,bgColor；也支持修改透明值alpha，如50表示半透明，若同时用bgColor的后两位和alpha修改了透明值，以alpha为主，若alpha为父容器，则里面的子组件的透明值也随着改变

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**append**</font>: 创建属性动画

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **duration** |<font color ='#808000'>**number**</font> |  | 是||单位为毫秒
  **props** |<font color ='#808000'>**object**</font> |  | 否||这是一个JSON node节点，包含多个参数，参数集合如下：{'x':10,'y':50,'height':500...}为空时表示状态不变
  **curve** |<font color ='#808000'>**string**</font> | Linear | 否|Linear|支持四种情况：1.'EaseInOut'动画启动时候慢，中间快，结束的时候慢、2.'EaseIn'动画启动的时候慢、3.'EaseOut'动画结束的时候慢、4.'Linear'动画速度不变
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 创建属性动画
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件


