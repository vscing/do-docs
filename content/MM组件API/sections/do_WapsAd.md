---
title: do_WapsAd 组件
---

### do_WapsAd 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_WapsAd)
 支持条幅广告，不支持windows平台

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#0092db'>同步方法</font>  |[show](#show)| 显示广告
<font color ='#0092db'>同步方法</font>  |[getHeight](#getHeight)| 获取广告高度
<font color ='#0092db'>同步方法</font>  |[close](#close)| 关闭广告

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=show><font color ='#0092db'>**show**</font></span>: 显示广告

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **y** |<font color ='#808000'>**string**</font> | 否 | 0|广告显示的y轴位置，默认顶头显示
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 在指定位置显示广告
- 示例:

  ```javascript
  do_WapsAd.show({y:800});

  ```

[回到顶部](#top)

>##### <span id=getHeight><font color ='#0092db'>**getHeight**</font></span>: 获取广告高度

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 返回广告显示的高度
- 说明:
- 示例:

  ```javascript
  var height = do_WapsAd.getHeight();

  ```

[回到顶部](#top)

>##### <span id=close><font color ='#0092db'>**close**</font></span>: 关闭广告

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明:
- 示例:

  ```javascript
  do_WapsAd.close()

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件
