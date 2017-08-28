---
title: do_TencentWebView 组件
---

### do_TencentWebView 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_TencentWebView)
 集成了腾讯x5内核,可以加载html网页，拥有强大的视频播放功能

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#42b983'>属性</font>  |[bounces](#bounces)| 反弹效果
<font color ='#42b983'>属性</font>  |[cacheType](#cacheType)| 缓存类型
<font color ='#42b983'>属性</font>  |[isShowLoadingProgress](#isShowLoadingProgress)| 是否显示进度条
<font color ='#42b983'>属性</font>  |[url](#url)| 网页地址
<font color ='#42b983'>属性</font>  |[zoom](#zoom)| 手势缩放
<font color ='#42b983'>属性</font>  |[userAgent](#userAgent)| 浏览器标识
<font color ='#0092db'>同步方法</font>  |[back](#back)| 回退
<font color ='#0092db'>同步方法</font>  |[forward](#forward)| 前进
<font color ='#0092db'>同步方法</font>  |[reload](#reload)| 重新加载
<font color ='#0092db'>同步方法</font>  |[stop](#stop)| 停止刷新
<font color ='#0092db'>同步方法</font>  |[canForward](#canForward)| 是否可继续前进
<font color ='#0092db'>同步方法</font>  |[canBack](#canBack)| 是否可后退
<font color ='#0092db'>同步方法</font>  |[setCookie](#setCookie)| 设置cookie
<font color ='#0092db'>同步方法</font>  |[setLoadingProgressColor](#setLoadingProgressColor)| 设置顶部进度条颜色
<font color ='#0092db'>同步方法</font>  |[setDefaultEncodingURL](#setDefaultEncodingURL)| 设置默认转码
<font color ='#0092db'>同步方法</font>  |[getContentSize](#getContentSize)| 获取加载页面内容尺寸
<font color ='#0092db'>异步方法</font>  |[loadString](#loadString)| 加载html字符串
<font color ='#0092db'>异步方法</font>  |[eval](#eval)| 执行JavaScript函数
<font color ='#e96900'>事件</font>  |[loaded](#loaded)| 加载结束事件
<font color ='#e96900'>事件</font>  |[start](#start)| 开始加载
<font color ='#e96900'>事件</font>  |[failed](#failed)| 加载错误事件

#### <font color ='#40A977'>**1.**</font> 属性

>###### <span id=bounces><font color ='#42b983'>**bounces**</font></span>: 反弹效果

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : true
- 说明 : 只支持iOS平台，为false时没有上拉下拉的反弹效果

>###### <span id=cacheType><font color ='#42b983'>**cacheType**</font></span>: 缓存类型

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : no_cache
- 说明 : 改变WebView的缓存方式，缺省值为no_cache表示不使用缓存；为normal时根据cache-control决定是否获取新数据；windows平台不支持

>###### <span id=isShowLoadingProgress><font color ='#42b983'>**isShowLoadingProgress**</font></span>: 是否显示进度条

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : false
- 说明 : 组件的顶部有一个绿色进度条，显示加载网页的进度，缺省false不显示

>###### <span id=url><font color ='#42b983'>**url**</font></span>: 网页地址

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 : 支持http://,https://,支持source://,data://文件格式。文件格式的说明可以参考Storage类

>###### <span id=zoom><font color ='#42b983'>**zoom**</font></span>: 手势缩放

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : false
- 说明 : 设置组件是否支持手势缩小放大，设置为true时支持

>###### <span id=userAgent><font color ='#42b983'>**userAgent**</font></span>: 浏览器标识

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 : 设置浏览器的User-Agent

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=back><font color ='#0092db'>**back**</font></span>: 回退

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=forward><font color ='#0092db'>**forward**</font></span>: 前进

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=reload><font color ='#0092db'>**reload**</font></span>: 重新加载

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=stop><font color ='#0092db'>**stop**</font></span>: 停止刷新

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=canForward><font color ='#0092db'>**canForward**</font></span>: 是否可继续前进

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: 返回是否可继续前进
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=canBack><font color ='#0092db'>**canBack**</font></span>: 是否可后退

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: 检查是否有可以后退的历史记录
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=setCookie><font color ='#0092db'>**setCookie**</font></span>: 设置cookie

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **url** |<font color ='#808000'>**string**</font> | 是 | |如果加载该域名地址，会自动把cookie传给服务器
  **value** |<font color ='#808000'>**string**</font> | 是 | |
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 设置浏览器的cookie
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=setLoadingProgressColor><font color ='#0092db'>**setLoadingProgressColor**</font></span>: 设置顶部进度条颜色

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **color** |<font color ='#808000'>**string**</font> | 是 | |颜色值格式为：8位16进制字符，前6位是RGB颜色值，后两位是透明度（Alpha），例如：000000FF
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 设置加载html页面时，组件顶部进度条的颜色
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=setDefaultEncodingURL><font color ='#0092db'>**setDefaultEncodingURL**</font></span>: 设置默认转码

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **isEncode** |<font color ='#808000'>**Boolean**</font> | 否 | true|默认按照utf-8编码方式转码，设置为false则不对原url进行处理
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 设置是否对url默认按照utf-8编码格式转码，仅支持iOS平台
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=getContentSize><font color ='#0092db'>**getContentSize**</font></span>: 获取加载页面内容尺寸

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回{width,height}
- 说明: 获取当前加载页面真实内容的宽高，windows平台不支持
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <span id=loadString><font color ='#0092db'>**loadString**</font></span>: 加载html字符串

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **text** |<font color ='#808000'>**string**</font> | 是 | |
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=eval><font color ='#0092db'>**eval**</font></span>: 执行JavaScript函数

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **code** |<font color ='#808000'>**string**</font> | 是 | |
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 无
- 说明: 在页面执行一段Javascript代码，并返回值
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=loaded><font color ='#e96900'>**loaded**</font></span>: 加载结束事件

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回{url}，其中url表示当前操作的url地址，该地址不一定为网络地址，本地html页面跳转也会触发并返回本地路径
- 说明: 加载结束事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <span id=start><font color ='#e96900'>**start**</font></span>: 开始加载

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回{url}，其中url表示当前操作的url地址，该地址不一定为网络地址，本地html页面跳转也会触发并返回本地路径
- 说明: 开始加载
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <span id=failed><font color ='#e96900'>**failed**</font></span>: 加载错误事件

- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 加载网页失败或加载一个错误的或者不存在的网页时触发，返回错误信息
- 说明: 加载错误事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


