---
title: LePlayerVod 组件
---

### LePlayerVod 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/LePlayerVod)
 乐视云提供的视频点播功能，http://www.lecloud.com/zh-cn/product/vod.html

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#0092db'>同步方法</font>  |[playByID](#playByID)| 根据视频的uuid播放视频

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=playByID><font color ='#0092db'>**playByID**</font></span>: 根据视频的uuid播放视频

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **uuid** |<font color ='#808000'>**string**</font> | 是 | |
  **vuid** |<font color ='#808000'>**string**</font> | 是 | |
  **payerName** |<font color ='#808000'>**string**</font> | 否 | 0|付费用户权限的验证
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 参考：http://static.letvcloud.com/wiki/doc/%E4%B9%90%E8%A7%86%E4%BA%91%E7%82%B9%E6%92%AD%E6%92%AD%E6%94%BESDK4.1.1-Android%E7%AB%AF%E4%BD%BF%E7%94%A8%E6%96%87%E6%A1%A3.pdf  通过UUID和VUID播放视频配置
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件


