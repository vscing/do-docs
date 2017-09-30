---
title: 使用Eclipse开发第一个Android组件
---
### 使用Eclipse开发第一个Android组件

DeviceOne Module自定义原生组件扩展SDK（以下简称SDK），DeviceOne平台具备有灵活性和可扩展性，支持三大移动操作系统平台扩展（Ios、Android、Windows）；SDK分为三类，（1）`UIModule`、（2）`SingletonModule`、（3）`MultitonModule`；目前我们为不同类型SDK开发了各种组件让用户很好的开发一个APP应用，具体请查看官方网站“在线帮助”，后续会提供更多组件的支持，供用户选择使用。为了满足具备有Android原生开发能力的用户热切需求，我们提供支持原生开发者自定义扩展组件。


本文档面向所有使用该SDK的Android开发人员、测试人员、合作伙伴以及对此感兴趣的其他用户：
- 阅读该文档要求用户熟悉Android应用开发。
- Deviceone使用脚本Core引擎进行和核心框架结合并相互调用，所有的组件都是由前端JS脚本来负责创建，调用组件对象相关属性、方法、事件，所以还希望用户具备熟悉Lua\JavaScript脚本语言。
- Deviceone引擎强调传输数据的简洁和统一性，因此选择轻量级的JSON作为JS和原生框架语言之间通讯的数据载体，所以要求开发者同时要熟悉Java和Javascript中JSON格式数据的操作。



###1. 简介

>DeviceOne推出了对Module扩展开发SDK，开发思路与原生自定义VIEW完全一致，只需根据SDK提供组件开发框架编写自定义属性、方式、事件工作。用户可以通过开发者平台`组件开发`功能模块，创建自定义扩展组件后，只需配置相关属性、方法、事件等简单操作。最后在`开发模版`项中下载扩展组件平台工程模版即可开发出属于自己的组件，轻松无缝接入DeviceOne平台，快速开发扩展组件，自行实现对DeviceOne引擎能力的增强，提高APP的质量及用户体验。


<span id="jump_moduletype"></span>
 ####1.1 扩展组件类型定义

- UIModule：简称（UI）是指用户界面控件对象，它的三要素：绘制、数据、控制，Page级别作用域，是由一个Page UIContainer负责创建并绘制，每个组件可以被多实例化。

例如：Button、Label、TextField等；



- SingletonModule：简称（SM）是指一个独立、完整的功能模块，App级别作用域，它运行在整个App且只会有一个实例存在。

例如：Camera、Notification、Network等；



- MultitonModule：简称（MM）是指一个较特殊、无可视化组件，通常用于处理请求、绑定数据、进程服务等功能，App、Page级别作用域，是多实例模块。

例如：Http、ListData等；



####1.2 组件类型结构-开发模版：

　　DeviceOne为扩展开发不同组件类型提供框架模版有所区别，而具体实现组件的属性、方法、事件编码方式是基本一致。请看如下UML结构图：
<div align="center">
![](../../images/ans/ans001.png)
</div>




###2. 开发前准备

- 开发环境

PC：Windows7/8/10/Mac OS

Eclipse3.4及以上或者Android Studio

ADT21及以上

Android SDK 14（4.0）

JDK1.7

JDK下载地址：[Win64位](http://ohtf3vllq.bkt.clouddn.com/jdk-7u79-windows-x64.exe),[MAC](http://ohtf3vllq.bkt.clouddn.com/jdk-7u79-macosx-x64.dmg)

其中Android环境推荐使用Google整合版的Eclipse：SDK ADT Bundle。下载地址：
http://developer.android.com/sdk/index.html#download (需翻墙)

Android Studio 下载地址
http://www.android-studio.org/

- 开发帮助参考

Android在线API文档：http://developer.android.com/reference/packages.html (需翻墙)
Deviceone 在线API文档：http://document.deviceone.net/assets/images/html/android_doc/index.html
DeviceOne 组件开源地址：http://github.com/do-android

###3.创建组件
####3.1 进入DeviceOne官网,注册账号并登陆

####3.2 登陆成功后会首先来到管理中心界面,点击 `开发` 按钮
<div align="center">
![](../../images/ans/ans002.png)
</div>

####3.3 点击 `组件开发` 来到下图页面：
 - 左边<font color="red">红色框体</font>部分为已经创建的组件列表
![](../../images/ans/ans003.png)

####3.4 点击 `创建组件` 弹出组件创建弹框，具体说明如下图：
 <div align="center">![](../../images/ans/ans004.png)</div>

- 输入上图所示选项内容，点击 `确定` 按钮后完成组件初始化创建，返回组件列表，可在组件列表中查看到 你好UI组件

####3.5 点击组件，进入组件配置界面：
- 基本配置
  - 组件id： 当前组件唯一id
  - 组件名称： 组件名称描述
  - 组件图标： 点`组件图标`按钮上传当前组件图片
  - 容器类型：该设置仅对UI控件有效
     - "不可包含其他控件"：
	 - "只能包含一个子控件"：
	 - "包含任意多子控件"：
   - 关键词语
   - 组件描述
   - 参数配置
   - 高级参数配置
 - 功能定义：包含属性,方法,事件的定义
 - 下载模板
 - 上传资源
 - 对外发布

下面说明一下添加属性,方法，事件是如何操作的
 <div align="center">![](../../images/ans/ans005.png)</div>
 属性,方法,事件的添加方式相同,根据自己需求自己定义。

 需要注意的是方法的参数值添加,请看下图
 <div align="center">![](../../images/ans/ans006.png)</div>

点击添加按钮后弹出如下页面

  <div align="center">![](../../images/ans/ans007.png)</div>

以上便是属性,方法,事件的基本配置,如果想要修改manifest里面的某些值或者是内部文件里面自定义的某些值可详见[参数配置](http://doc.deviceone.net/web/doc/advance_course/advance_parameter.htm)


####3.6 基本配置以及功能定义之后就可以下载模板了,eclipse和Android Studio均可以使用,下载对应的模板就可以了
  <div align="center">![](../../images/ans/ans008.png)</div>

###4. 使用SDK开发原生自定义组件

 开发者可以下载自定义扩展组件开发模版来对照学习，快速入门和理解开发组件相关编码。

>提示：字符@TYPEID_前缀（即：（名称）组件ID唯一标识）；

####4.1 在eclipse下开发

下载SDK开发工程，解压后是一个标准的Android工程目录。

如图所示：
<div align="center">![](../../images/ans/ans009.png)</div>

- 打开Eclipse导入该SDK，操作步骤如下：

Eclipse ->File ->Import ->General ->Existing Project into Workspace ->Browser ->选择zip解压的目录 ->Finish即可

导入后的工程结构，如图所示：

<div align="center">![](../../images/ans/ans010.png)</div>



- 目录结构和类简述：

==***src/doext***==包是指：开发扩展组件接口定义和具体实现，开发者用户都在该包目录下进行创建包扩展、类定义及编码工作。注：请勿在该包外创建与组件相关类或接口，否则Build脚本将不会编译到组件JAR中，导致出现问题。



==***doext.define***==包下定义了用于声明绑定映射至JS组件对象属性及方法。

@TYPEID_MAbstract类为Model的抽象类，继承自引擎doCore.jar包中的DoUIModule类，并重写相关函数，其子类为具体Model实现类。 开发者用户如果已经为组件配置了相关属性，该抽象类onInit方法中将自动生成为每个属性进行注册。



@TYPEID_IMethod为接口类，主要定义了组件方法接口，开发者用户如果已经为组件配置了相关方法，该接口将自动生成相关接口方法定义。



**声明方法接口、MAbstract理由：**

开发者在自定义原生扩展组件开发过程中难免需要对现有组件方法、属性进行修改或新增。DeviceOne要求开发者在开发扩展组件整个生命周期内，需要线上组件与线下（本地开发）组件的方法、属性、事件保持同步，从而避免组件API对外开放使用出现问题，为了尽量减少对现有组件开发已经实现的编码冲突，开发者只需替换接口定义类。

例如：

如果开发者在后台对组件配置做了修改，需要重新下载开发模版，替换现有扩展组件工程src/doext.define包下接口类，然后在相应的具体实现类中只需做简单修改。



***==doext.implements==***包下是开发扩展组件的具体实现类，开发者只需对具体方法进行实现。以下根据不同组件类型说明：

==***src/dotest***==包主要为自定义扩展组件提供测试使用，开发者用户在开发组件完成后可以自行编写测试代码，于此来确保组件相关属性、方法、事件能正常使用及响应；具体测试编码请参考dotest.module.activit.WebViewSampleTestActivty类。

####4.2 在Android Studio下开发
下载SDK开发工程，然后解压,如下图所示
<div align="center">![](../../images/ans/ans011.png)</div>

打开Android Studio，点击 `Open an existing Android Studio project` 导入该工程,如图
<div align="center">![](../../images/ans/ans012.png)</div>

功能实现在 @TYPEID Module对应的目录下面,测试则在app Module对应的目录下面。

- **UI组件**

@TYPEID_View类和Android原生开发自定义一个View是相同的需要继承一个具体View并实现doCore.jar中DoUIModuleView接口和doext.define.@TYPEID_IMethod接口类；开发模版已经默认实现@TYPEID_IMethod接口。

View类请看：doext.implements.@TYPEID_View.java



- **SM、MM组件**

@TYPEID_Model类实现@TYPEID_IMethod接口，开发模版已经默认实现@TYPEID_IMethod接口。

Module类请看：doext.implements.@TYPEID_Model.java




####4.3 开发扩展组件

- 开发扩展组件共分为三种类型：UI、SM、MM，类型定义描述：请见[扩展组件类型定义](#jump_moduletype)。

- 这里不进行对每种类型组件开发模版进行阐述，开发者只要了解不同组件之间的概念及UML结构，只需要关注如何实现自定义组件行为即可，DeviceOne官方组件在GitHub上已经对外开放组件源码，开发者可以通过https://github.com/do-android 链接下载相关组件源码。

- 注：开发者用户在创建组件后需进行配置组件相关操作，如属性、方法、事件等，开发模版会动态生成相关方法接口定义及属性注册代码，给开发者减少编码工作，轻松开发，只需关注具体实现即可。

- SM，MM类型的组件获取当前上下文Context方法: DoServiceContainer.getPageViewFactory().getAppContext()。


- 注册属性：

　　目前DeviceOne对SM类型组件不支持属性配置，DeviceOne框架对扩展组件属性初始化是通过@TYPEID_MAbstract.java抽象类onInit()法进行注册，此抽象类继承至DoUIModule类，并重写父类onInit()方法，由具体子类@TYPEID_Model实现。

如下图红色框：

![](../../images/ans/ans013.png)





注册属性

@_property 属性对象；

```java

 protected void registProperty(DoProperty _property) throws Exception {



 }

```



 属性对象构造器

 @_propertyID  名称ID

 @_PropertyDataType 属性值类型（枚举值String, Bool, Number）

 @_defaultValue 默认值

 @_designOnly 是否允许动态设置，如果为true只有在设计设置有效（true、false）；

```java

 public DoProperty(String _propertyID, PropertyDataType

			_propertyDataType, String _defaultValue, boolean _designOnly) {

		this.id = _propertyID;

		this.value = "";

		this.dataType = PropertyDataType.String;

		this.defaultValue = _defaultValue;

		this.designOnly = _designOnly;

 	}

```



- 获取属性值：

　　UI类型组件@TYPEID_View实现DoUIModuleView接口类并实现（onPropertiesChanging、onPropertiesChanged）两个方法（如果是MM类型组件需重写父类这两个方法），获取属性值是通过方法传递_changedValues <K，V>集合参数来获取相应属性值。

如下图：

![](../../images/ans/ans014.png)



例如：注册一个属性为String类型“text”，现在要获取前端JS赋的初始值或者动态的修改text值，就可以通过编码：**String val = _changedValues.get(“text”);**



- 方法定义：

**描述**

DeviceOne为方法定义分为同步、异步两种类型。

同步：是指没有耗时逻辑操作，UI线程操作可能会改变组件对象属性，方法可以有返回值。



异步：是指既有耗时逻辑操作，建立新的线程避免UI线程阻塞，没有返回值，方法执行完毕可以通过回调函数。



**声明**

扩展组件所有配置的方法都定义在@TYPEID_IMethod.java接口类中，如前面所述：开发者可以通过开发者平台“开发组件”对组件进行配置方法，组件开发模版会自动完成接口方法定义，开发者只需在具体实现类中对方法进行实现。

例如在@TYPEID_IMethod接口定义组件方法，如下图：

![](../../images/ans/ans015.png)





**实现**

UI类型组件@TYPEID_View实现DoUIModuleView接口类并实现（invokeSyncMethod、invokeAsyncMethod）两个方法（如果是MM、SM类型组件需重写父类这两个方法），并实现@TYPEID_IMethod.java接口类中所有组件方法。



在invokeSyncMethod、invokeAsyncMethod方法体通过“_methodName”来判断方法调用对应接口实现方法，如下图：

![](../../images/ans/ans016.png)

![](../../images/ans/ans017.png)



- 异步回调函数：

如何执行异步内完成方法回调？可以通过如下方法：

_scriptEngine.callback(_callbackFuncName, _invokeResult);

**参数**

@_callbackFuncName回调函数名；

@_invokeResult传递回调参数对象；

获取DoInvokeResult对象方式new DoInvokeResult()，可以为回调参数设置多中不同类型。

具体如下图：

![](../../images/ans/ans018.png)



一个完整回调示例代码：

```java

DoInvokeResult _invokeResult = new DoInvokeResult(getUniqueKey());

DoJsonNode _node = new DoJsonNode();

_node.setOneInteger("index", 1);

_invokeResult.setResultNode(_node);

_scriptEngine.callback(_callbackFuncName, _invokeResult);

前端JS函数通过data.index的方式获取值。

```



- Fire事件：

DeviceOne 提供了事件消息机制，通过触发事件的方式来响应前端JS事件回调函数，开发者可以根据Android 原生事件或自定义事件，通过开发者平台组件“配置->事件”来创建相应事件名。所有组件事件绑定都是由前端JS脚本on进行注册，原生代码只需要Fire相应事件即可，并由deviceone引擎负责调用事件回调函数；

**示例**

--前端JS为Button组件绑定（注册）一个“touch”点击事件；

```java

button.on("touch",function(err,data){

	--回调执行，处理点击事件逻辑

});

```

```java

/*原生Button组件触发一个点击事件*/

@Override

public void onClick(View v) {

	DoInvokeResult _invokeResult = new DoInvokeResult();

	this.model.getEventCenter().fireEvent("touch", _invokeResult);

}

```



###5. 资源配置

>扩展组件资源R引用管理

DeviceOne引擎及Android原生扩展组件中均**==不允许出现R文件的引用==**， R资源ID由DeviceOne框架引擎负责管理，开发者可以通过doCore DoResourcesHelper类API提供了相应方法来获取R资源ID。



- Res资源文件

SDK开发工程目录下凡是以“deviceone_”前缀打头命名的资源文件，开发者不要随意改动，保持其原状，否则SDK可能在启动过程中报找不到引擎资源的警告而强制退出，开发者如需新增资源，请自行建立资源目录或XML文件。



- AndroidManifest配置

Deviceone SDK 对AndroidManifest配置文件增加了两种命名空间名称“**==deviceone==**” 和“**==android==**” 如下：

```xml
<manifest xmlns:deviceone="http://schemas.android.com/apk/res/android"
xmlns:android=http://schemas.android.com/apk/res/android
```

文档所有元素属性都以“**==deviceone==**”命名空间开头即表示为SDK原状，开发者不要进行随意改动，否则自动打包可能会出现编译无法通过。

**注：**

开发者如需要在AndroidManifest文件中增加新Activity、Service、权限等配置项，请使用“**==android==**”命名空间开头，这和正常开发Android配置一样，如下。

![](../../images/ans/ans019.png)

- eclipse 下打包上传 执行Ant Build

开发者当组件开发完成并通过**==*doext.test*==**测试后，运行工程根目录下**do_buil.xml** Ant构建脚本，Build成功后会在当前根目录下生成一个@TYPEID.ZIP包，开发者需将该ZIP包上传到组件资源库中。

- Android Studio 下打包上传 请点击[这里](http://doc.deviceone.net/web/doc/advance_course/source_android.htm)


[回到顶部](#top)
