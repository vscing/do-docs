---
title: M0011_TencentLive 组件
---

### M0011_TencentLive 组件

 支持平台: iOS,Android
 必须配合服务端使用，服务端文档详见https://www.qcloud.com/document/product/454/6808#2..E4.BF.AE.E6.94.B9.E5.9C.A8.E7.BA.BF.E7.8A.B6.E6.80.81，前端数据以put方式发送

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**startPlay**</font>: 进入直播

- 参数:

  名称 | 类型 |是否必填|缺省值|说明
  ---- |-------------  |--------------|--------|------
  **serverUrl** |<font color ='#808000'>**string**</font> |  | 是|业务服务器地址，部署小直播后台地址
  **liveInfo** |<font color ='#808000'>**object**</font> |  | 是|为fetchList方法返回值中的pusherlist数组中的一项，具体参考fetchList描述
  **roomNo** |<font color ='#808000'>**string**</font> |  | 是|订阅后返回的房间号
  **serverShareUrl** |<font color ='#808000'>**string**</font> |  | 是|请参考：https://www.qcloud.com/document/product/454/8046
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 进入直播室（观众）
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**startPush**</font>: 开始直播

- 参数:

  名称 | 类型 |是否必填|缺省值|说明
  ---- |-------------  |--------------|--------|------
  **serverUrl** |<font color ='#808000'>**string**</font> |  | 是|业务服务器地址，部署小直播后台地址
  **title** |<font color ='#808000'>**string**</font> |  | 是|
  **location** |<font color ='#808000'>**string**</font> | 主播当前经纬度，如39.915174,116.403901表示(纬度,经度) | 否|
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 开始直播（主播），参考https://www.qcloud.com/document/product/454/6808#2..E4.BF.AE.E6.94.B9.E5.9C.A8.E7.BA.BF.E7.8A.B6.E6.80.814.拉取列表 pusherinfo定义
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <font color ='#0092db'>**uploadFrontcover**</font>: 上传封面

- 参数:

  名称 | 类型 |是否必填|缺省值|说明
  ---- |-------------  |--------------|--------|------
  **serverUrl** |<font color ='#808000'>**string**</font> |  | 是|业务服务器地址，部署小直播后台地址
  **image** |<font color ='#808000'>**string**</font> |  | 是|以data://或者source://开始的图片路径
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {"code":"错误码，0表示成功，其他表示失败","url":"上传成功后返回的网络url"}
- 说明: 上传封面
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**fetchList**</font>: 拉取房间列表

- 参数:

  名称 | 类型 |是否必填|缺省值|说明
  ---- |-------------  |--------------|--------|------
  **serverUrl** |<font color ='#808000'>**string**</font> |  | 是|业务服务器地址，部署小直播后台地址
  **flag** |<font color ='#808000'>**number**</font> | 1 | 否|1:拉取在线直播列表 2:拉取7天内点播列表 3:拉取在线直播和7天内点播列表，直播列表在前，点播列表在后
  **pageno** |<font color ='#808000'>**number**</font> | 0 | 否|分页号
  **pagesize** |<font color ='#808000'>**number**</font> | 20 | 否|每页大小
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 详细返回信息参见https://www.qcloud.com/document/product/454/6808#2..E4.BF.AE.E6.94.B9.E5.9C.A8.E7.BA.BF.E7.8A.B6.E6.80.81 4.拉取列表"returnValue":"错误码，0表示成功，其他表示失败","returnMsg":"错误码的描述","returnData":{"pusherlist":"直播、点播列表数据（数组）","totalcount":"列表总数"}
- 说明: 拉取房间列表
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**login**</font>: 登录

- 参数:

  名称 | 类型 |是否必填|缺省值|说明
  ---- |-------------  |--------------|--------|------
  **accountType** |<font color ='#808000'>**string**</font> |  | 是|用户的账号类型
  **identifier** |<font color ='#808000'>**string**</font> |  | 是|用户名
  **userSig** |<font color ='#808000'>**string**</font> |  | 是|鉴权Token
  **accessToken** |<font color ='#808000'>**string**</font> |  | 是|当用户在服务端登录（项目业务服务端）后会返回该值，游客登录时该值为空串
  **nickname** |<font color ='#808000'>**string**</font> |  | 是|
  **headpic** |<font color ='#808000'>**string**</font> | 网络地址 | 否|
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {"returnValue":"错误码，0表示成功，其他表示失败","returnMsg":"错误的描述"}
- 说明: 使用腾讯云信账号登录，需要自己搭建注册环境，对接云信平台
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件

>###### <font color ='#e96900'>**C2P**</font>: 组件触发事件跳到指定的业务逻辑界面

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回参数类型{type:''},type=1标示充值,type=2标示登陆
- 说明: 组件触发事件跳到指定的业务逻辑界面
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**ShareEvent**</font>: 组件触发事件跳到指定的业务逻辑界面

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {content: '内容',image: '封面地址',scene: '0表示分享给微信好友;1表示分享到朋友圈',title: '标题',url: '直播地址'}
- 说明: 组件触发事件跳到指定的业务逻辑界面
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


