---
title: do_TouchID 组件
---

### do_TouchID 组件

 支持平台: iOS8.0,Android
 iPhone 5s以后版本的手机特有的指纹识别功能，调用此模块可实现用户指纹输入验证登陆app 。使用本模块需要支持指纹识别的手机和ios8.0以上的操作系统

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <font color ='#0092db'>**evaluate**</font>: 指纹验证

- 参数:

  名称 | 类型 |是否必填|缺省值|说明
  ---- |-------------  |--------------|--------|------
  **title** |<font color ='#808000'>**string**</font> | 指纹验证 | 否|使用touchID的原因
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {code:0： 认证失败；1：用户取消验证；2：选择输入密码；3：系统取消认证；4：未设置密码,无法开启认证；5：当前设备未录入指纹信息；6:当前设备不支持指纹识别,status:true||false}
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件


