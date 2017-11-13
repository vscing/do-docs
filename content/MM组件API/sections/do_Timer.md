---
title: do_Timer 组件
---

### do_Timer 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/MM/do_Timer)
 定时器，功能是在指定的时间间隔内反复触发指定任务事件，应用于“发送验证码倒计时“等记时相关的场景

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#42b983'>属性</font>  |[delay](#delay)| 延时启动时间
<font color ='#42b983'>属性</font>  |[interval](#interval)| 间隔时间
<font color ='#0092db'>同步方法</font>  |[start](#start)| 启动
<font color ='#0092db'>同步方法</font>  |[stop](#stop)| 取消
<font color ='#0092db'>同步方法</font>  |[isStart](#isStart)| 是否启动定时器
<font color ='#e96900'>事件</font>  |[tick](#tick)| 固定间隔被调用触发

#### <font color ='#40A977'>**1.**</font> 属性

>###### <span id=delay><font color ='#42b983'>**delay**</font></span>: 延时启动时间

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 0
- 说明 : 从现在起延迟多长时间开始启动，单位为毫秒，<0时不执行定时任务

>###### <span id=interval><font color ='#42b983'>**interval**</font></span>: 间隔时间

- 数据类型 : <font color ='#808000'>**number**</font>
- 默认值 : 1000
- 说明 : 定时器将每隔指定豪秒时间触发一次事件,单位毫秒，默认为1000，<=0时不执行定时任务

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=start><font color ='#0092db'>**start**</font></span>: 启动

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 启动定时器
- 示例:

  ```javascript
  //开始计时器,5秒后触发第一次,之后每2秒触发一次
  do_Timer.delay = 5000;
  do_Timer.interval = 2000;
  do_Timer.start()

  ```

[回到顶部](#top)

>##### <span id=stop><font color ='#0092db'>**stop**</font></span>: 取消

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 取消定时器
- 示例:

  ```javascript
  do_Timer.stop()

  ```

[回到顶部](#top)

>##### <span id=isStart><font color ='#0092db'>**isStart**</font></span>: 是否启动定时器

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: 为true时定时器为启动状态，false时定时器为未启动状态
- 说明: 判断定时器是否启动，返回当前状态
- 示例:

  ```javascript
  var data = do_Timer.isStart();
	deviceone.print(data,"计时器是否启动")

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=tick><font color ='#e96900'>**tick**</font></span>: 固定间隔被调用触发

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述:
- 说明: 固定间隔被调用触发
- 示例:

  ```javascript
  do_Timer.on("tick",function(){
	   deviceone.print("计时器触发")
  })

  ```

[回到顶部](#top)
