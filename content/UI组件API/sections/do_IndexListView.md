---
title: do_IndexListView 组件
---

### do_IndexListView 组件

* 支持平台: iOS7.0,Android4.0
IndexListView实际上是一个界面右边带索引的ListView，可以绑定一个HashData数据源，按下滑动右边的索引，可以快速定位到该索引下的首条数据，主要应用于通讯录，歌曲播放器等界面

#### <font color ='#40A977'>**1.**</font> 属性

>###### <font color ='#42b983'>**indexBarColors**</font>: 索引颜色

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 00000000,C0C0C0,000000,00000000
- 说明 : 包含四个颜色，分别是索引列表背景色、按下索引背景色、索引文本颜色、滑块颜色，中间用逗号隔开，仅android平台支持

>###### <font color ='#42b983'>**selectedColor**</font>: Cell选中的背景颜色

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : ffffff00
- 说明 : 设置IndexListView 的按下选择颜色，如果在模板中设置rootLayout背景颜色，将不起作用

>###### <font color ='#42b983'>**templates**</font>: Cell对应的模板UI文件组

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 : 一个IndexListView可以有多个cell模板，这个属性包含多个source://开头的ui文件，中间用逗号隔开，格式类似如下：“source://view/cell1.ui,source://view/cell2.ui,source://view/cell3.ui”

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**bindItems**</font>: 绑定item的数据

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **data** |<font color ='#808000'>**object**</font> |  | 是||比如{'A':[{'template':0,'text':'a1'},{'template':1,'text':'a2'}],'B':[{'template':0,'text':'b1'},{'template':1,'text':'b2'}]}，其中每个group下第一条数据表示分组信息，不可点击
  **indexs** |<font color ='#808000'>**object**</font> |  | 否||一个数组列表，按照此列表显示列表数据，可以为空，为空就按照HashData‘随机’显示列表数据
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 为IndeListView绑定数据源，只支持HashData实例，其中每组第一条数据表示分组信息，不可点击
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**refreshItems**</font>: 刷新item数据

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 动态修改HashData数据源后，需要调用此方法才能正确显示数据
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <font color ='#e96900'>**touch**</font>: 点击cell触发

- 返回值类型 : <font color ='#808000'>**Node**</font>
- 返回值描述: 返回data中的groupID和group下的数据index，比如['groupID':'A','index':'2']
- 说明: 点击cell触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**longTouch**</font>: 长按cell触发

- 返回值类型 : <font color ='#808000'>**Node**</font>
- 返回值描述: 返回data中的groupID和group下的数据index，比如['groupID':'A','index':'2']
- 说明: 长按cell触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


