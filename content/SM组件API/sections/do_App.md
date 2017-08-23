---
title: do_App 组件
---

### do_App 组件

 支持平台: iOS7.0,Android4.0
 这个是DeviceOne提供的基本应用类，通常在DeviceOne里开发的一个工程项目就是一个App实例。这个类负责页面Page的基本跳转，和App作用域内的数据共享等。

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**getAppID**</font>: 当前App的唯一ID

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: App的ID
- 说明: 应用内可以用多个App实例，这个id作为多个App区分的唯一标识。
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <font color ='#0092db'>**openPage**</font>: 弹出新的页面

- 参数:

  名称 | 类型 |是否必填|缺省值|说明
  ---- |-------------  |--------------|--------|------
  **source** |<font color ='#808000'>**string**</font> |  | 是|路径支持source://和data://目录。关于文件协议说明可以参考Storage类。
  **data** |<font color ='#808000'>**string**</font> |  | 否|页面之间的数据传递。比如在页面A的基础上弹出页面B，页面A可以通过data参数把数据传递到页面B，页面B可以通过Page的getData方法来获取传递过来的数据
  **animationType** |<font color ='#808000'>**string**</font> | slide_r2l | 否|winphone8不支持该动画效果，android和ios支持。目前支持以下几种：
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
'slide_l2r_1'：从左至右滑出（旧页淡出效果）
'slide_r2l_1'：从右至左滑出（旧页淡出效果）
'push_l2r_1': 从左至右推出（旧页被遮盖）
'push_r2l_1': 从右至左推出（旧页被遮盖）
  **keyboardMode** |<font color ='#808000'>**string**</font> | hidden | 否|当屏幕中有焦点时是否弹出软键盘（default--跟系统保持一致[已废弃]，visible--总是弹出，hidden--总是隐藏）
  **scriptType** |<font color ='#808000'>**string**</font> |  | 否|若参数有值，则打开的ui文件对应的脚本文件就是这个参数对应的文件。比如若参数有值，且为javascr，则打开xx.ui.js否则打开xx.ui.lua，若参数没有值，则打开系统全局配置的语言类型脚本文件
  **statusBarState** |<font color ='#808000'>**string**</font> | show | 否|打开一个新的page的时候，控制顶部状态栏显示的状态，有三种值show:缺省值，表示顶部状态栏显示，所有视图都是从状态栏下开始显示；hide: 表示状态栏消失，所有视图都是从屏幕最顶端开始显示；transparent:表示状态栏透明，所有视图是从屏幕最顶端开始显示，可以透过状态栏看到底下的视图。 该属性android只有4.4版本后支持
  **statusBarFgColor** |<font color ='#808000'>**string**</font> | white | 否|打开一个新的page的时候，如果不是全屏的话，顶部状态栏字体的前景色，只能为'white'和'black'两种值，仅支持iOS平台
  **statusBarBgColor** |<font color ='#808000'>**string**</font> | 000000FF | 否|打开一个新的page的时候，如果不是全屏的话，顶部状态栏背景色，默认值为000000FF(黑色)
  **id** |<font color ='#808000'>**string**</font> |  | 否|打开一个新的page的时候，增加一个打开的Page的唯一标示，id不能重复，如果重复则从上往下找到第一个为准
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 在目前的Page基础上弹出新的Page，每一个Page都是扩充全屏，多个Page一级级覆盖，只有关闭了上层Page，才能看到下层Page
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**closePage**</font>: 关闭最上层页面

- 参数:

  名称 | 类型 |是否必填|缺省值|说明
  ---- |-------------  |--------------|--------|------
  **data** |<font color ='#808000'>**string**</font> |  | 否|
  **animationType** |<font color ='#808000'>**string**</font> |  | 否|不设置时，默认取openPge动画所对应配套的关闭动画，例如openPage中是从左至右滑出，则配套关闭为从右至左。
winphone8不支持该动画效果，android和ios支持。
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
  **layer** |<font color ='#808000'>**number**</font> | 1 | 否|表示连续关闭多个page的次数，缺省是1，设置为任何小于1的数字都表示1表示只关闭当前页面。如果这个值大于1，则只有一次动画效果，result事件只会触发一次，中间关闭的页面不会有动画也不会触发result事件
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 上层Page关闭的时候会触发下层Page一个result事件，这个事件可以把数据传递到下层Page
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**closePageToID**</font>: 关闭指定页面

- 参数:

  名称 | 类型 |是否必填|缺省值|说明
  ---- |-------------  |--------------|--------|------
  **data** |<font color ='#808000'>**string**</font> |  | 否|
  **animationType** |<font color ='#808000'>**string**</font> |  | 否|不设置时，默认取openPge动画所对应配套的关闭动画，例如openPage中是从左至右滑出，则配套关闭为从右至左。
winphone8不支持该动画效果，android和ios支持。
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
  **id** |<font color ='#808000'>**string**</font> |  | 否|
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 可以关闭指定页面，指定的id为openPage时定义的；上层Page关闭的时候会触发下层Page一个result事件，这个事件可以把数据传递到下层Page；当id为空时只关闭一层页面，id找不到时会报错
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**update**</font>: 更新页面数据

- 参数:

  名称 | 类型 |是否必填|缺省值|说明
  ---- |-------------  |--------------|--------|------
  **source** |<font color ='#808000'>**object**</font> |  | 否|仅支持data目录下一个或多个子目录或者文件，只处理能找到的文件或目录
  **target** |<font color ='#808000'>**string**</font> |  | 否|只允许是source目录，如果目录不存在，则创建对应的目录
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: 拷贝是否成功，false为失败，true为成功
- 说明: 支持从data目录下拷贝一个目录或文件到source目录下并覆盖原目录或文件；若为更新data目录下页面，则仅需先替换要更新的页面，再掉一下update方法，不用带参数即可
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件

>###### <font color ='#e96900'>**loaded**</font>: App启动完成时触发，通常这个事件是整个程序的入口。

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 
- 说明: App启动完成时触发，通常这个事件是整个程序的入口。
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


