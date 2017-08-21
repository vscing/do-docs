---
title: do_BaiduNavigate 组件
---

### do_BaiduNavigate 组件

* 支持平台: iOS7.0,Android4.0
百度导航支持语音播报（使用语言播报，需要在http://app.navi.baidu.com/ttsregister/appinfo导航TTS平台中进行注册申请），路线规划及导航

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**start**</font>: 开始导航

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **startPoint** |<font color ='#808000'>**string**</font> |  | 是||设置起点经纬度，如39.915174,116.403901表示(纬度,经度)
  **endPoint** |<font color ='#808000'>**string**</font> |  | 是||设置终点经纬度，如40.915174,117.403901表示(纬度,经度)
  **coType** |<font color ='#808000'>**string**</font> | BD09LL | 否|BD09LL|BD09_MC：百度墨卡托坐标，ios不支持；BD09LL：百度经纬度坐标；GCJ02：国测局坐标，ios不支持；WGS84：GPS坐标
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 开始导航，计算路线
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <font color ='#e96900'>**failed**</font>: 导航失败时候触发

- 返回值类型 : <font color ='#808000'>****</font>
- 返回值描述: 
- 说明: 导航失败时候触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**begin**</font>: 开始导航

- 返回值类型 : <font color ='#808000'>****</font>
- 返回值描述: 
- 说明: 开始导航
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**success**</font>: 成功开启导航

- 返回值类型 : <font color ='#808000'>****</font>
- 返回值描述: 
- 说明: 成功开启导航
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


