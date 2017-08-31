---
title: JS使用
---
### JS使用


**DeviceOne**平台通常的逻辑代码都是在ui文件对应的ui.js里编写，ui.js是随ui文件自动生成的。我们通常也需要自定义一些js模块，封装一些javascript代码作为函数可以被重复调用。
我们通过一个demo来说明这个问题。

### 创建js文件
在`source`下的`script`下创建一个自己的js文件，可以创建子目录，但是<mark>**极力推荐只放在**</mark>`source/script`这个根目录下

>放在别的目录下也可以，包括放在data:// 下，但是如果要加密，只会加密这个source/script下的js文件，所以推荐只放在source/script下

 ![](../../images/js001.png)
在这个demo里定义了2个js文件，一个是`souce://script/util.js` 和`source://script/ui/util.js`

### 定义和声明函数
在这个js文件里正常定义js的函数，然后利用`module.exports`声明这个函数可以被外部使用
>注意：在自定义的js文件里使用deviceone的函数和API，需要先额外加载一下deviceone的库，参考示例第一句

```javascript
var d1 = require("deviceone");//需要加载deviceone的核心js库
//声明
module.exports.encode = base64encode;
module.exports.decode = base64decode;

.....

function base64encode(str) { //通过JavaScript实现base64编码
   ......
    return out;  
}

var alg = d1.sm("do_Algorithm");
function base64decode(str) {//通过deviceone的do_Algorithm组件来实现base64的解码
        return alg.base64Sync("decode",str);
}
```

这个例子里我们定义了三个函数
1. base64的编码的`encode`函数。定义在`source/script/util.js`。
2. base64的解码的`decode`函数。定义在`source/script/util.js`。
3. 定义返回按钮closepage的功能的init函数。定义在`source/script/ui/util.js`

### 使用函数
使用这个函数，需要先调用`require`方法加载你自己定义的js模块，require里的参数就是你定义的js名字，注意<mark>**不需要加扩展名**</mark>

```javascript
var nf = sm("do_Notification");
var util = require("util");//加载source/script/util.js模块
//也可以写成require("source://script/util");不要后缀
var ui_util = require("ui/util");//加载source/script/ui/util.js模块
//也可以写成require("source://script/ui/util");不要后缀
//返回按钮
ui_util.init("close");

//
.....
encodeButton.on("touch", function() {
        var src = srcTextBox.text;
        var dest = util.encode(src);
        destTextBox.text = dest;
})

decodeButton.on("touch", function() {
        var src = destTextBox.text;
        var dest = util.decode(src);
        srcTextBox.text = dest;
})
```
这个demo点击 `Base64编码`按钮把用户输入的字符串转成base64字符串，点击`Base64解码`再把base64字符串返回原字符串

 ![](../../images/js002.png)

这个demo详细参考[这里](http://doc.deviceone.net/web/doc/code4do/custom_js_demo.htm)

###### 注意：我们如果通过do_Webview组件加载html和js文件的话，规则和常规的web方式一样，通过`<script>`标签,这里就不介绍了。

[回到顶部](#top)
