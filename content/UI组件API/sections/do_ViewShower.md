---
title: do_ViewShower 组件
---

### do_ViewShower 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_ViewShower)
 ViewShower是一个包含多个子VIew的UI容器组件，每个子View的大小和容器大小一致，切换每个View可以添加动画效果，并且可以保持每个View的最后显示状态，支持动态的添加或删除。因为每一个子View在内存里都有对应的对象，所以用户不能在这个容器里添加太多子View。通常这个组件用于整个App的主界面，和底部一个BottomBar结合使用，点击底部按钮，切换不同的视图。

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#0092db'>同步方法</font>  |[showView](#showView)| 切换View
<font color ='#0092db'>同步方法</font>  |[addViews](#addViews)| 增加多个View
<font color ='#0092db'>同步方法</font>  |[removeView](#removeView)| 删除某个View
<font color ='#0092db'>同步方法</font>  |[getView](#getView)| 获取子View
<font color ='#e96900'>事件</font>  |[viewChanged](#viewChanged)| View切换完成时触发

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=showView><font color ='#0092db'>**showView**</font></span>: 切换View

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **id** |<font color ='#808000'>**string**</font> | 是 | |切换的目标View的 ID
  **animationType** |<font color ='#808000'>**string**</font> | 否 | |winphone8不支持该动画效果，android和ios支持。
目前支持以下几种：
'slide_l2r': 从左至右滑出
'slide_r2l': 从右至左滑出
'slide_b2t': 从底至上滑出
'slide_t2b': 从上至底滑出
'push_l2r': 从左至右推出
'push_r2l': 从右至左推出
'push_b2t': 从底至上推出
'push_t2b': 从上至底推出
'fade' : 淡入淡出
'page_curl' : 上翻页
'page_uncurl' : 下翻页
'cube' :立体翻转
  **animationTime** |<font color ='#808000'>**number**</font> | 否 | 300|动画效果持续时间，单位为ms毫秒
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=addViews><font color ='#0092db'>**addViews**</font></span>: 增加多个View

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **data** |<font color ='#808000'>**object**</font> | 是 | |要增加的View的索引，默认值为增加到最后，如果id已经存在，会覆盖之前的View，结构[{ id : '', path : ''},{id :'' , path : ''}, ..... ]
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=removeView><font color ='#0092db'>**removeView**</font></span>: 删除某个View

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **id** |<font color ='#808000'>**string**</font> | 是 | |要删除的View的id
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=getView><font color ='#0092db'>**getView**</font></span>: 获取子View

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **id** |<font color ='#808000'>**string**</font> | 是 | |要获取的View的id
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 子view对应的ui文件RootView地址
- 说明: 获取某个子view对应的ui文件RootView地址
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=viewChanged><font color ='#e96900'>**viewChanged**</font></span>: View切换完成时触发

- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回View切换后的id
- 说明: View切换完成时触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


