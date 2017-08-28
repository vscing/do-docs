---
title: do_IconFont 组件
---

### do_IconFont 组件

 支持平台: iOSiOS 7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_IconFont)
 支持从http://www.iconfont.cn/plus网站下载的ttf格式图标

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#42b983'>属性</font>  |[iconColor](#iconColor)| 字体颜色
<font color ='#42b983'>属性</font>  |[iconSize](#iconSize)| 字体大小
<font color ='#42b983'>属性</font>  |[iconName](#iconName)| 字体名称
<font color ='#42b983'>属性</font>  |[iconCode](#iconCode)| 字库对应图标代码
<font color ='#e96900'>事件</font>  |[touch](#touch)| 点击触发

#### <font color ='#40A977'>**1.**</font> 属性

>###### <span id=iconColor><font color ='#42b983'>**iconColor**</font></span>: 字体颜色

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 000000FF
- 说明 : 获取或设置控件前景色，为8位16进制整数，前6位为rgb颜色值，后两位为透明度

>###### <span id=iconSize><font color ='#42b983'>**iconSize**</font></span>: 字体大小

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 17
- 说明 : 

>###### <span id=iconName><font color ='#42b983'>**iconName**</font></span>: 字体名称

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 : 创建UIFont使用的是字体名，解压缩下载的字库包，双击打开“iconfont.ttf”，取字体名称项即可（Android平台取得是.ttf文件名，所以在DO平台上传的.ttf文件需要保持跟iconfont.ttf文件中字体名称同名）

>###### <span id=iconCode><font color ='#42b983'>**iconCode**</font></span>: 字库对应图标代码

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : 
- 说明 : 解压缩下载的字库包，打开“demo_unicode.html”查找该字体名称下每个图标所对应的HTML实体Unicode码，一般为8位的Unicode字符，比如：“关闭”对应的HTML实体Unicode码为：&#xe640，只需传递后四位字符即可

#### <font color ='#40A977'>**2.**</font> 同步方法

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=touch><font color ='#e96900'>**touch**</font></span>: 点击触发

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 
- 说明: 点击触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


