---
title: do_SlideView 组件
---

### do_SlideView 组件

 支持平台: iOS7.0,Android4.0
 这个UI组件包含多个子视图(UI文件），实现多个子视图之间左右平缓滑动效果，通过设置looping属性支持无限循环滑动，该组件还支持设置多个不同模板视图

#### <font color ='#40A977'>**1.**</font> 属性

>###### <font color ='#42b983'>**allowGesture**</font>: 是否支持手势滑动

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : true
- 说明 : 当属性值为true时，组件可通过手势左右滑动来切换页面；为false时，手势无法滑动，只能通过修改index来切换页面；Windows平台不支持

>###### <font color ='#42b983'>**isAllCache**</font>: 是否缓存页面状态（已废弃）

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : false
- 说明 : （不论设置成true和false，效果都为设置成true时一样）为true的时候每一条数据缓存一个View，对应的ui文件和js文件只会加载一次，对应的dataRefresh事件只会触发一次，以后不管如何左右滑动都不再加载和触发事件。如果数据不多，建议设置为true
为false时，可以复用View，对应的ui和js可能在来回滑动SlideView的时候会加载多次，而datarefreshed事件每次滑动到这一页就会触发一次。如果需要不想保留每一个页的状态变化，另外需加载较多数据的时候，建议使用false

>###### <font color ='#42b983'>**looping**</font>: 左右无限滑动

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : false
- 说明 : 左右无限循环滑动视图，设置值为true表示支持无限循环滑动，默认为false，windows不支持

>###### <font color ='#42b983'>**index**</font>: 当前滑动UIView索引

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 0
- 说明 : 设置滑动视图索引值，默认为0

>###### <font color ='#42b983'>**templates**</font>: 显示视图对应UI模板文件

- 数据类型 : <font color ='#808000'>**object**</font>
- 默认值 : 
- 说明 : 可以设置一个或多个UI模板文件，值为String类型，多个模板之间分别用“,”分隔，例如：“source://view/temp/t0.ui,source://view/temp/t1.ui”

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**bindItems**</font>: 绑定视图模板数据

- 参数:

  名称 | 类型 |是否必填|缺省值|说明
  ---- |-------------  |--------------|--------|------
  **data** |<font color ='#808000'>**object**</font> |  | 否|
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

>##### <font color ='#0092db'>**startLoop**</font>: 开始轮播

- 参数:

  名称 | 类型 |是否必填|缺省值|说明
  ---- |-------------  |--------------|--------|------
  **interval** |<font color ='#808000'>**number**</font> | 300 | 否|轮播间隔时间，单位为毫秒
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 当looping属性为true时，轮播会从右至左按index顺序循环；当looping为false时，顺序轮播完所有index页后再逆序轮播
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**stopLoop**</font>: 停止轮播

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 停止轮播
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**getView**</font>: 获取子View

- 参数:

  名称 | 类型 |是否必填|缺省值|说明
  ---- |-------------  |--------------|--------|------
  **index** |<font color ='#808000'>**string**</font> |  | 是|要获取的View的索引
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

>###### <font color ='#e96900'>**indexChanged**</font>: 滑动显示当前视图后触发该事件

- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 返回当前index
- 说明: 滑动显示当前视图后触发该事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**touch**</font>: 点击cell触发

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 当前cell的index值,如：{'index':1}
- 说明: 点击cell触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


