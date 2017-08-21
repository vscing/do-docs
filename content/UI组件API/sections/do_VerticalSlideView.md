---
title: do_VerticalSlideView 组件
---

### do_VerticalSlideView 组件

 支持平台: iOS7.0,Android4.0
 这个UI组件包含多个子视图(UI文件），实现多个子视图之间上下平缓滑动效果，该组件还支持设置多个不同模板视图

#### <font color ='#40A977'>**1.**</font> 属性

>###### <font color ='#42b983'>**allowGesture**</font>: 是否支持手势滑动

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : true
- 说明 : 当属性值为true时，组件可通过手势上下滑动来切换页面；为false时，手势无法滑动，只能通过修改index来切换页面，windowsPC平台不支持

>###### <font color ='#42b983'>**index**</font>: 当前滑动UIView索引

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 0
- 说明 : 设置滑动视图索引值，默认为0

>###### <font color ='#42b983'>**templates**</font>: 显示视图对应UI模板文件

- 数据类型 : <font color ='#808000'>**object**</font>
- 默认值 : 
- 说明 : 可以设置一个或多个UI模板文件，值为String类型，多个模板之间分别用“,”分隔，例如：“source://view/temp/t0.ui, source://view/temp/t1.ui”

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**bindItems**</font>: 绑定视图模板数据

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **data** |<font color ='#808000'>**object**</font> |  | 否||
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 绑定数据类型为do_ListData实例
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**refreshItems**</font>: 刷新数据

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 支持动态刷新当前视图显示数据
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <font color ='#e96900'>**indexChanged**</font>: 滑动显示当前视图后触发该事件

- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 返回当前index
- 说明: 滑动显示当前视图后触发该事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


