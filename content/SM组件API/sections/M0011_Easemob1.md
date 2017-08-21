---
title: M0011_Easemob1 组件
---

### M0011_Easemob1 组件

* 支持平台: iOS7,Android16
环信即时通讯IM

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**makeVoiceCall**</font>: 拨打语音通话

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **username** |<font color ='#808000'>**string**</font> |  | 是||拨打语音通话给指定的username
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**logoff**</font>: 注销用户

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**createGroup**</font>: 创建群组

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **subject** |<font color ='#808000'>**string**</font> |  | 否||
  **description** |<font color ='#808000'>**string**</font> |  | 否||
  **occupants** |<font color ='#808000'>**object**</font> |  | 否||群组成员的IM用户名（不包括创建者自己,是一个数组）
  **style** |<font color ='#808000'>**number**</font> | 2 | 否|2|是一个枚举值。0.OnlyOwnerInvite:私有群组，创建完成后，只允许Owner 邀请用户加入；1.MemberCanInvite:私有群组，创建完成后，只允许Owner 和群成员邀请用户加入；2.JoinNeedApproval:公开群组，创建完成后，只允许Owner 邀请用户加入; 非群成员用户需发送入群申请，Owner 同意后才能入组；3.OpenJoin:公开群组，创建完成后，允许非群组成员加入，不需要Owner同意
  **message** |<font color ='#808000'>**string**</font> |  | 否||邀请成员加入时,附带消息
  **maxUsersCount** |<font color ='#808000'>**number**</font> | 200 | 否|200|群组的最大成员数(3 - 2000，默认是200)
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回群组id{"groupId":""}
- 说明: 当前创建群组的IM用户为该群的Owner，不建议从客户端创建群，因为从客户端创建的群没有邀请权限，建议用户自己搭建后台调用环信接口创建群，或者直接在唤醒开发者后台创建群
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**fetchGroupInfo**</font>: 获取群组信息

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **groupId** |<font color ='#808000'>**string**</font> |  | 是||
  **includeMembersList** |<font color ='#808000'>**boolean**</font> | false | 否|false|为true时获取群成员列表
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回的信息，和新建群时的参数一致。。。
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**inviteToGroup**</font>: 邀请用户加入群组

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **groupId** |<font color ='#808000'>**string**</font> |  | 是||
  **invitee** |<font color ='#808000'>**object**</font> |  | 是||IM用户名数组
  **reason** |<font color ='#808000'>**string**</font> |  | 否||
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**acceptInvitationFromGroup**</font>: 接受入群邀请

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **groupId** |<font color ='#808000'>**string**</font> |  | 是||
  **inviter** |<font color ='#808000'>**string**</font> |  | 否||
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**declineInvitationFromGroup**</font>: 拒绝入群邀请

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **groupId** |<font color ='#808000'>**string**</font> |  | 是||
  **inviter** |<font color ='#808000'>**string**</font> |  | 否||
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**applyJoinToGroup**</font>: 发送进群申请

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **groupId** |<font color ='#808000'>**string**</font> |  | 是||
  **reason** |<font color ='#808000'>**string**</font> |  | 否||
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 用户主动申请加入一个公开群组，群类型只能为JoinNeedApproval或OpenJoin
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**acceptJoinApplication**</font>: 同意加入群组的申请

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **groupId** |<font color ='#808000'>**string**</font> |  | 是||
  **groupName** |<font color ='#808000'>**string**</font> |  | 是||
  **applicant** |<font color ='#808000'>**string**</font> |  | 是||
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 只有群Owner调用该方法才有效
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**declineJoinApplication**</font>: 拒绝加入群组的申请

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **groupId** |<font color ='#808000'>**string**</font> |  | 是||
  **applicant** |<font color ='#808000'>**string**</font> |  | 是||
  **reason** |<font color ='#808000'>**string**</font> |  | 否||
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 只有群Owner调用该方法才有效
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**leaveGroup**</font>: 主动退群

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **groupId** |<font color ='#808000'>**string**</font> |  | 是||
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 群主（Owner）不支持退群操作，只能解散群。退出群组分为主动退群和被动退群。被动退群即为被Owner踢出群组
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**destroyGroup**</font>: 解散群组

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **groupId** |<font color ='#808000'>**string**</font> |  | 是||
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 解散群组需要Owner权限。
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**changeGroupSubject**</font>: 修改群

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **groupId** |<font color ='#808000'>**string**</font> |  | 是||
  **subject** |<font color ='#808000'>**string**</font> |  | 是||
  **description** |<font color ='#808000'>**string**</font> |  | 否||只支持iOS平台
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 只有Owner有权限修改。修改群的名称和描述
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**removeOccupants**</font>: 踢出群组成员

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **groupId** |<font color ='#808000'>**string**</font> |  | 是||
  **occupants** |<font color ='#808000'>**object**</font> |  | 是||要踢出的群组成员的IM用户名（不包括创建者自己,是一个数组）
  **reason** |<font color ='#808000'>**string**</font> |  | 否||
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 只有Owner有权限修改
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <font color ='#0092db'>**revokeMessage**</font>: 撤回消息

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **conversationId** |<font color ='#808000'>**string**</font> |  | 是||IM用户名username（单聊）、groupID（群聊）
  **messageId** |<font color ='#808000'>**string**</font> |  | 是||
- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: 撤回是否成功
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**login**</font>: IM用户登录

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **username** |<font color ='#808000'>**string**</font> |  | 是||
  **password** |<font color ='#808000'>**string**</font> |  | 是||
  **autoLogin** |<font color ='#808000'>**boolean**</font> | false | 否|false|即首次登录成功后，不需要再次调用登录方法，在下次 APP 启动时，SDK 会自动为您登录
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 登录是否成功，返回信息为{state:' 0 成功 | 1 失败 ',message:' 回执信息 '}
- 说明: 使用IM用户信息登录
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**sendTextMessage**</font>: 发送文本消息

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **username** |<font color ='#808000'>**string**</font> |  | 是||单聊时为需要发送消息对象的IM用户名；群聊时为groupId
  **text** |<font color ='#808000'>**string**</font> |  | 是||发送文本的内容
  **chatType** |<font color ='#808000'>**string**</font> | Chat | 否|Chat|发送会话的类型，是一个枚举值，包括单聊(Chat)，群聊(GroupChat)
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {“messageId”:“消息的唯一标识符”}
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**sendLocationMessage**</font>: 发送位置消息

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **username** |<font color ='#808000'>**string**</font> |  | 是||
  **latitude** |<font color ='#808000'>**number**</font> |  | 是||
  **longitude** |<font color ='#808000'>**number**</font> |  | 是||
  **address** |<font color ='#808000'>**string**</font> |  | 否||具体位置信息
  **chatType** |<font color ='#808000'>**string**</font> | Chat | 否|Chat|发送会话的类型，是一个枚举值，包括单聊(Chat)，群聊(GroupChat)
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {“messageId”:“消息的唯一标识符”}
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**sendMediaMessage**</font>: 发送多媒体消息

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **username** |<font color ='#808000'>**string**</font> |  | 是||
  **messageType** |<font color ='#808000'>**number**</font> |  | 是||发送消息的类型，是一个枚举，包括0.图片(Image)，1.语音(Voice)，2.视频(Video)，3.文件(File)
  **path** |<font color ='#808000'>**string**</font> |  | 是||图片，语音，视频的路径，只支持本地data://目录
  **title** |<font color ='#808000'>**string**</font> |  | 否||
  **chatType** |<font color ='#808000'>**string**</font> | Chat | 否|Chat|发送会话的类型，是一个枚举值，包括单聊(Chat)，群聊(GroupChat)
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {“messageId”:“消息的唯一标识符”}
- 说明: 发送多媒体消息，包括：图片，语音，视频
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**getAllConversations**</font>: 获取所有会话

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 获取会话列表是一个数组，返回值包括[{"conversationId":"IM用户名username（单聊）、groupID（群聊）","type":"是一个枚举，包括单聊(Chat)，群聊(GroupChat)","timestamp":"最后一条消息的时间戳","lastMessage":"最后一条消息，当消息为文本时则显示消息内容；若为定位消息则显示[定位]；若为图片消息则显示[图片]；若为语音消息则显示[语音]；若为音频消息则显示[音频]；若为文件消息则显示[文件]"}]，环信只支持获取本设备中的会话消息，如果要获取账号下所有设备中有过的会话消息，需要用户自己搭建服务器对接环信的服务器
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**deleteConversation**</font>: 删除会话

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **conversationId** |<font color ='#808000'>**object**</font> |  | 是||会话id数组
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**getConversation**</font>: 获取单个会话

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **conversationId** |<font color ='#808000'>**string**</font> |  | 是||
  **chatType** |<font color ='#808000'>**string**</font> | Chat | 否|Chat|发送会话的类型，是一个枚举值，包括单聊(Chat)，群聊(GroupChat)
  **maxCount** |<font color ='#808000'>**number**</font> | 20 | 否|20|加载记录的最大消息数
  **messageId** |<font color ='#808000'>**string**</font> |  | 否||开始查询的起点message的Id，如果不填的话默认从最新的一条开始
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: [{"messageId": "消息的唯一标识符","conversationId": "所属会话的唯一标识符","from": "发送方","to": "接收方","timestamp": "时间戳","body":{"type":"消息体类型，包括，0.Text(文本),1.Image(图片),2.Location(位置),3.Voice(语音),4.Video(视频),5.File(文件)","text（type为0）": "消息内容","remotePath（type为1）": "大图remote路径","localPath（type为1）": "大图local路径","thumbnailRemotePath（type为1）": "小图remote路径","thumbnailLocalPath（type为1）": "小图local路径","latitude（type为2）": "纬度","longitude（type为2）": "经度","address（type为2）": "地址","remotePath（type为3）": "音频remote路径","localPath（type为3）": "音频local路径","fileLength（type为3）": "音频文件大小","duration（type为3）":"音频的时间长度","remotePath（type为4）": "视频remote路径","localPath（type为4）": "视频local路径","thumbnailRemotePath（type为4）": "第一帧缩略图remote路径","thumbnailLocalPath（type为4）": "第一帧缩略图local路径","fileLength（type为4）": "视频文件大小","duration（type为4）": "视频的时间长度","remotePath（type为5）": "文件remote路径","localPath（type为5）": "文件local路径","fileLength（type为5）": "文件文件大小"}}]
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**unreadMessagesCount**</font>: 获取会话未读消息数

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **conversationId** |<font color ='#808000'>**string**</font> |  | 是||
  **chatType** |<font color ='#808000'>**string**</font> | Chat | 否|Chat|发送会话的类型，是一个枚举值，包括单聊(Chat)，群聊(GroupChat)
- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 当前会话的未读消息数
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**getPublicGroups**</font>: 获取公开群组

- 参数:

  名称 | 数据类型 |默认值|是否必填|缺省值|说明
  ---- |-------------  |----------|--------------|--------|------
  **cursor** |<font color ='#808000'>**number**</font> |  | 是||设置起始位置，从1开始计数
  **pageSize** |<font color ='#808000'>**number**</font> |  | 是||期望返回结果的数量
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: [{"groupId":"群组id"}]
- 说明: 获取指定范围内的公开群。
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件

>###### <font color ='#e96900'>**messages**</font>: 接收到新消息触发事件

- 返回值类型 : <font color ='#808000'>**Node**</font>
- 返回值描述: {"chatType":"消息类型,包括Chat(单聊),GroupChat(群聊)","messageId": "消息的唯一标识符","conversationId": "所属会话的唯一标识符","from": "发送方","to": "接收方","timestamp": "时间戳","body":{"type":"消息体类型，包括，0.Text(文本),1.Image(图片),2.Location(位置),3.Voice(语音),4.Video(视频),5.File(文件)","text（type为0）": "消息内容","remotePath（type为1）": "大图remote路径","localPath（type为1）": "大图local路径","thumbnailRemotePath（type为1）": "小图remote路径","thumbnailLocalPath（type为1）": "小图local路径","latitude（type为2）": "纬度","longitude（type为2）": "经度","address（type为2）": "地址","remotePath（type为3）": "音频remote路径","localPath（type为3）": "音频local路径","fileLength（type为3）": "音频文件大小","duration（type为3）":"音频的时间长度","remotePath（type为4）": "视频remote路径","localPath（type为4）": "视频local路径","thumbnailRemotePath（type为4）": "第一帧缩略图remote路径","thumbnailLocalPath（type为4）": "第一帧缩略图local路径","fileLength（type为4）": "视频文件大小","duration（type为4）": "视频的时间长度","remotePath（type为5）": "文件remote路径","localPath（type为5）": "文件local路径","fileLength（type为5）": "文件文件大小"}}
- 说明: 接收到新消息触发事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**joinGroup**</font>: 收到进群申请

- 返回值类型 : <font color ='#808000'>**Node**</font>
- 返回值描述: 只有用户申请进JoinNeedApproval公开群，Owner收到进群申请，才会触发该事件，{"groupId":"群组id","groupName":"群组名称","applicant":"申请者","reason":"申请者的附属信息"}
- 说明: 收到进群申请
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**leavedGroup**</font>: 用户被动离开群组，群组被Owner解散或者用户被从群组中移除

- 返回值类型 : <font color ='#808000'>**Node**</font>
- 返回值描述: {"groupId":"群组id","groupName":"群组名称","reason":"踢出原因"}
- 说明: 用户被动离开群组，群组被Owner解散或者用户被从群组中移除
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**groupInvitation**</font>: 接收到邀请进群的申请

- 返回值类型 : <font color ='#808000'>**Node**</font>
- 返回值描述: {"groupId":"群组id","inviter":"邀请者","reason":"邀请者的附属信息"}
- 说明: 接收到邀请进群的申请
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**autoLogin**</font>: 若登录时设置自动登录，则下次进入自动登录时触发

- 返回值类型 : <font color ='#808000'>****</font>
- 返回值描述: 
- 说明: 若登录时设置自动登录，则下次进入自动登录时触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**connectionStateChanged**</font>: 连接服务器的状态变化时会接收到该回调，有以下几种情况，会触发该事件：1. 登录成功后，手机无法上网时；2. 登录成功后，网络状态变化时

- 返回值类型 : <font color ='#808000'>**Node**</font>
- 返回值描述: {state:0 登录成功后，手机无法上网时 | 1 登录成功后，网络状态变化时}
- 说明: 连接服务器的状态变化时会接收到该回调，有以下几种情况，会触发该事件：1. 登录成功后，手机无法上网时；2. 登录成功后，网络状态变化时
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**logout**</font>: 被动退出登录：1. 正在登录的账号在另一台设备上登录；2. 正在登录的账号被从服务器端删除。主动调用退出方法不会触发

- 返回值类型 : <font color ='#808000'>**Node**</font>
- 返回值描述: {state:0 显示帐号已经被移除 | 1 显示帐号在其他设备登陆}
- 说明: 被动退出登录：1. 正在登录的账号在另一台设备上登录；2. 正在登录的账号被从服务器端删除。主动调用退出方法不会触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**invitationAccpted**</font>: 进群邀请被接受

- 返回值类型 : <font color ='#808000'>**Node**</font>
- 返回值描述: {groupId:当前邀请群组,invitee:被邀请人,reason:接受原因}
- 说明: 进群邀请被接受
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**invitationDeclined**</font>: 进群邀请被拒绝

- 返回值类型 : <font color ='#808000'>**Node**</font>
- 返回值描述: {groupId:当前邀请群组,invitee:被邀请人,reason:拒绝原因}
- 说明: 进群邀请被拒绝
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**revoke**</font>: 对方撤回消息

- 返回值类型 : <font color ='#808000'>****</font>
- 返回值描述: 对方撤回消息时会触发该事件
- 说明: 对方撤回消息
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


