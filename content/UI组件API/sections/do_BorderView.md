---
title: do_BorderView 组件
---

### do_BorderView 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_BorderView)
 这个UI组件包含多个子视图(UI文件），里面最多能放五个子视图，分别停靠在上、右、下、左、中五条边线，组件绘制顺序为上右下左中，子视图之间不会重叠，若某一方向的子视图过大，造成下一顺序的子视图没有可用空间绘制则不显示下一顺序的子视图

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#42b983'>属性</font>  |[items](#items)| BorderView显示内容
<font color ='#42b983'>属性</font>  |[centerFillParent](#centerFillParent)| 居中子视图填充父容器
<font color ='#42b983'>属性</font>  |[topView](#topView)| 居上子视图
<font color ='#42b983'>属性</font>  |[rightView](#rightView)| 居右子视图
<font color ='#42b983'>属性</font>  |[bottomView](#bottomView)| 居下子视图
<font color ='#42b983'>属性</font>  |[leftView](#leftView)| 居左子视图
<font color ='#42b983'>属性</font>  |[centerView](#centerView)| 居中子视图
<font color ='#0092db'>同步方法</font>  |[getView](#getView)| 获取子组件地址

#### <font color ='#40A977'>**1.**</font> 属性

>###### <span id=items><font color ='#42b983'>**items**</font></span>: BorderView显示内容

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 :
- 说明 : 设置BorderView显示内容（必须是一个Object），例如：item格式如下，其中rightView与centerView表示数据指定给BorderView的具体View，必须为topView、rightView、bottomView、leftView、centerView的其中一个
  ```

  {
      "rightView":{
          "template":0,
          "image":"source://1.jpg"
      },
      "centerView":{
          "template":2,
          "title":"content",
          "image":"source://1.jpg"
      }
  }
  ```

>###### <span id=centerFillParent><font color ='#42b983'>**centerFillParent**</font></span>: 居中子视图填充父容器

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : false
- 说明 : 居中的子视图是否向四周填充，为false时不填充，此时居中子视图会居中显示；为true时填充上、右、下、左子视图（若存在）绘制完成后的中间剩余部分

>###### <span id=topView><font color ='#42b983'>**topView**</font></span>: 居上子视图

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 :
- 说明 : 设置要显示的居上子视图ui文件路径，有改动需要调UI组件的基类方法redraw才能生效

>###### <span id=rightView><font color ='#42b983'>**rightView**</font></span>: 居右子视图

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 :
- 说明 : 设置要显示的居右子视图ui文件路径，有改动需要调UI组件的基类方法redraw才能生效

>###### <span id=bottomView><font color ='#42b983'>**bottomView**</font></span>: 居下子视图

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 :
- 说明 : 设置要显示的居下子视图ui文件路径，有改动需要调UI组件的基类方法redraw才能生效

>###### <span id=leftView><font color ='#42b983'>**leftView**</font></span>: 居左子视图

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 :
- 说明 : 设置要显示的居左子视图视图ui文件路径，有改动需要调UI组件的基类方法redraw才能生效

>###### <span id=centerView><font color ='#42b983'>**centerView**</font></span>: 居中子视图

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 :
- 说明 : 设置要显示的居中子视图视图ui文件路径，有改动需要调UI组件的基类方法redraw才能生效

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=getView><font color ='#0092db'>**getView**</font></span>: 获取子组件地址

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **direction** |<font color ='#808000'>**string**</font> | 是 | |要获取地址的子组件方向，有以下枚举值：top、right、bottom、left、center，分别表示居上、右、下、左、中子视图
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 子组件地址
- 说明: 获取子组件地址
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件
