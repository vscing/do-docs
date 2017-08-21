---
title: do_TencentWebView 组件
---

### do_TencentWebView 组件

 支持平台: iOS7.0,Android4.0
 集成了腾讯x5内核,可以加载html网页，拥有强大的视频播放功能

#### <font color ='#40A977'>**1.**</font> 属性

>###### <font color ='#42b983'>**bounces**</font>: 反弹效果

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : true
- 说明 : 只支持iOS平台，为false时没有上拉下拉的反弹效果

>###### <font color ='#42b983'>**cacheType**</font>: 缓存类型

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : no_cache
- 说明 : 改变WebView的缓存方式，缺省值为no_cache表示不使用缓存；为normal时根据cache-control决定是否获取新数据；windows平台不支持

>###### <font color ='#42b983'>**isShowLoadingProgress**</font>: 是否显示进度条

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : false
- 说明 : 组件的顶部有一个绿色进度条，显示加载网页的进度，缺省false不显示

>###### <font color ='#42b983'>**url**</font>: 网页地址

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 : 支持http://,https://,支持source://,data://文件格式。文件格式的说明可以参考Storage类

>###### <font color ='#42b983'>**zoom**</font>: 手势缩放

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : false
- 说明 : 设置组件是否支持手势缩小放大，设置为true时支持

>###### <font color ='#42b983'>**userAgent**</font>: 浏览器标识

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 : 设置浏览器的User-Agent

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**back**</font>: 回退

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**forward**</font>: 前进

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**reload**</font>: 重新加载

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**stop**</font>: 停止刷新

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**canForward**</font>: 是否可继续前进

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: 返回是否可继续前进
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**canBack**</font>: 是否可后退

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: 检查是否有可以后退的历史记录
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**setCookie**</font>: 设置cookie

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **url** |<font color ='#808000'>**string**</font> |  | 是||如果加载该域名地址，会自动把cookie传给服务器
  **value** |<font color ='#808000'>**string**</font> |  | 是||
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 设置浏览器的cookie
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**setLoadingProgressColor**</font>: 设置顶部进度条颜色

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **color** |<font color ='#808000'>**string**</font> |  | 是||颜色值格式为：8位16进制字符，前6位是RGB颜色值，后两位是透明度（Alpha），例如：000000FF
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 设置加载html页面时，组件顶部进度条的颜色
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**setDefaultEncodingURL**</font>: 设置默认转码

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **isEncode** |<font color ='#808000'>**Boolean**</font> | true | 否|true|默认按照utf-8编码方式转码，设置为false则不对原url进行处理
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 设置是否对url默认按照utf-8编码格式转码，仅支持iOS平台
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**getContentSize**</font>: 获取加载页面内容尺寸

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

>##### <font color ='#0092db'>**loadString**</font>: 加载html字符串

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **text** |<font color ='#808000'>**string**</font> |  | 是||
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**eval**</font>: 执行JavaScript函数

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **code** |<font color ='#808000'>**string**</font> |  | 是||
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 无
- 说明: 在页面执行一段Javascript代码，并返回值
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件

>###### <font color ='#e96900'>**loaded**</font>: 加载结束事件

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回{url}，其中url表示当前操作的url地址，该地址不一定为网络地址，本地html页面跳转也会触发并返回本地路径
- 说明: 加载结束事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**start**</font>: 开始加载

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回{url}，其中url表示当前操作的url地址，该地址不一定为网络地址，本地html页面跳转也会触发并返回本地路径
- 说明: 开始加载
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**failed**</font>: 加载错误事件

- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 加载网页失败或加载一个错误的或者不存在的网页时触发，返回错误信息
- 说明: 加载错误事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


