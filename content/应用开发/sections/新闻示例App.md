---
title: 新闻示例App
---
### 新闻示例App

* [搭建主框架](#搭建主框架)
* [完善主框架](#完善主框架)
* [完成反馈页面](#完成反馈页面)
* [完成新闻页面](#完成新闻页面)
* [完成通讯页面](#完成通讯页面)
* [完成发现面](#完成发现页面)
* [应用收官](#应用收官)

### <a name="搭建主框架">搭建主框架</a>
通过[Hollow World](../../../起步/sections/Hello World)的学习，你已经掌握了如何通过debug调试器来跟PC上的设计器联调来实时查看UI设计效果、调试代码了，接下来通过一系列的demo开发教学你将很快上手学习到如何开发一个真正的App。

* 1.[导入项目](#导入项目)
* 2.[搭建框架](#搭建框架)
* 3.[页面交互](#页面交互)

视频教程[请点击](http://v.youku.com/v_show/id_XMTU2ODU4MTQxNg==.html)观看

将要学习的demo效果图如下所示
 ![](../../images/djz001.png)

<a name="导入项目">1. 如何导入完整项目</a>

本节示例demo请参考[下载地址](/web/zip/20160714/87fb237ab2ad4fffb85acf4c46ed4165.zip)，可以导入到设计器中学习。

导入教程：
下载到本地后，解压到某个目录中
 ![](../../images/djz002.png)
在设计器中选择`File`-`Import`-`DeviceOne`-`Existing projects into Workspace`点击`Next`选择刚刚解压后的目录，再次点击`Next`即可将完整的demo导入设计器中。

要开发App，最重要的就是确定主框架，好的主框架能起到减少工作量、简化代码的作用，而页面通常需要产品人员的UE设计和美工人员的UI设计，如下图所示，这两个步骤完成后才开始实现功能，由于篇幅限制，本教程不再赘述如何设计UI和UE，直接通过开发一个仿微信主页面的页面来做示范。

<a name="搭建框架">2. 开始搭建框架</a>
在起步教程[Hello world](../../../起步/sections/Hello World)中大家已经学会了如何创建项目，这里直接使用该项目。

首先在IDE中展开项目层级结构
 ![](../../images/djz003.png)
`app.js`是整个项目的入口脚本环境，双击该文件在右侧进入编辑。需要注意的是`app.js`较为特殊，如果要在该文件内使用DeviceOne的组件，需要先require("DeviceOne")，如第一句代码所示，而其他.js脚本环境是不需要引用可以直接使用的。在这个脚本环境中我们要做的操作是打开一个新页面，需要调用的是App组件的openPage方法，openPage总共有八个参数，这里先简单介绍用到的其中三个，其他参数的用法详见[App的openPage](http://store.deviceone.net/documents/do_App/1.3.html#openPage)。这里整段代码含义就是先定义一个sm类[组件分类介绍](../../../应用开发/sections/组件概述)的App，在App的loaded事件中打开一个新页。loaded事件会App启动完成时触发，所以我们把打开新页的打开写在这里面。其中openPage方法的source参数表示的是需要打开的页面的地址（绝对路径）；statusBarState参数表示的是顶部状态栏显示状态，这里选择的是transparent，这样设置能让打开的index.ui页在手机上显示的为全屏效果，即隐藏手机的顶部状态栏；animationType参数表示的是打开页面时的过渡动画类型，这里选择fade淡入淡出的方式，这样就能以淡入淡出的过渡动画全屏打开到index.ui页面了。

接着我们双击打开index.ui，进入ui视图的编辑。
 ![](../../images/djz004.png)
所有的页面展示都是通过在.ui文件中罗列组件来实现，如上图绿框所示；若需要添加ui组件，只需在组件列表Components（红框所示）中拖拽组件到ui画布上，黄框OutLine中展示的是当前页面的层级关系，在OutLine中越靠下面的组件会展示在页面越上层。

再简单分析一下主界面，整个项目的尺寸是iphone6的尺寸750x1334，分上下两个部分，底部是一个Bottom Bar导航栏，上面是随着底部导航切换的界面
 ![](../../images/djz005.png)
>页面布局示意图

这节主要介绍如何实现Botton Bar。

首先打开OutLine，
 ![](../../images/djz006.png)
在RootView中只允许有一个容器类组件，其他组件都是放在这个容器类组件中的，通常我们选择ALayout绝对布局组件来当这个容器组件。我们点击选中该组件（如上图红框所示），通过属性列表修改该组件的id为do_ALayout_root，默认大小是跟整个项目的大小相同的750x1334，再继续像该容器内添加四个ALayout，id分别修改成do_ALayout_top、do_ALayout_body、do_ALayout_line和do_ALayout_bottom，它们的id对应了它们的功能分别如页面布局示意图中所示的top、body、line和bottom。分别调整着四个ALayout的x、y、width、height属性，以调整它们在页面中的位置。再继续向do_ALayout_bottom容器中添加四个ALayout，id分别改为do_ALayout_b0/b1/b2/b3，
 ![](../../images/djz007.png)
再分别向这四个ALayout中添加一个Label和ImageView组件，并调整它们的x、y、width、height以达到下图所示效果
 ![](../../images/djz008.png)
此时你的项目中ImageView没有显示出图片，需要在source://image或者创建其他想要存放图片的目录将想要展示的图片放进去
 ![](../../images/djz009.png)
再分别选中四个ImageView组件，修改它们的source属性指向存放图片的绝对路径，就能显示图片了。
这里需要注意的是，`DeviceOne`有强大的[屏幕适配技术](../../../应用开发/sections/屏幕适配)，但可能会在某些局部对图片显示形状要求严格的地方会稍微有些变形，为了保证点ALayout有一个特殊属性isStretch，这里将该属性设置成false来保证ImageView不变形。

<a name="导入项目">3. 页面交互</a>
有了页面效果，接下来就需要使页面动起来。双击index.ui.js进入代码编辑页，
 ![](../../images/djz010.png)
先通过组件类型定义三个`sm组件`Notification、Global和Page，在需要的地方可以通过自定义对象名+.的方式来使用该组件的属性、方法和事件。再将所需要用到的ALayout、ImageView、Label定义一下，`ui组件`的定义方式跟sm组件类似，不同的是ui("")括号里填的是刚刚在.ui页面修改的对应组件的id名。

ImageView和ALayout都有点击事件（touch），为了让用户有更好的体验，我们加大点击响应范围，将touch事件订阅在Bottom的四个ALayout中，并在该事件中通过改变其他ALayout里Label的文字颜色和ImageView图片source来达到点击选中的效果。
 ![](../../images/djz011.png)

另外我们想让这个demo在android设备上能通过点击手机上的“返回”虚拟按键来返回到debug首页，需要用到刚刚我们定义过的Notification、Global和Page组件，还有一个`mm组件`Timer定时器，`mm组件`的定义方式跟`sm组件`相同，只需要组件类型即可定义。
点击android手机上的“返回”虚拟按键会触发Page组件的back事件，所以我们订阅back事件并在back事件里处理返回还是退出。
 ![](../../images/djz012.png)

到这里，一个能响应点击事件并切换图片的demo就完成了，是不是很简单易学呢？！我们可以从上一节教程中所学的手机和电脑联调代码的方法来赶快验证一下所学内容啦。


### <a name="完善主框架">完善主框架</a>

* [导入项目](#导入项目-完善)
* [完善主框架](#完善主框架-完善)
* [完成viewShower子视图](#完成viewShower子视图)
* [打开新页](#打开新页)
* [启动动画](#启动动画)

视频教程[请点击](http://v.youku.com/v_show/id_XMTU2ODYwMDQ0MA==.html)观看

将要学习的demo效果图如下所示
 ![](../../images/wsz001.gif)

<a name="导入项目-完善">1. 导入完整项目</a>

本节示例demo请参考[下载地址](/web/zip/20160714/97e790314e2944d6b40ad710dd0fadcb.zip)，可以导入到设计器中学习。

<a name="完善主框架-完善">2. 完善主框架</a>
在上一节教程[搭建主框架](#搭建主框架)中大家已经学会了如何主框架，本节教程使用上一节未完成的demo。

我们分析一下demo机构，通过点击Bottom Bar上的不同按钮来切换内容，这种情况下最适合用ViewShower这个组件，ViewShower是一个包含多个子VIew的UI容器组件。我们从组件列表里拖一个ViewShower到UI设计页面中，并通过调整x/y/width/height为0,0,750,1109将其固定在body的位置，把组件ID改为do_ViewShower_main。

双击index.ui.js打开代码编辑页面，先通过ID实例化ViewShower组件，再给ViewShower绑定数据，在`DeviceOne`的组件库中，ViewShower、ListView等这种容器类都是采用MVVM形式来绑定数据的，使得开发人员可以将View和业务逻辑分离出来。

这里先给ViewShower定义需要绑定的数据viewShower_data，其中id需要保持唯一，否则后id已经存在，会覆盖之前的View；path为需要展示的子View所在的UI页面的绝对路径，此时path所指的三个页面还不存在，一会来创建。定义好数据后，通过ViewShower的addViews方法将数据绑定进去，在调showView方法使其先默认显示第一个页面，即id为"news"的子页面。
 ![](../../images/wsz002.png)

想要完成每点击一个按钮就切换显示的子View，还需要在每个按钮的点击事件里加上切换子View的方法showView，并通过show不同id的子View来切换页面。
 ![](../../images/wsz003.png)

<a name="完成viewShower子视图">3. 完成viewShower子视图</a>
接下来我们来完成需要展示的子View视图。
 ![](../../images/wsz004.png)
在`view`目录上点击右键，选择`New`-`Folder`，填写要创建的目录名称为"news"，新建后再在`news`目录上点击右键，选择`New`-`UI File`新建名称为main的UI界面，在创建页面的同时IDE会同时创建一个跟main.ui关联的代码文件main.ui.js，双击打开main.ui文件，向页面的最外层ALayout中再拖进一个ALayout组件作为viewShower子View的最外层容器，修改它的id为do_ALayout_main，调整高度为1109，因为在主页面index.ui中viewShower的高度也为1109，**如果子View的宽高超过它父容器viewShower的宽高会导致内容显示不全的问题**，
 ![](../../images/wsz005.png)
再向该页面的do_ALayout_main中拖拽一个Label，修改Label的text为“新闻”。这样viewShower的一个子View就完成了，其他两个子View也是相同内容，所以只需负责该页面即可，在`news`目录上点击右键，选择`Copy`,再点击`View`目录选择`Paste`，填写目录名为“find”，打开main.ui修改Label的text为“搜索”即可，同样的再复制、粘贴一次，修改目录名为“contact”、Label的text为“通讯录”，这样viewShower的三个子View就完成了。（再多复制一份，目录名改成“feedback”，Label的text为“反馈”，为后续做准备）

<a name="打开新页">4. 打开新页</a>
在Bottom Bar中，我们想通过点击第四个按钮“反馈”来另外打开一个新页面，让用户填写反馈信息。先双击打开`feedback`目录中的main.ui文件，在do_ALayout_main中继续添加一个ALayout作为该页面的top，ID改为do_ALayout_1，调整宽高分别为750/128；再向do_ALayout_1中添加一个ALayout用于点击，ID改为do_ALayout_back，调整位置、宽高分别为x=4，y=6，width=147，height=110；再向do_ALayout_back中添加一个Label用于展示文字，ID改为do_Label_3，将Label的text改为“返回”。
 ![](../../images/wsz006.png)
打开main.ui.js，订阅do_ALayout_back的点击事件用于关闭该页面。同时处理在点击android设备的虚拟返回按钮时也关闭该页面。
 ![](../../images/wsz007.png)

回到index.ui.js，在do_ALayout_b3的touch事件中调用app的openPage方法，将目标地址指向刚刚调整过的/feedback/main.ui页面，将顶部状态栏显示状态改为透明（控制statusBarState参数为“transparent”）以全屏形式打开新页，同时将打开页面的动画类型（animationType）改成从右往左推出（push_r2l）。
 ![](../../images/wsz008.png)

<a name="启动动画">5. 启动动画</a>
为了让app有更生动的效果，我们让demo一进入的时候有一个动画效果作为欢迎页面，在source://view下创建一个跟index.ui平级的start.ui页面，在根ALayout里添加一个与根ALayout一样大小的ImageView，将ID改为do_ImageView_content,给这个ImageView一个source显示图片；再添加一个Label组件，修改ID为do_Label_welcome，修改do_Label_welcome的fontColor/fontSize属性调整显示字体的颜色和大小，页面就完成了。再双击打开start.ui.js页面，
 ![](../../images/wsz009.png)

先实例化当前页面的UI组件，并定义需要使用到的相关组件，在定义一个`MM组件`animation用于调用UI组件的动画，这个动画是控制ImageView组件的，所以ID定义为img_anima，通过修改img_anima的属性，我们可以操控这个动画的走向，这里想让ImageView的动画是缩放，所以选择scale方法，通过给scale方法的不同参数以不同的参数值来制作这个动画，比如delay设置成0既是让动画立即开始，duration设置成2000是让整个动画时间为2秒等等..
 ![](../../images/wsz010.png)

接下来也是同样的方法给Label定义一个旋转的动画，最后通过调用所有UI组件都通用的animate方法我们将定义的这些动画加在UI组件上并在动画完成后打开新页main.ui。
 ![](../../images/wsz011.png)

到此，本节教程就结束了，赶快拿起手机打开调试来查看效果吧！

### <a name="完成反馈页面">完成反馈页面</a>

上一节中我们学会了如何通过点击不同按钮切换页面，这节专注于完成反馈页面的功能以及细节动画。

* [导入项目](#导入项目-完成)
* [添加新组件](#添加新组件-完成)
* [同步新组件](#同步新组件-完成)
* [完成页面布局](#完成页面布局-完成)
* [输入时加动画效果](#输入时加动画效果)
* [弹出日期选择](#弹出日期选择)
* [直接引用UI页面](#直接引用UI页面)
* [自定义函数的使用](#自定义函数的使用)

视频教程[请点击](http://v.youku.com/v_show/id_XMTU2ODY0MTQxNg==.html)观看

将要学习的demo效果图如下所示
 ![](../../images/wcfk001.png)

<a name="导入项目-完成">1. 导入完整项目</a>

本节示例demo请参考[下载地址](/web/zip/20160714/a9665fe0327645dfa7f3fecb4b1787ed.zip)，可以导入到设计器中学习。

<a name="添加新组件-完成">2. 添加新组件</a>
本节中将要用到两个新组件，do_DateTimePicker和do_Picker组件，这两个组件是在创建应用时没有的，需要从组件商店中添加。在第一节[文件管理](../../../起步/sections/Hello World)教程中，我们通过设计器新建的项目，会在[开发者中心](http://developer.deviceone.net/)-[应用开发](http://developer.deviceone.net/app/index)创建一个相应的应用，如图所示 ![](../../images/wcfk002.png)
我们点击`应用配置`按钮，进入应用配置页，选择“组件配置”，如下图所示 ![](../../images/wcfk003.png)
蓝框中的内容是当前应用可使用的组件列表，每个组件都有不同版本，每个版本对应着更新了不同内容，用户在使用时选择自己想用的版本即可；点击绿框中的“添加组件”按钮，然后选择“商店组件”，找到do_Picker和do_DataTimePicker组件，点击后面的“+”号进行添加组件操作，此时再返回“组件列表”中就可以看到刚刚我们新添加的两个组件了。
 ![](../../images/wcfk004.png)

<a name="同步新组件-完成">3. 同步新组件</a>
想要在设计器中使用刚刚添加的两个组件，只需要在WorkSpace中选中该应用，再点击一下同步按钮即可。这样我们从商店选择的新组件就可以在设计器中使用了。
 ![](../../images/wcfk005.png)

<a name="完成页面布局-完成">3. 完成页面布局</a>
分析一下页面布局，这里我们使用一个线性布局LinearLayout(红框)去包裹四个绝对布局ALayout（蓝框）这四个ALayout的ID从上到下分别设置为do_ALayout_3、do_ALayout_createTime、do_ALayout_type和do_ALayout_7，因为线性布局所有内部子控件都从上向下罗列，保证组件直接紧密排列，每个ALayout中又去分别包裹Label标签组件、TextBox、TextField等用于显示和输入的组件，最底下都有一个height为1，bgColor为灰色的ALayout作为一条分割线。
 ![](../../images/wcfk006.png)

<a name="输入时加动画效果">4. 输入时加动画效果</a>
在ID为do_ALayout_3的ALayout中，添加一个Label组件（修改ID为do_Label_title）和一个单行文本TextField（修改ID为do_TextField_title），通过给Label设置text属性为“标题”来展示我们想要显示的文字；修改TextField的hint属性为“标题”能让该组件在text属性为空时显示提示信息。
 ![](../../images/wcfk007.png)
我们想让输入文字时有显示“标题”的Label组件有一个向上的动画效果，直接订阅TextField的textChanged事件，这个事件会在text改变时触发，在事件的回调中调用所有UI都有的基类方法show，通过给show方法设置动画类型和动画时间参数，来达到Label的动画效果，需要说明的是，在使用show方法前要保证UI组件的visible是为false的才会有动画效果。同样的效果我们也给放“内容”的Label加上。
 ![](../../images/wcfk008.png)

<a name="弹出日期选择">5. 弹出日期选择</a>
我们想要在点击“反馈时间”的do_ALayout（ID为）时弹出do_DateTimePicker选择日期，只需要订阅do_ALayout_createTime的touch点击事件，在触发事件的回调中调用do_DateTimePicker的show方法来显示一个日期选择器。
 ![](../../images/wcfk009.png)
因为do_DateTimePicker是SM类型的，这里直接通过类型来对组件进行实例化。
 ![](../../images/wcfk010.png)

<a name="直接引用UI页面">6. 直接引用UI页面</a>
要实现文章顶部的效果图第三张所示效果，我们首先要单独添加一个UI页面，只放一个Picker组件，并将页面的其他地方设置为灰色透明效果。
 ![](../../images/wcfk011.png)
想要在点击“反馈类型”时该页面直接弹出，只需先添加该页面到main.ui页面中，并按id实例化该页面，
 ![](../../images/wcfk012.png)
再订阅do_ALayout_type的touch事件，在事件触发的回调中调用所有UI组件都有的积累方法show来显示组件本身即可完成在一个页面中直接引用另外一个UI页面。
 ![](../../images/wcfk013.png)

<a name="自定义函数的使用">7. 自定义函数的使用</a>
页面画完后，我们要做的就是把用户填写的数据提交到后台。在提交数据之前，我们要处理一下用户提交的数据，使用的是自定义函数，必须在source://script目录下新建一个tool.js文件，在该脚本环境中定义自定义函数，并声明这个函数使其能被外部应用，
 ![](../../images/wcfk014.png)
在main.ui.js中require引用一下该方法，就可以在main.ui.js中使用该自定义函数了。
 ![](../../images/wcfk015.png)
更加详细的关于自定义函数的使用，详见[JS使用](../../../应用开发/sections/JS使用)

然后我们使用http的upload方式将用户填写和选择的数据提交到后台处理，整个反馈意见的功能就完成了。
 ![](../../images/wcfk016.png)

### <a name="完成新闻页面">完成新闻页面</a>

本节教程将介绍如何用DeviceOne简单而高效的完成一个新闻页面。

* [导入项目](#导入项目-完新)
* [数据模板分离MVVM模型](#数据模板分离)
* [自定义事件](#自定义事件)
* [展示新闻](#展示新闻)
* [九宫格展示](#九宫格展示)

视频教程[请点击](http://v.youku.com/v_show/id_XMTU2ODY5MzUxMg==.html)观看

将要学习的demo效果图如下所示
 ![](../../images/wcxw001.png)

<a name="导入项目">1. 导入完整项目</a>

本节示例demo请参考[下载地址](/web/zip/20160714/762201024984461087822df0e7769b7f.zip)，可以导入到设计器中学习。

为了方便大家理解页面结构，请参考下图
 ![](../../images/wcxw002.png)
图中红框所示的上面部分是SegmentView组件，和下面的BottomBar共同组成页面公共部分，而蓝框中是一个SlideView组件，可以左右滑动切换页面且跟SegmentView联动，页面个数则是取决于数据条数，如数据有四条就有四个页面；绿框所示是ListView组件，在本教程中是SlideView的模板，而ListView又可以绑定不同模板来展现不同页面；而黄框所示是跟上节教程中相同的直接引用一个UI页面。总而言之，这里的页面层级关系是SlideView的模板中嵌套了一个ListView，而ListView的模板又是其他不同页面。
 ![](../../images/wcxw003.png)

<a name="数据模板分离">2. 数据模板分离</a>
`DeviceOne`的数据绑定是采用了MVVM模式的，实现了页面和数据分离，数据通过绑定在不同模板上控制了页面的显示。`DeviceOne`提供了两个数据绑定组件，都是MM类型组件，一个是ListData，它本质上是一个可变数组（支持JSON array），可以增删改查数据；另外一个是HashData，它本质上是一个可变key-value键值对，也可以增删改查。
这里我们给SegmentView定义一个数据源jsonTabs，
 ![](../../images/wcxw004.png)
再把这个数据源赋值给数据绑定组件ListData，定义SegmentView的数据模型module。
 ![](../../images/wcxw005.png)
因为数据绑定组件可以绑定不同的数据源，而一个数据源只能被一个数据绑定组件绑定，是一对多的关系，所以当我们想把相同的数据源作为SlideView的数据模型module时需要复制一份数据源。

定义好数据模型module，我们再来定义ViewModel也就是模板视图。先给SegmentView定义一个模板视图UI页面newsTypeTabTemplate.ui，修改根ALayout的id为do_ALayout_root，里面拖拽一个Label，修改id为do_Label_title，调整Label的位置和大小。
 ![](../../images/wcxw006.png)
然后我们在newsTypeTabTemplate.ui.js里把Label的text和tag属性通过`UI组件`通用的setMapping方法跟数据模型module联系起来，定义映射关系，这样ViewModule模板视图就完成了。（其中name和selected是jsonTabs数据源中的key） ![](../../images/wcxw007.png)
现在只需要修改SegmentView的template属性，将属性值指向我们刚刚定义的newsTypeTabTemplate.ui的url，View和ViewModule就联系起来了。
 ![](../../images/wcxw008.png)

最后我们要将数据模型module和它们都建立起联系，只需要用SegmentView添加绑定了数据模型module的ListData组件即可。
 ![](../../images/wcxw009.png)

更多关于数据绑定的介绍，详见[数据绑定](../../../应用开发/sections/数据绑定)

<a name="自定义事件">3. 自定义事件</a>
为了让更真实的模拟新闻类App的使用习惯，我们处理一下选择不同的SegmentView时底下的SlideView页面也跟着切换的效果，即让SegmentView和SlideView联动起来。这个步骤非常简单，只需要在SegmentView的indexChanged事件中将当前SegmentView所处cell的index赋值给SlideView的cell，即可完成。
 ![](../../images/wcxw010.png)

我们想要在SlideView切换不同的cell的同时页面数据也跟着切换，这就需要在SlideView的indexChanged事件里做大量操作，为了优化代码结构，这里就将切换数据的操作全部放在自定义事件selectOneTab中完成，只在触发indexChanged事件的回调中同时触发该自定义事件，这样我们在订阅selectOneTab事件时所作代码也都会被执行了。

订阅selectOneTab事件，在其中做更新数据的操作
 ![](../../images/wcxw011.png)

**需要特殊注意的是，自定义事件的订阅和触发可以不在同一个页面的脚本环境中完成，只需要保证自定义事件的触发在订阅之后即可**。

更多关于自定义事件的使用，详见[自定义事件](../../../应用开发/sections/事件和消息机制)。

这里为了更好的体验效果，让SlideView能无限滑动并且加载速度更快，只需要简单的设置两个属性即可。其一就是将SlideView的looping属性设置为true，实现无限滑动；其二就是设置isAllCache属性为true，在浏览上一页时预缓存下个页面。

<a name="展示新闻">4. 展示新闻</a>
新闻展示页面的数据是通过Http组件请求的后台数据，在手势向下pull或向上push滑动页面时刷新请求，接下来详细说下这个步骤如何实现。

*展示新闻*
用上面同样的方法，我们先处理一下SlideView的数据和模板，不同的是这里SlideView的模板里嵌套了一个ListView组件，所以我们先处理ListView组件。ListView的数据是从后台通过http请求获取的，所以在添加了ListView的页面newsIndexSlideTemplate.ui对应的newsIndexSlideTemplate.ui.js脚本环境中去请求数据，并在Http的请求成功事件中将数据绑定给一个ListData组件，再让ListView去绑定该数据，同时复位pull或push出来的头部。（需要注意的是，这里直接将请求到的数据绑定给ListView组件，所以需要前后台沟通好数据格式，在后台保存时也是用JSON Array。）
 ![](../../images/wcxw012.png)

因为ListView是支持多模版的，这里我们给ListView组件绑定两个模板，一个用于展示新闻列表newsRowTemplate0.ui，一个用于展示轮播图片newsRowTemplate1.ui。这两个模板也同样在模板页的根节点上调用setMapping方法定义好数据映射关系，这样数据与模板就结合起来了，在ListView上就能显示我们从后台请求到的数据了。

这里提一个小的处理，因为我们不确定要展示的数据到底有多少个字节，全部展示要占用多大的空间，所以我们设置ListView的模板页中要展示数据的Label的高度为-1，表示自动高度，并且将maxLines属性设置为2，表示最多只显示两行，这样就能控制每个cell显示数据的空间都是固定高度的，数据能整齐排列。

另外一个小处理就是让图片显示的速度更快，因为所有图片都是网络图片，显示之前都会先去请求，这样在网络环境不稳定时可能会导致图片显示框先出现默认图片（设置defaultImage）再显示真正要显示的图片。这里只需要简单的设置ImageView的cacheType为temporary，表示第一次加载图片时就缓存到本地，以后每次打开这个ImageView都会先读缓存的本地图片，然后再读服务器的网络图片，这样就能优化ImageView的加载速度，从而提高体验。

*刷新新闻*
想要在ListView页面上向下pull和向上push操作中获取新的数据并重新显示在模板中，首先要设置ListView的isFooterVisible和isHeaderVisible属性为true，这样上下拉的时候使头部和尾部可见，再分别在ListView的pull和push事件中去重新请求数据，并且在http请求的success事件中调用ListView的rebound方法让头部或尾部复位。
 ![](../../images/wcxw013.png)

<a name="九宫格展示">5. 九宫格展示</a>
最后，我们说一下第三张效果图中点击“+”号会弹出一个快速选择新闻类型的UI界面如何实现。

首先画出需要弹出的UI页面newsTypeGrids.ui，也如之前教程中处理弹出Picker页面一样，在该页面中只放一个GridView组件，其他地方设置成灰色半透明效果。再设置GridView的模板页newsTypeGridTemplate.ui，同样定义好数据映射，将之前给SegmentView定义的数据源也复制一份让GridView绑定上，最后只需要在“+”号的touch事件中让newsTypeGrids.ui显示出来即可。

### <a name="完成通讯页面">完成通讯页面</a>

本节教程将要教会大家如何加载本地通讯录。

* [导入项目](#导入项目-完通)
* [导入通讯录](#导入通讯录-完通)
* [自定义js模块](#自定义js模块-完通)

视频教程[请点击](http://v.youku.com/v_show/id_XMTU2ODcyNzU4MA==.html)观看

将要学习的demo效果图如下所示
 ![](../../images/wctx001.png)

<a name="导入项目-完通">1. 导入完整项目</a>

本节示例demo请参考[下载地址](/web/zip/20160714/326b638894c54020a103126788b9d5d5.zip)，可以导入到设计器中学习。

这节教程中将要用到的组件有do_Contact、do_IndexListView，请大家前几节教程所教授的方法，提前添加这两个组件，并打成相应调试包用于调试。

<a name="导入通讯录-完通">2. 导入通讯录</a>
`DeviceOne`开发的do_Contact组件是针对手机本地通讯录的增删查改提供相应功能的一个组件，而do_IndexListView是一个右边带索引的ListView组件，通过索引能快速定位到该索引下首条数据，常被用于类似通讯录和歌曲列表等功能中。

所以想要在App中模拟手机通讯录功能，只需简单地将本地通讯录里的数据读取出来并将这些数据绑定给IndexListView中展示即可。

先按照之前的教程中提到过的MVVM模型，给do_IndexListView定义一个模板页addressCell.ui，在addressCell.ui.js中定义好数据映射，再将do_IndexListView的template属性指向addressCell.ui的地址，这样ViewModel就定义好了。一会儿我们从本地通讯录中获取的数据将在模板中显示。

接下来再准备数据module。我们将从本地通讯录中读取出的数据绑定给do_HashData组件，

我们定义一个`MM`类的数据源组件do_HashData，并向其中添加本地通讯录中读取出来的数据，再让do_IndexListView去绑定do_HashData数据源即可。
 ![](../../images/wctx002.png)

<a name="自定义js模块-完通">3. 自定义js模块</a>
在上图红框中的代码，导入了自定义js库，获取通讯录的联系人的首字母拼音。
这里简单说下如何引用自定义js库和自定义js函数。
被引用的js库和js函数必须放在source://script目录下，文件以.js为后缀
 ![](../../images/wctx003.png)
在要引用库的.ui.js文件中引入自定义js库即可使用自定义函数了。
 ![](../../images/wctx004.png)
更详细的文档详见[JS使用](../../../应用开发/sections/JS使用)

### <a name="完成发现页面">完成发现页面</a>

* [导入项目](#导入项目-完发)
* [do_WebView组件](#do_WebView组件)
* [扫描功能](#扫描功能)
* [自定义事件](#自定义事件-完发)

视频教程[请点击](http://v.youku.com/v_show/id_XMTU2ODc4MDQ0MA==.html)观看

将要学习的demo效果图如下所示
 ![](../../images/wcfx001.png)

<a name="导入项目-完发">1. 导入完整项目</a>

本节示例demo请参考[下载地址](/web/zip/20160714/1102da049d84414fa4aee2be475a77f9.zip)，可以导入到设计器中学习。

这节教程中将要用到的组件有do_BarcodeView请大家前几节教程所教授的方法，提前添加这个组件，并打成相应调试包用于调试。

<a name="do_WebView组件">2. do_WebView组件</a>
do_WebView是一个很强大的组件，既可以访问网页，也可以加载本地html，更可以在html页面中嵌套DeviceOne组件，能完美结合h5页面和DeviceOne原生组件。

分析一下我们将要实现的发现页面，点击“扫描”按钮调用do_BarcodeView的扫描功能，进行二维码扫描，而在页面正中放一个do_WebView组件，加载本地的html文件，在该文件中自定义页面样式，并在html中画出的button按钮中响应DeviceOne的各组件功能。
 ![](../../images/wcfx002.png)

更详细的文档请见[WebView](../../../UI组件API/sections/do_WebView)

<a name="扫描功能">3.扫描功能</a>
新建一个scanBarcode.ui页面，里面就放一个do_BarcodeView组件，在点击“点击扫描”按钮后打开该页，并调用do_BarcodeView的scan功能扫描二维码，在扫描成功的回调中调用closePage关闭该页，这里仅供演示用，正常扫描的结果会在回调函数的data中返回，用户可以拿到这个data做任意操作。

<a name="自定义事件-完发">4.自定义事件</a>
`DeviceOne`提供事件和消息机制，开发者可以很方便的使用。这里有一个简单的示例：
 ![](../../images/wcfx003.png)
通过on来订阅do_ALayout_opt的touch事件，在合适的地方用fire来触发该事件，需要注意的是，事件的触发需在订阅之后。

更详细的文档请见[事件和消息机制](../../../应用开发/sections/事件和消息机制)

### <a name="应用收官">应用收官</a>

通过之前的几节教程，不知道您对使用`DeviceOne`开发一个应用是不是已经得心应手了，本节教程将教会大家如何在开发完成之后通过`DeviceOne`平台将一个应用打成安装包，用于发布到各大应用平台。

* [加密及证书](#加密及证书)
* [图标及启动页](#图标及启动页)
* [组件选择](#组件选择)
* [打包](#打包)

视频教程[请点击](http://v.youku.com/v_show/id_XMTU2ODgyNjM0OA==.html)观看

想要选择多平台、应用是横屏显示还是竖屏显示？添加更多组件、给应用添加证书、启动页等等这一系列的关于应用的配置都可以通过点击`应用开发`-`应用配置`来进行配置。
 ![](../../images/yysg001.png)

<a name="加密及证书">1. 加密及证书</a>
`DeviceOne`提供一整套关于应用的配置选项，在平台配置中，用户可以选择打哪几个平台的安装包，并对选择的平台进行相应配置，包括选择应用横屏还是竖屏显示、应用的唤醒ID、填写android平台特有的渠道ID、iOS平台的应用跳转等等各平台特有属性。而下图中蓝框中的编辑按钮是对应用名称进行修改的入口，应用名称即为安装在手机上显示的名称。
 ![](../../images/yysg002.png)

处于安全和保护知识产权的考虑，`DeviceOne`提供数据加密和项目源代码加密，用于保证项目源码的安全性和重要数据不外泄。在“证书&安全设置”中，用户可以通过勾选“代码加密”来选择是否加密自己的应用源代码，并选择各平台的证书。（这里所选择的证书是由`个人中心`－`证书管理`中填写的，也可直接点击`管理证书`。）一个应用的一个平台对应了一个证书、证书的是应用的标示，更准确的说，android平台证书中的包名、iOS平台证书中的BundleID是标示应用唯一性的凭证。
 ![](../../images/yysg003.png)

<a name="图标及启动页">2. 图标及启动页</a>
在“图标及启动页”这一选项中，用户可以自行上传所需的图标和启动页，最上面两项上传完会由`DeviceOne`平台帮助您自动生成所有平台的图标和启动页，如果有对图片分辨率要求较高的需求，用户可以在下图红框所示的下面分别上传不同平台不同分辨率的图片。
 ![](../../images/yysg004.png)

<a name="组件选择">3. 组件选择</a>
目前`DeviceOne`提供的官方组件已经有将近100个，为了保证用户打出的安装包大小不会过大，在新建应用时，我们只会将一些必要组件如do_Button、do_Label和一些核心组件添加进去，其他用户需要用到的组件就在“组件配置”中添加，这里添加的组件可以是商店里其他用户出售的组件，也可以是由用户自己的开发团队开发未开放到商店的内部组件，需要注意的是**商店组件是有版本区分的，不同版本是否向下兼容是由组件的开发者决定的，而每个版本也有对应的文档和不同功能，用户可根据自己的需要选择不同的组件版本。当所选组件迭代了新版本，无需重新选择，只需点击组件后面的升级按钮，即可看到最新版本的更新内容，用户可自行选择是否升级到最新版本。**内部组件没有组件版本，永远取最新上传的组件资源。
 ![](../../images/yysg005.png)

<a name="打包">4. 打包</a>
最后，配置完所需配置，可以开始进行打包，需要注意的是**加密、图标、启动页对调试安装包是不起作用的，调试安装包建议仅作调试使用。仅改动代码而没有添加新组件可以不用频繁地BUILD调试安装包。**而BUILD发布安装包第一次需要由IDE设计器发起，后续如果没有代码改动，只有应用配置改动，可以直接在网站发起，我们会用您最后一次从IDE发起打包的代码来进行编译。
 ![](../../images/yysg006.png)

打完的安装包，用户可以点击“扫描”，通过扫二维码的方式来进行下载，或者点击“下载安装”将安装包下载到本地。
 ![](../../images/yysg007.png)


[回到顶部](#top)
