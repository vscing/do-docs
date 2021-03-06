---
title: do_Page 组件
---

### do_Page 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_Page)
 应用程序基本页面类，包括UI布局和逻辑代码。每一个移动应用都是由多个Page一层层的叠加来组成。在当前Page的基础上打开新的Page，新的Page打开后会盖住底部的Page，当新的Page关闭后，又会露出底部的Page。
每一个Page都有自己的脚本运行环境，Page内所有的组件都公用这一个脚本环境。

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#0092db'>同步方法</font>  |[getData](#getData)| 获取从上一层page传递过来的数据
<font color ='#0092db'>同步方法</font>  |[remove](#remove)| 删除子ui
<font color ='#0092db'>同步方法</font>  |[hideKeyboard](#hideKeyboard)| 隐藏软键盘
<font color ='#0092db'>同步方法</font>  |[supportPanClosePage](#supportPanClosePage)| 手势滑动关闭页面
<font color ='#e96900'>事件</font>  |[back](#back)| 点击设备物理或虚拟返回按键触发事件（Android、WindowsPhone有效）
<font color ='#e96900'>事件</font>  |[menu](#menu)| 点击设备物理或虚拟菜单按键触发事件（Android、WindowsPhone有效）
<font color ='#e96900'>事件</font>  |[loaded](#loaded)| 页面加载完触发事件
<font color ='#e96900'>事件</font>  |[resume](#resume)| 回到前台、Page回到顶端时触发或打开当前页面
<font color ='#e96900'>事件</font>  |[pause](#pause)| 进入后台、被其他Page盖住或关闭当前页面时触发
<font color ='#e96900'>事件</font>  |[result](#result)| 上层Page关闭时触发
<font color ='#e96900'>事件</font>  |[keyDown](#keyDown)| 点击设备物理或虚拟返回按键触发事件（Android、WindowsPhone有效）

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=getData><font color ='#0092db'>**getData**</font></span>: 获取从上一层page传递过来的数据

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 传递过来的数据
- 说明: 弹出新的page，通过data来传递数据。
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=remove><font color ='#0092db'>**remove**</font></span>: 删除子ui

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **id** |<font color ='#808000'>**string**</font> | 是 | |通过子ui的id和地址获取到子ui，然后删除
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 删除Page里一个子UI
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=hideKeyboard><font color ='#0092db'>**hideKeyboard**</font></span>: 隐藏软键盘

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 找到当前page是否有键盘弹出，然后把焦点释放，键盘隐藏
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=supportPanClosePage><font color ='#0092db'>**supportPanClosePage**</font></span>: 手势滑动关闭页面

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **data** |<font color ='#808000'>**string**</font> | 否 | |
  **support** |<font color ='#808000'>**Boolean**</font> | 否 | true|单独设置某页支持手势关闭
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 可通过与openPage动画相反手势关闭页面，并从当前页面传递data给下层页面，仅支持iOS平台
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=back><font color ='#e96900'>**back**</font></span>: 点击设备物理或虚拟返回按键触发事件（Android、WindowsPhone有效）

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 
- 说明: 点击设备物理或虚拟返回按键触发事件（Android、WindowsPhone有效）
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <span id=menu><font color ='#e96900'>**menu**</font></span>: 点击设备物理或虚拟菜单按键触发事件（Android、WindowsPhone有效）

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 
- 说明: 点击设备物理或虚拟菜单按键触发事件（Android、WindowsPhone有效）
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <span id=loaded><font color ='#e96900'>**loaded**</font></span>: 页面加载完触发事件

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 
- 说明: 页面加载完触发事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <span id=resume><font color ='#e96900'>**resume**</font></span>: 回到前台、Page回到顶端时触发或打开当前页面

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 
- 说明: 回到前台、Page回到顶端时触发或打开当前页面
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <span id=pause><font color ='#e96900'>**pause**</font></span>: 进入后台、被其他Page盖住或关闭当前页面时触发

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 
- 说明: 进入后台、被其他Page盖住或关闭当前页面时触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <span id=result><font color ='#e96900'>**result**</font></span>: 上层Page关闭时触发

- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 上层Page关闭的时候会触发下层Page一个result事件。并返回上层页面关闭时传递过来的数据
- 说明: 上层Page关闭时触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <span id=keyDown><font color ='#e96900'>**keyDown**</font></span>: 点击设备物理或虚拟返回按键触发事件（Android、WindowsPhone有效）

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {keyCode:对应按键的值}
- 说明: 点击设备物理或虚拟返回按键触发事件（Android、WindowsPhone有效）
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


