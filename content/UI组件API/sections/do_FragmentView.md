---
title: do_FragmentView 组件
---

### do_FragmentView 组件

 支持平台: iOS7.0,Android14 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_FragmentView)
 支持从最左侧或右侧边缘滑出视图，整体侧滑视图带有缩放和渐变效果；

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#42b983'>属性</font>  |[supportGesture](#supportGesture)| 支持手势滑动
<font color ='#42b983'>属性</font>  |[templates](#templates)| 显示视图对应UI模板文件
<font color ='#42b983'>属性</font>  |[allowAnimation](#allowAnimation)| 动画缩放效果
<font color ='#0092db'>同步方法</font>  |[reset](#reset)| 重置为初始视图
<font color ='#0092db'>同步方法</font>  |[showLeft](#showLeft)| 显示左侧视图
<font color ='#0092db'>同步方法</font>  |[showRight](#showRight)| 显示右侧视图
<font color ='#0092db'>同步方法</font>  |[bindItems](#bindItems)| 绑定视图模板数据
<font color ='#0092db'>同步方法</font>  |[refreshItems](#refreshItems)| 刷新数据

#### <font color ='#40A977'>**1.**</font> 属性

>###### <span id=supportGesture><font color ='#42b983'>**supportGesture**</font></span>: 支持手势滑动

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : both
- 说明 : 包含三种类型，缺省both表示同时支持左右滑动

>###### <span id=templates><font color ='#42b983'>**templates**</font></span>: 显示视图对应UI模板文件

- 数据类型 : <font color ='#808000'>**object**</font>
- 默认值 : 
- 说明 : 可以设置一个或多个UI模板文件，值为String类型，多个模板之间分别用“,”分隔，例如：“source://view/temp/content.ui,source://view/temp/left.ui”

>###### <span id=allowAnimation><font color ='#42b983'>**allowAnimation**</font></span>: 动画缩放效果

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : false
- 说明 : 允许滑动或显示时有动画缩放展示效果

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=reset><font color ='#0092db'>**reset**</font></span>: 重置为初始视图

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=showLeft><font color ='#0092db'>**showLeft**</font></span>: 显示左侧视图

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=showRight><font color ='#0092db'>**showRight**</font></span>: 显示右侧视图

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=bindItems><font color ='#0092db'>**bindItems**</font></span>: 绑定视图模板数据

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **data** |<font color ='#808000'>**object**</font> | 否 | |
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 可绑定listData实例，addData数据内容为JSON字符串，key值分别为：template（主视图），leftTemplate（左侧视图，可选），rightTemplate（右侧视图，可选），value对应templates属性对应UI模板索引值；例如：[{ template:0 ,leftTemplate:1}]
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=refreshItems><font color ='#0092db'>**refreshItems**</font></span>: 刷新数据

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 支持动态刷新当前视图显示数据
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件


