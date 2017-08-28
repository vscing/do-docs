---
title: do_GestureCipher 组件
---

### do_GestureCipher 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_GestureCipher)
 可以创建九宫格手势密码并且验证是否正确

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#0092db'>异步方法</font>  |[set](#set)| 设置手势密码
<font color ='#0092db'>异步方法</font>  |[validate](#validate)| 验证手势密码

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <span id=set><font color ='#0092db'>**set**</font></span>: 设置手势密码

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: 设置成功返回true,否则返回false
- 说明: 会有两次设置机会,两次设置相同则设置成功,
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=validate><font color ='#0092db'>**validate**</font></span>: 验证手势密码

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **patternDisplay** |<font color ='#808000'>**string**</font> | 否 | false|默认不可见
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: 验证成功返回true，否则返回false
- 说明: 验证手势密码是否正确
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件


