---
title: Hello World
---

### Hello World介绍

程序员学习新技术都是通过Hello World开始的，我们也不例外。这里我们简单了解利用do平台开发App的基本流程：

* [开发环境搭建](#开发环境搭建)
* [开发者账号](#开发者账号)
* [新建项目](#新建项目)
* [拖拽一个组件](#拖拽一个组件)
* [修改js代码](#修改js代码)
* [手机调试效果](#手机调试效果)
* [发布App](#发布App)

视频教程[请点击](http://video.deviceone.net/)观看

<a name="开发环境搭建">1. 开发环境搭建</a>

do平台的开发的基本开发工作都是围绕**DeviceOne**提供的IDE（`DeviceOne Studio`），我们通常简称为<mark>**设计器**</mark>。

设计器是基于`Eclipse`核心的RCP,熟悉Eclipse的的开发人员应该很熟悉基本的操作。设计器是跨平台的，可以在Windows，Mac下运行。

下载页面是[这里](http://doc.deviceone.net/web/doc/env/ide.htm)

>**注：设计器启动的问题基可以参考[IDE的安装和使用](../../../应用开发/sections/IDE的安装和使用)**

<a name="开发者账号">2. 开发者账号</a>

DeviceOne开发平台，一些相关配置、生成APP离线包，需要开发者账号，目前开发者账号赞不开放。

do平台提供的开发者服务有一些服务项目需要在线，创建一个开发者账号是必须要的。注册没什么特殊，简单略过。
没有账号也可以进行基本的编程调试。


<a name="新建项目">3. 新建项目</a>

下载设计器后，启动的界面类似常规的Eclipse界面，do平台基本的开发工作都是围绕着设计器，基本上所有的工作步骤都在设计器上操作：

首先需要新建一个项目，点击`File`-`New`-`DeviceOne Project`或者直接在`Script Explorer`窗口的右键`New`-`DeviceOne Project`：

![](../../images/h001.png)

新建项目需要联网，输入用户密码验证码后登陆。但是创建完之后是支持离线开发和调试的。

![](../../images/h002.png)

<a name="拖拽一个组件">4. 拖拽一个组件</a>
新建完成后，会自动生成一些文件。
双击打开`index.ui`，我们可以看到一个可视化的设计区域和右边的UI备选区，我们从右边找到`do_Label`拖拽到设计区
接着选中这个组件，然后在`Properties`窗口把它的`bgColor`改成00FF00FF（前6位表示颜色，后2位表示透明值),我们可以马上看到Label的背景变成了绿色效果
![](../../images/h003.png)


<a name="修改js代码">5. 修改js代码</a>
我们再来双击打开`index.ui.js`，我们可以看到`JavaScript`的编辑器，修改一行代码，把`Hello World`改成`Hello DeviceOne`。在js文件里可以修改应用运行的逻辑。表示点击这个按钮，alert出一个信息

![](../../images/h004.png)

<a name="手机调试效果">6. 手机调试效果</a>
我们最后来手机上看看运行的效果。
**首先**我们需要安装一个调试用的App，打开[这里](http://doc.deviceone.net/web/doc/env/debug_app.htm)扫描里面二维码安装一个`doDebugger`的App，Android，iOS手机都可以，windows和winphone版本不支持二维码扫描安装，这一课暂时不提。安装完如下图。这里提一下，这个调试App是可以定制的，也就是开发者可以选择更多组件打包一个新的doDebugger，这里暂时不详细解释。

![](../../images/h005.png)

**然后**我们回到设计器中的`Service`右键点击`Create`按钮，如果弹出一个选择窗口，请选择刚创建好的test项目。创建后，记录下显示的ip地址和port号。请确保`state`是`Running`

![](../../images/h006.png)
![](../../images/h007.png)

**继续**我们回到手机，打开`doDebugger`这个app，在服务地址处输入刚才我们记录下的地址和端口。请确保手机和电脑在同一网段。然后点击`更新`,把代码从电脑上同步到手机上。如果更新提示失败，请参考[这里](http://bbs.deviceone.net/forum.php?mod=viewthread&tid=479&extra=page%3D1).

![](../../images/h008.png)

我们点击`进入`，就可以看到我们在设计器上设计的效果，点击按钮，会弹出`Hello DeviceOne`
![](../../images/h009.png)

是不是觉得很简单了。就这样，我们在设计器上可以继续修改代码，修改UI，重启App，然后再次点击`更新`按钮和`进入`按钮就可以实时的看到开发的效果。一直到这个App完成所有你需要达到的功能。

<a name="发布App">7. 发布App</a>

最后需要打包一个最终发布版本的App给测试人员测试或发布到组件商店供最终用户下载。通过点击菜单里的"Build Release Build"按钮就可以生成安装包：

![](../../images/h010.png)

下载到开发者自己的电脑，然后上传到自己的服务器和组件商店。**Do**开发的App在开发完毕后和平台就没有任何关系，我们也绝不会在App里埋点收集用户的信息。
[回到顶部](#top)