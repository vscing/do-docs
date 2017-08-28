---
title: XmturuiOCR 组件
---

### XmturuiOCR 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/XmturuiOCR)
 

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#0092db'>同步方法</font>  |[scan](#scan)| 打开火车票识别界面
<font color ='#e96900'>事件</font>  |[result](#result)| 

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=scan><font color ='#0092db'>**scan**</font></span>: 打开火车票识别界面

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **appKey** |<font color ='#808000'>**string**</font> | 是 | |
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 打开界面，点击拍照，会触发result事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=result><font color ='#e96900'>**result**</font></span>: 

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回识别后的数据，{{start:'起始站',num:'车次',end:'终点站',time:'发车时间',seat:'座位号',name:'姓名',seatclass:'座位类型',cardNum:'身份证号码',price:'价格'}}
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


