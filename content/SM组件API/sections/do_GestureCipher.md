---
title: do_GestureCipher 组件
---

### do_GestureCipher 组件

* 支持平台: iOS7.0,Android4.0
可以创建九宫格手势密码并且验证是否正确

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <font color ='#0092db'>**set**</font>: 设置手势密码

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: 设置成功返回true,否则返回false
- 说明: 会有两次设置机会,两次设置相同则设置成功,
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**validate**</font>: 验证手势密码

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **patternDisplay** |<font color ='#808000'>**string**</font> | false | 否|false|默认不可见
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: 验证成功返回true，否则返回false
- 说明: 验证手势密码是否正确
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件


