---
title: 使用Android Studio开发第一个Andoird组件
---
### 使用Android Studio开发第一个Andoird组件

## [DeviceOne文档](http://doc.deviceone.net/web/doc/index.htm)  > [高级教程](http://doc.deviceone.net/web/doc/advance_course.htm)> Android Studio 开发组件资源上传规则

以M3506_MobileRTC组件为类，这个组件依赖两个zoom-common-lib，zoom-mobilertc第三方库
![](../../images/ans/ane001.png)
这个Project总共分为四部分：app，M3506_MobileRTC，zoom-common-lib，zoom-mobilertc
app: 里面都是一些测试代码，用来测试组件用的，组件上传资源**不需要**包含此部分代码
M3506_MobileRTC：组件的开发工作都在这个项目中，**需要**实现组件的具体功能，组件上传资源需要包含此部分代码
zoom-common-lib：组件的依赖Module，组件上传资源**需要**包含此部分代码
zoom-mobilertc：组件的依赖Module，组件上传资源**需要**包含此部分代码

app 与M3506_MobileRTC 目录结构如下
![](../../images/ans/ane002.png)

![](../../images/ans/ane003.png)

介绍完这些后，就正式说一下资源压缩规则了
1.Build 资源成aar文件 Build/Rebuild Project
![](../../images/ans/ane004.png)

Build 成功后会在 build/outputs/aar/ 目录下面生成以组件ID 为资源名称的 **M3506_MobileRTC.aar，不要修改资源名称，修改了打包会失败**
![](../../images/ans/ane005.png)

**2.手动删除M3506_MobileRTC.aar中的docore.jar**

**3.复制 M3506_MobileRTC.aar，zoom-common-lib-release.aar，zoom-mobilertc-release.aar 到临时目录M3506_MobileRTC**

**4.在M3506_MobileRTC目录创建一个aar空文件**
![](../../images/ans/ane006.png)

5.使用zip压缩 **aar，M3506_MobileRTC.aar，zoom-common-lib-release.aar，zoom-mobilertc-release.aar**四个文件
![](../../images/ans/ane007.png)

**Zip的目录结构如下：（注意不要多添加一层目录）**
![](../../images/ans/ane008.png)

**6.上传M3506_MobileRTC.zip 文件即可**

**PS：<mark>
1.Android Studio版本不能使用DoResourcesHelper 获取资源
2.如果有so文件的话，必须有armeabi-v7a架构的so的文件，否则会运行失败
</mark>**

[回到顶部](#top)
