---
title: do_BarcodeView 组件
---

### do_BarcodeView 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_BarcodeView)
 条码扫描视图，能设置view的基本属性，宽高等，扫描框内有矩形校正区域，扫描时有简单的动画显示，支持一维码、二维码（包括QR码、DM码等），若想在页面已启动时就加载扫描功能，建议将start方法放在do_Page的loaded事件回调中执行。
 下图为扫描区域跟组件大小一样的效果图：
 <img src="../../images/barcodeview_scan.png" width="330" height="380" />

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#42b983'>属性</font>  |[scanArea](#scanArea)| 扫描的区域
<font color ='#0092db'>同步方法</font>  |[flash](#flash)| 开关闪光灯
<font color ='#0092db'>异步方法</font>  |[start](#start)| 启动扫描

#### <font color ='#40A977'>**1.**</font> 属性

>###### <span id="scanArea"><font color ='#42b983'>**scanArea**</font></span>: 扫描的区域

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 :
- 说明 : 设置扫描区域的位置和宽高，x,y,width,height，中间用逗号隔开；扫描区域不建议设置超出组件本身宽高和范围；默认值取控件的一半宽高，居中显示，修改后必须重新调start方法才会生效。
- 示例:
  ```javascript

  var do_BarcodeView = ui("do_BarcodeView_1");

  //设置扫描的区域 150,150,300,300,设置后需要调用start方法重新启动扫描才可以生效
  do_BarcodeView.scanArea = "150,150,300,300";
  do_BarcodeView.start(function(data) {
  	if (data)
  		deviceone.print(JSON.stringify(data), "扫描结果");
  });

  ```
  下图是组件宽高为600,600设置扫描区域为"150,150,300,300"的效果图：    
  <img src="../../images/barcodeview_setscanarea.png" width="330" height="380" />

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id="flash"><font color ='#0092db'>**flash**</font></span>: 开关闪光灯

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |------|------|------|------
  **status** |<font color ='#808000'>**string**</font> | 是 | |闪光灯状态，支持两种状态：on（开启）、off（关闭）
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 开关手机系统闪光灯
- 示例:
  ```javascript

  //开启闪光灯
  do_BarcodeView.flash("on");
  //关闭闪光灯
  do_BarcodeView.flash("off");

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <span id="start"><font color ='#0092db'>**start**</font></span>: 启动扫描

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回data是一个JSON对象类型
- 说明: 条码扫描成功后会自动停止并执行异步回调，将扫描结果返回，如需再次扫描需重新调用该方法
- 示例:
  ```javascript

  // 启动扫描
	do_BarcodeView.start(function(data) {
		  if (data)
			    deviceone.print(JSON.stringify(data), "扫描结果");
	});

  //扫描结果示例
  {
      "code":"QR_CODE",
      "value":"http://www.deviceone.net"
  }
  
  ```

#### <font color ='#40A977'>**4.**</font> 事件

#### <font color ='#40A977'>**5.**</font> 常见问题

- 1. IOS二维码生成时选择定位区域图形,不规则图形导致的无法扫描成功。   
     原因： iOS使用的是原生的框架，如果扫描失败就无法识别了

#### <font color ='#40A977'>**6.**</font> 基本配置

[回到顶部](#top)
