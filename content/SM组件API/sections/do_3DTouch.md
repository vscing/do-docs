---
title: do_3DTouch 组件
---

### do_3DTouch 组件

 支持平台: iOS,Android 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_3DTouch)
 目前支持桌面快捷菜单，最多只能添加4个；因苹果特性，该功能只有在第二次启动App时生效

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#0092db'>同步方法</font>  |[addShortcutItem](#addShortcutItem)| 添加桌面快捷菜单
<font color ='#0092db'>同步方法</font>  |[removeShortcutItem](#removeShortcutItem)| 删除桌面快捷菜单
<font color ='#e96900'>事件</font>  |[touch](#touch)| 点击item触发

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=addShortcutItem><font color ='#0092db'>**addShortcutItem**</font></span>: 添加桌面快捷菜单

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **id** |<font color ='#808000'>**string**</font> | 是 | |快捷菜单中Item的唯一标示
  **title** |<font color ='#808000'>**string**</font> | 是 | |
  **icon** |<font color ='#808000'>**string**</font> | 是 | |显示的图标，目前只支持官方提供的图标，DeviceOne集成了官方图标，修改了短码，具体详见http://doc.deviceone.net/web/doc/detail_course/third_party/3DTouch.htm
  **subTitle** |<font color ='#808000'>**string**</font> | 否 | |Item的子标题
  **userInfo** |<font color ='#808000'>**object**</font> | 否 | |自定义内容，为空或者json字符串
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=removeShortcutItem><font color ='#0092db'>**removeShortcutItem**</font></span>: 删除桌面快捷菜单

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **id** |<font color ='#808000'>**object**</font> | 是 | |快捷菜单中Item的唯一标示，如['id1','id2'...]
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=touch><font color ='#e96900'>**touch**</font></span>: 点击item触发

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回值包括，{'id':'','title':'','subTitle':'','userInfo':''}
- 说明: 点击item触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


