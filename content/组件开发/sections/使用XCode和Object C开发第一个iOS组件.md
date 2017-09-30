---
title: 使用XCode和Object C开发第一个iOS组件
---
### 使用XCode和Object C开发第一个iOS组件

DeviceOne Module自定义原生组件扩展SDK（以下简称SDK），DeviceOne平台具备有灵活性和可扩展性，支持三大移动操作系统平台扩展（iOS、Android、WindowPhone）；SDK分为三类，（1）UIModule、（2）SingletonModule、（3）MultitonModule；目前我们为不同类型SDK开发了各种组件让用户很好的开发一个APP应用，具体请查看官方网站“在线帮助”，后续会提供更多组件的支持，供用户选择使用。为了满足具备有iOS原生开发能力的用户热切需求，我们提供支持原生开发者自定义扩展组件。
本文档面向所有使用该SDK的iOS开发人员、测试人员、合作伙伴以及对此感兴趣的其他用户。阅读该文档要求用户熟悉iOS应用开发。Deviceone使用脚本Core引擎进行和核心框架结合并相互调用，所有的组件都是由前端JS脚本来负责创建，调用组件对象相关属性、方法、事件，所以还希望用户具备熟悉Lua\JavaScript脚本语言，最后也是最为重要的一点，你需要能够熟练使用Deviceone官方提供的设计器。


### 1.简介

> DeviceOne推出了对Module扩展开发SDK，开发思路与原生自定义view完全一致，只需根据SDK提供组件开发框架编写自定义属性、方式、事件工作。用户可以通过开发者平台“开发->组件开发”功能模块，创建自定义扩展组件后，只需配置相关属性、方法、事件等简单操作。最后在“开发模版”项中下载扩展组件平台工程模版即可开发出属于自己的组件，轻松无缝接入DeviceOne平台，快速开发扩展组件，自行实现对DeviceOne引擎能力的增强，提高APP的质量及用户体验。

#### 1.1 创建扩展组件类型定义：

- UIModule：简称（UI）是指用户界面控件对象，它的三要素：绘制、数据、控制，Page级别作用域，是由一个Page UIContainer负责创建并绘制，每个组件可以被多实例化。

例如：Button、Label、TextField等；

- SingletonModule：简称（SM）是指一个独立、完整的功能模块，App级别作用域，它运行在整个App且只会有一个实例存在。

例如：Camera、Notification、Network等；

- MultitonModule：简称（MM）是指一个较特殊、无可视化组件，通常用于处理请求、绑定数据、进程服务等功能，App、Page级别作用域，是多实例模块。

例如：Http、ListData等；


#### 1.2.组件类型结构-开发模版：

　　DeviceOne为扩展开发不同组件类型提供框架模版有所区别，而具体实现组件的属性、方法、事件编码方式是基本一致。请看如下UML结构图：

<div align="center">![](../../images/ios/ios001.png)</div>


### 2.开发前准备

 - 开发环境
  - PC： Mac OS 10.10.8以上
  - Xcode 6.0以上
 - 开发帮助参考
DeviceOne 在线API文档：http://doc.deviceone.net/web/doc/index.htm
DeviceOne 组件源码地址：http://github.com/do-ios

### 3.建立组件

1.进入[DeviceOne注册页](http://developer.deviceone.net/login/?returnUrl=http://developer.deviceone.net/app),注册账号,如下图：
![](../../images/ios/ios002.png)

2.成功注册后登陆来到个人页面,点击如图红色箭头所示的**`开发`**按钮：
![](../../images/ios/ios003.png)

 3.点击**`组件开发`**来到下图页面：
 - 左边<font color="red">红色框体</font>部分为已经创建的组件列表
 - 点击**`创建组件`**按钮弹出创建组件弹框
(../../images/ios/ios004.png)

4.点击**`创建组件`**弹出组件创建弹框，具体说明如下图：
 <div align="center">![](../../images/ios/ios005.png)</div>
 - 输入上图所示选项内容，点击`确定`按钮后完成组件初始化创建，返回组件列表，可在组件列表中查看到`“你好UI组件”

6.点击组件，进入组件配置界面：
 - 基本配置
   - 组件id： 当前组件唯一id
   - 组件名称： 组件名称描述
   - 组件图标： 点`组件图标`按钮上传当前组件图片
   - 容器类型：该设置仅对UI控件有效
     - "不可包含其他控件"：
	 - "只能包含一个子控件"：
	 - "包含任意多子控件"：
 - 功能定义
 - 下载模板
 - 上传资源
 - 对外发布


6、在上图中，我们可以看到我们刚才添加的组件的基础信息，如ID等。我们接下来可以进一步为组件添加属性、方法和事件，点击上图左侧列表菜单中的功能定义，就可以进入如下界面：
![](../../images/ios/ios006.png)

7、我们点击添加，可以打开属性添加界面，如下图：
![](../../images/ios/ios007.png)

8、在上图中添加了名称等属性的设置之后我们可以点保存，然后完成该属性的添加（方法和事件的添加方法同属性），之后我们点击上图左侧菜单“组件开发”，可以看到如下图：
![](../../images/ios/ios008.png)

9、点击上图中的下载，我们就可以将iOS版本的组件模板工程下载到我们的MAC电脑上了。


### 4.使用SDK开发原生自定义组件：
我们刚才在上面的讲解中下载了一个组件的模板工程，下面我们打开工程，看到如下工程目录：
![](../../images/ios/ios009.png)

我们可以看到该组件模板工程目录有几个group（相当于eclipse的Folder）,其作用分别是：lib里面主要是需要用的iOS原生framework；Do_Test是我们的工程文件，打开之后如上右图，我们可以看到有两个子group：doCore和doFrame，这两个group 是我们开发用到的接口，除此，还有一个AppDelegate和ViewController，对于做过iOS原生开发的人，我想对这两个类应该不会陌生，同样，我们也是在这里启动我们的工程；doExtLib是我们组件类所在的group，里面可以建立我们自己的子group；Products就是我们的静态库也就是.a文件所在的地方了。
1、	我们在doExtLib目录下添加我们的组件类（该类文件已经在该工程的文件夹中了），如下图：
![](../../images/ios/ios010.png)

2、	添加之后如下图：
![](../../images/ios/ios011.png)

3、	本示例是以一个UI组件来讲解，因此上图展示的UI组件的类结构。UI组件通常由三种文件组成，即：_IView 、_UIModel、_UIView 三种标识结尾的类命名规范，上图中的_do_HelloWorld_是我们自己定义的组件名称。

1> _IView文件中是我们该组件的协议文件，属性方法，同步或异步方法等都在此定义；

2> _UIModel是该UI组件的model，里面包含了我们组件的实例信息，比如默认的frame(我们在设计器中通过拖拽设置的)等，稍后我们会讲到；在这里我们还要在OnInit方法中注册属性，遵照如下格式：
![](../../images/ios/ios012.png)

3> _UIView就是我们组件的view了，我们在里面实现我们的属性方法以及同步或异步方法。组件模板中自动为我们添加了一些方法，我们可以在_UIView的类实现中，看到如下三个方法。LoadView是该组件加载之后调用的方法，我们可以将一些初始化的操作放到这里，例如实例变量的初始化等；OnDispose方法通常是用来销毁实例变量或者是实例对象的；
OnRedraw 中是用来对该组件进行布局，例如子视图的位置和尺寸等。我们可以通过_model的RealX,RealY,RealWidth,RealHeight来获取默认的frame，该frame是我们在设计器中设置的。

![](../../images/ios/ios013.png)

4> 我们如果需要对属性的改变做出处理，那么我们需要实现协议方法，类似于这样的格式的方法：”Change_我们定义的属性名”，在这个方法中，实现我们的代码。

5> 以上三个方法是必须实现的，是由平台自动调用。除此，我们想要实现组件的其它操作，可以放到我们自定义的方法中去。例如我们自定义了一个方法,可以参照模板中的注释，来实现参数的获取，以及执行结束回调脚本
DeviceOne方法定义分为同步、异步两种类型:
•	同步：是指没有耗时逻辑操作，UI线程操作可能会改变组件对象属性，方法可以有返回值。
•	异步：是指既有耗时逻辑操作，建立新的线程避免UI线程阻塞，没有返回值，方法执行完毕可以通过回调函数将结果送回前端。
![](../../images/ios/ios014.png)

6>我们也可以定义事件，例如我们定义一个touch事件，那么我们可以按照下面的方式将结果通知脚本：
doInvokeResult *_invokeResult = [[doInvokeResult alloc] init];
[_invokeResult SetResultText:YES];
[self.EventCenter FireEvent:@"touch" :_invokeResult];
这样，如果我们在脚本中订阅了touch事件，那么在脚本中就可以得到回调的结果了。

7> 如果我们需要在当前组件中嵌套某些其他的ui文件，即ui模板（设计器或者脚本中添加）；我们要使用下面的方式，加载这个ui文件，并生成我们想要的view，通常我们会在两个地方做这个事情，一是在方法中，一是在属性改变的时候；首先我们看看方法中如何做，如下：
![](../../images/ios/ios015.png)

以上代码实现加载ui文件并生成一个view的过程（来自Deviceone 官方组件”do_ViewShower”的”showView”方法）。我们需要注意两点：
1、在以上第一行中参fileName是我们在设计器中设置的模板路径，即类似于”source://view/1.ui”的格式；
2、以上代码是生成了一个view，在这之后我还需要执行原生的”[self addSubview:view]”,来添加该view。注意了这两点之后，剩下就进入了我们的纯原生时间了，我们在原生中如何写代码，在这里我们也如何写就是了。
如果我们要在属性改变中加载”.ui”文件，会稍微有些区别，需要注意如下两点:
>  	- [container LoadDefalutScriptFile:fileName]这句执行前需要加一个判断条件” if      (pageModel.ScriptEngine)”，即：
>          if (pageModel.ScriptEngine){
>	  [container LoadDefalutScriptFile:fileName]；
>          }
>	  - 我们需要在_UIModel 中实现如下方法:
![](../../images/ios/ios016.png)
以上代码参考DeviceOne官方组件”do_ListView”。”loadModuleJS”是我们   在”_UIView”定义的方法，我们在loadModuleJS中需要这样做，如下：
![](../../images/ios/ios017.png)
我们用GetPropertyValue来获取headerView属性值，也就是我们在设计器中设置的类似于”source://view/headerView.ui”的”.ui”文件。

总结：
    属性加载”.ui”之所以有以上两点需要注意，原因在于：组件内嵌的”.ui”文件是要在整个组件加载完成之后才会加载，通俗的说，先加载外层的再加载内嵌的，而”.ui”中设置的属性值是在整个组件或页面加载一开始就进行了赋值，此时外层还没加载完成，因此”LoadDefalutScriptFile”现在无效，就必须实现”DidLoadView”方法，这样在外层加载完成之后，” DidLoadView”会被调用，我们在其中执行”LoadDefalutScriptFile”就可以了；而属性可能在脚本中，即”.js”中被多次赋值（js中的任何代码都是在ui加载之后执行的），因此在”Change_属性名”中我们还是要保留”LoadDefalutScriptFile”的调用。


8>如果模板为我们自动生成了这几个组件类不能满足我们的需求，那么我们可以自CustomView.h的类，然后我们可以在”showView”方法中将其实例化，然后调用CustomView的方法就可以了。

9> 如果我们想要进行调试将一些信息输出到设计器的”LogCat”中，我们可以这样做：
![](../../images/ios/ios018.png)

      1>如果我们要上传组件，那么我们需要将其编译成.a静态库文件。
  注：
           1、 在xcode中我们要将下图中高亮选项选为no
![](../../images/ios/ios019.png)
2、 我们只需要上传 xxx_UIModel.h 、xxx_UIView.h以及我们编译成功的.a文件。如果我们有一些设置信息，那么我们需要添加一个.plist文件，如果有图片以及其他资源文件，那么我们需要增加一个.bundle文件；.plist和.bundle也一同上传；如果用到了第三方的framework，则也要一并上传。

3、 如果在我们自己建立的这个组件里面用到了第三方的开源库，那么为了避免其他组件中也引用了同样的开源库，建议对开源库中的类名进行重命名，命名规则可以参考 “doHWXXXXX”的方式 ，”do”为统一前缀,”HW”为我们当前的组件的缩写，由于我们这个组件的名字为”HelloWorld”，因此我们缩写为”HW”,”XXXXX”自然就是我们原本的类名了；如果用到了类别，那么建议修改类别中的方法名，也是为了避免其他组件中引入了相同的类别而造成冲突。

4、	以上我们介绍了一个UI组件的开发过程，下面我们分别来介绍下SM和MM的开发。首先我们介绍下SM的开发：
1>	组件的建立过程和之前UI组件的建立过程是一样的，建立之后我们下载模板过程，然后打开，可以看到如下截图：
![](../../images/ios/ios020.png)
我们可以看到SM组件模板工程中也有几个group，其作用同UI组件；组件的类结构同UI组件是不同的：
1>_ISM是我们要实现的协议，里面有我们定义的方法；

2>_App是用来执行在整个应用初始启动的时候需要执行的一些方法，例如微信分享等。以官方SM组件”do_Notification”为例，我们首先可以看到如下代码：
![](../../images/ios/ios021.png)

我们必须要在 Instance 方法中声明我们的SM实例，参照以上代码，我们在自定义的SM组件中将类名替换成我们自己的类名就可以了。
接下来我们可以看到这两个方法：
![](../../images/ios/ios022.png)

从方法名来看是不是感到很熟悉？没错，这就是我们将来会在整个应用中的AppDelegate中调用的方法（注意：是我们将来把整个组件的类，也就是doExtLib下的类文件，通过官方云平台打包进去并生成一个ipa也就是我们的app；这个app的AppDelegate要执行的方法，但是我们在这里实现。）由于”do_Notification”不需要第三方应用跳转，因此返回”NO”。我们可以再看看DeviceOne官方组件”do_SinaWeiBo”，如下：
![](../../images/ios/ios023.png)

我们可以看到以上代码中调用了微博的api。还是在 _App中，我们回到顶部可以看到有一个属性：@synthesize OpenURLScheme;该属性可以用来存储第三方应用跳转需要的key,还是新浪微博这个组件，我们看“do_SinaWei_SM.m”，在方法”login”中，我们可以看到这句话：
![](../../images/ios/ios024.png)
可以看到用来存储微博分享和登陆时的key。

3>_SM中用来实现我们添加组件时定义的方法，我们在这里实现该组件的行为。


5、	MM组件，模板工程结构如下图：
![](../../images/ios/ios025.png)
可以看到”MM”类型的组件和”UI”、”SM”类型也拥有同样的group结构，当然其作用也是相同的。

1>	_IMM我们要实现的协议，里面定义了该组件要使用的属性和方法；

2>	_MM 中实现我们的组件方法，默认有如下两个方法：
![](../../images/ios/ios026.png)

![](../../images/ios/ios027.png)
        我们在”OnInit”中注册属性，注册方式如下（同UI组件）：
![](../../images/ios/ios028.png)
       可以参照DeviceOne官方组件”do_Http”。
我们在”OnDispose”中释放资源，例如我们组件定义的实例变量，例如数组、 字典或者是其他对象。

[回到顶部](#top)
