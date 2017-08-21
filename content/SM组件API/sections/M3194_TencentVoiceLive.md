---
title: M3194_TencentVoiceLive 组件
---

### M3194_TencentVoiceLive 组件

 支持平台: iOS8.0,Android4.0
 

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**logout**</font>: 登出

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**enableSpeaker**</font>: 打开/关闭扬声器

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **isEnable** |<font color ='#808000'>**Boolean**</font> | false | 否|false|true表示开启，false表示关闭
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 开启或关闭扬声器/耳机。
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**enableMic**</font>: 打开/关闭麦

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **isEnable** |<font color ='#808000'>**Boolean**</font> | true | 否|true|true表示开启，false表示关闭
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 打开/关闭麦
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**getVolume**</font>: 获取麦克风的音量

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 音频设备音量，范围0－100
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**getDynamicVolume**</font>: 获取麦克风的实时音量

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 音频设备音量，范围0－100
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <font color ='#0092db'>**login**</font>: 登录

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **userId** |<font color ='#808000'>**string**</font> |  | 是||
  **accountType** |<font color ='#808000'>**string**</font> |  | 是||用户的账号类型
  **identifier** |<font color ='#808000'>**string**</font> |  | 是||用户名
  **userSig** |<font color ='#808000'>**string**</font> |  | 是||鉴权Token
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {"returnValue":"错误码，0表示成功，其他表示失败","returnMsg":"错误的描述"}
- 说明: 使用腾讯云信账号登录，需要自己搭建注册环境，对接云信平台
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**createRoom**</font>: 创建房间

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **roomId** |<font color ='#808000'>**number**</font> |  | 是||房间id 房间唯一标识 建议由业务方后台统一分配
  **controlRole** |<font color ='#808000'>**string**</font> |  | 是||
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {"returnValue":"错误码，0表示成功，其他表示失败","returnMsg":"错误码的描述"}
- 说明: 创建一个直播，只有在初始化和登录成功之后才能创建直播
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**joinRoom**</font>: 加入房间

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **roomId** |<font color ='#808000'>**string**</font> |  | 是||
  **controlRole** |<font color ='#808000'>**string**</font> | 1 | 否|1|
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {"returnValue":"错误码，0表示成功，其他表示失败","returnMsg":"错误码的描述"}
- 说明: 观众角色调用加入房间接口
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**quitRoom**</font>: 退出房间

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {"returnValue":"错误码，0表示成功，其他表示失败","returnMsg":"错误码的描述"}
- 说明: 退出房间
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件


