---
title: do_FrameAnimationView 组件
---

### do_FrameAnimationView 组件

 支持平台: iOS7.0,Android4.0以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_FrameAnimationView)
 帧动画视图，可以加载gif动图，也可以将多张图片组合设置为动图效果。

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#0092db'>同步方法</font>  |[startImages](#startImages)| 开始动画
<font color ='#0092db'>同步方法</font>  |[startGif](#startGif)| 开始动画
<font color ='#0092db'>同步方法</font>  |[stop](#stop)| 结束动画

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=startImages><font color ='#0092db'>**startImages**</font></span>: 开始动画

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **data** |<font color ='#808000'>**object**</font> | 是 | |
  **repeat** |<font color ='#808000'>**number**</font> | 否 | 1|默认值为1执行一次动画效果，小于0时表示无限循环，为0时表示没有动画效果,大于0表示动画效果重复的次数
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明:data参数示例如下   

  ```
  [
      {
          "path":"data://2.png",      //图片支持data://, source://路径
          "duration":50               //duration的单位为毫秒
      },
      {
          "path":"data://3.png",
          "duration":50
      },
      ...    
  ]
  ```
- 示例:

  ```javascript

  //1.开始动画,支持source://路径下的图片
  var imgs = [];
  for (var i = 1; i <= 8; i++) {
  	imgs.push({
  		path : "source://view/do_FrameAnimationView/image/" + i + ".png",
  		duration : 100
  	});
  }
  do_FrameAnimationView.startImages({data:imgs, repeat:-1}); //repeat值为-1表示无限循环           


  //2.开始动画,支持data://路径下的图片
  var source_images = [], target_images = [];
	for (var i = 1; i <= 12; i++) {
		source_images.push("initdata://" + i + ".png");
	}
	for (var i = 1; i <= 12; i++) {
		target_images.push({
			path : "data://gif/image/" + i + ".png",
			duration : 100
		});
	}
	if (!sm("do_Storage").fileExist("data://gif/image/12.png")) {
    // data://gif/image/下不存在图片先拷贝图片
		sm("do_InitData").copy(source_images, "data://gif/image/",
			function(_d, e) {
				if (_d) { // 拷贝文件成功
					do_FrameAnimationView.startImages({
						data : target_images,
						repeat : -1
					});
				}
			})
	} else {
		do_FrameAnimationView.startImages({
			data : target_images,
			repeat : -1
		});
	}

  ```
  左图为图片是source路劲下的效果图，右图为图片是data路劲下的效果图（可以下载组件示例代码运行看动图效果）：     
  <div>
  <img src="../../images/frameanimationview_sourceimage.png" height="380" width="320" >

  <img src="../../images/frameanimationview_dataimage.png" height="380" width="320" >

  </div>

[回到顶部](#top)

>##### <span id=startGif><font color ='#0092db'>**startGif**</font></span>: 开始动画

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **data** |<font color ='#808000'>**string**</font> | 是 | |图片支持data://, source://路径
  **repeat** |<font color ='#808000'>**number**</font> | 否 | 1|默认值为1执行一次动画效果，小于0时表示无限循环，为0时表示没有动画效果,大于0表示动画效果重复的次数；windows平台不支持设置重复次数，只能循环播放
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明:
- 示例:

  ```javascript

  //1.开始动画,支持source://路径下的gif图片
  do_FrameAnimationView.startGif({
		data : "source://view/do_FrameAnimationView/image/timg.gif",
		repeat : -1
	});

  //2.开始动画,支持data://路径下的gif图片
  if (!sm("do_Storage").fileExist("data://gif/pic.gif")) {
    //data路径下不存在gif图片，先拷贝
    sm("do_InitData").copyFile("initdata://pic.gif",
			"data://gif/pic.gif", function(_d, e) {
				if (_d) {
					do_FrameAnimationView.startGif({
						data : "data://gif/pic.gif",
						repeat : -1
					});
				}
			})
	} else {
		do_FrameAnimationView.startGif({
			data : "data://gif/pic.gif",
			repeat : -1
		});
	}

  ```
  左图为gif图片是source路劲下的效果图，右图为gif图片是data路劲下的效果图（可以下载组件示例代码运行看动图效果）：     
  <div>
  <img src="../../images/frameanimationview_sourcegif.png" height="380" width="320" >

  <img src="../../images/frameanimationview_datagif.png" height="380" width="320" >

  </div>

[回到顶部](#top)

>##### <span id=stop><font color ='#0092db'>**stop**</font></span>: 结束动画

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明:
- 示例:

  ```javascript

  do_FrameAnimationView.stop();  //结束动画

  ```

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件


#### <font color ='#40A977'>**5.**</font> 常见问题


#### <font color ='#40A977'>**6.**</font> 基本配置

[回到顶部](#top)
