---
title: do_VideoRecord 组件
---

### do_VideoRecord 组件

 支持平台: iOS7.0,Android
 录制视频，输出MP4格式

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**start**</font>: 开始录制视频

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **quality** |<font color ='#808000'>**string**</font> | 否 | normal|选择录音输出的质量，支持high(1920*1080)、normal(1280*720)、low(640*480),如果手机不支持high,以及normal,默认为low格式
  **limit** |<font color ='#808000'>**number**</font> | 否 | -1|录制视频的时长限制，以毫秒为单位，-1时表示不限时长
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 打开录制界面开始录制视频
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**stop**</font>: 停止录制视频

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 停止录制视频
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <font color ='#e96900'>**error**</font>: 录制出错事件

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 
- 说明: 录制出错事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**finish**</font>: 完成录制

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回值包含两个节点{path:'data://temp/do_VideoRecord/20160101101010111.mp4',size:'232342'}，其中path为保存视频的路径，文件名是日期+精确到毫秒时间；size为视频大小，单位为KB
- 说明: 完成录制
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


