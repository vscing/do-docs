---
title: M3506_MobileRTC 组件
---

### M3506_MobileRTC 组件

 支持平台: iOS7.0,Android
 集成了zoom的MobileRTC的视频会议组件

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <font color ='#0092db'>**getMeetingState**</font>: 获取会议状态

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: A MobileRTCMeetingState to tell client the meeting state currently. 
    //Idle
    MobileRTCMeetingState_Idle        = 0,
    //Connecting
    MobileRTCMeetingState_Connecting  = 1,
    //In Meeting
    MobileRTCMeetingState_InMeeting   = 2,
- 说明: This method is used to tell the client whether the meeting is ongoing or not.
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**isMeetingHost**</font>: 是否为会议主持人

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: Return true, the current user is the host of the meeting.
- 说明: This method is used to tell whether the current user is the host of the meeting or not.
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**isMeetingLocked**</font>: 会议是否被锁定

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: Return true, the meeting has been locked by host.
- 说明: This method is used to tell whether the meeting is locked by host or not.
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**isNoMeetingAudio**</font>: 音频不存在

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: Return true if the meeting audio does not exist.
- 说明: This method is used to tell the client whether the meeting audio existed or not.
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**joinMeetingWithDictionary**</font>: 加入会议

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **dict** |<font color ='#808000'>**object**</font> | 是 | |The dictionary which contains the meeting parameters.
- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: A MobileRTCMeetError to tell client whether the meeting started or not.    
    //Success
    MobileRTCMeetError_Success                    = 0,
    //Incorrect meeting number
    MobileRTCMeetError_IncorrectMeetingNumber     = 1,
    //Meeting Timeout
    MobileRTCMeetError_MeetingTimeout             = 2,
    //Network Unavailable
    MobileRTCMeetError_NetworkUnavailable         = 3,
    //Client Version Incompatible
    MobileRTCMeetError_MeetingClientIncompatible  = 4,
    //User is Full
    MobileRTCMeetError_UserFull                   = 5,
    //Meeting is over
    MobileRTCMeetError_MeetingOver                = 6,
    //Meeting does not exist
    MobileRTCMeetError_MeetingNotExist            = 7,
    //Meeting has been locked
    MobileRTCMeetError_MeetingLocked              = 8,
    //Meeting Restricted
    MobileRTCMeetError_MeetingRestricted          = 9,
    //JBH Meeting Restricted
    MobileRTCMeetError_MeetingJBHRestricted       = 10,
    
    //Invalid Arguments
    MobileRTCMeetError_InvalidArguments           = 99,
    //Invalid Arguments
    MobileRTCMeetError_InvalidUserType            = 100,
    //Already In another ongoing meeting
    MobileRTCMeetError_InAnotherMeeting           = 101,
    //Unknown error
    MobileRTCMeetError_Unknown                    = 102,
- 说明: This method is used to join a meeting with parameters in a dictionary.
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**joinMeetingWithMeetingNoAndDisplayName**</font>: 加入会议

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **meetingNo** |<font color ='#808000'>**string**</font> | 是 | |会议id
  **displayName** |<font color ='#808000'>**string**</font> | 是 | |显示名字
- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: return A MobileRTCMeetError to tell client whether can join the meeting or not.、
typedef enum {
    //Success
    MobileRTCMeetError_Success                    = 0,
    //Incorrect meeting number
    MobileRTCMeetError_IncorrectMeetingNumber     = 1,
    //Meeting Timeout
    MobileRTCMeetError_MeetingTimeout             = 2,
    //Network Unavailable
    MobileRTCMeetError_NetworkUnavailable         = 3,
    //Client Version Incompatible
    MobileRTCMeetError_MeetingClientIncompatible  = 4,
    //User is Full
    MobileRTCMeetError_UserFull                   = 5,
    //Meeting is over
    MobileRTCMeetError_MeetingOver                = 6,
    //Meeting does not exist
    MobileRTCMeetError_MeetingNotExist            = 7,
    //Meeting has been locked
    MobileRTCMeetError_MeetingLocked              = 8,
    //Meeting Restricted
    MobileRTCMeetError_MeetingRestricted          = 9,
    //JBH Meeting Restricted
    MobileRTCMeetError_MeetingJBHRestricted       = 10,
    
    //Invalid Arguments
    MobileRTCMeetError_InvalidArguments           = 99,
    //Invalid Arguments
    MobileRTCMeetError_InvalidUserType            = 100,
    //Already In another ongoing meeting
    MobileRTCMeetError_InAnotherMeeting           = 101,
    //Unknown error
    MobileRTCMeetError_Unknown                    = 102,
    
}MobileRTCMeetError;
- 说明: 使用会议id和显示的名字加入会议
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**leaveMeetingWithCmd**</font>: 离开会议

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **cmd** |<font color ='#808000'>**number**</font> | 是 | |Leave meeting by the command type.
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: This method is used to end/leave an ongoing meeting.
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**loginWithEmailAndPassword**</font>: 使用邮箱密码登陆

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **email** |<font color ='#808000'>**string**</font> | 是 | |login email account.
  **password** |<font color ='#808000'>**string**</font> | 是 | |login password.
- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: return true, if user can login with work email.
- 说明: Designated for login MobileRTC with work email account.（暂未实现）
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**logoutRTC**</font>: 登出

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: return true, if user can logout.
- 说明: Designated for logout MobileRTC.（暂未实现）
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**pauseMeetingAudio**</font>: 暂停／恢复会议音频

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **pause** |<font color ='#808000'>**boolean**</font> | 是 | |if true to pause audio; if false to resume audio.
- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: 操作是否成功
- 说明: This method is used to pause/resume audio in the meeting.
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <font color ='#0092db'>**startMeetingWithDictionary**</font>: 开始会议

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **dict** |<font color ='#808000'>**object**</font> | 是 | |The dictionary which contains the meeting parameters.
- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: //Success
MobileRTCMeetError_Success                    = 0,
//Incorrect meeting number
MobileRTCMeetError_IncorrectMeetingNumber     = 1,
//Meeting Timeout
MobileRTCMeetError_MeetingTimeout             = 2,
//Network Unavailable
MobileRTCMeetError_NetworkUnavailable         = 3,
//Client Version Incompatible
MobileRTCMeetError_MeetingClientIncompatible  = 4,
//User is Full
MobileRTCMeetError_UserFull                   = 5,
//Meeting is over
MobileRTCMeetError_MeetingOver                = 6,
//Meeting does not exist
MobileRTCMeetError_MeetingNotExist            = 7,
//Meeting has been locked
MobileRTCMeetError_MeetingLocked              = 8,
//Meeting Restricted
MobileRTCMeetError_MeetingRestricted          = 9,
//JBH Meeting Restricted
MobileRTCMeetError_MeetingJBHRestricted       = 10,
    
//Invalid Arguments
MobileRTCMeetError_InvalidArguments           = 99,
//Invalid Arguments
MobileRTCMeetError_InvalidUserType            = 100,
//Already In another ongoing meeting
MobileRTCMeetError_InAnotherMeeting           = 101,
//Unknown error
MobileRTCMeetError_Unknown                    = 102,
- 说明: This method is used to start a meeting with parameters in a dictionary.
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <font color ='#e96900'>**MeetingError**</font>: Designated for Meeting Error message.

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: error, internal error code.
message, the message for meeting error.
- 说明: Designated for Meeting Error message.
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**MeetingReturn**</font>: Designated for Meeting Response.

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: error, tell client related to this meeting event.
    //Success
    MobileRTCMeetError_Success                    = 0,
    //Incorrect meeting number
    MobileRTCMeetError_IncorrectMeetingNumber     = 1,
    //Meeting Timeout
    MobileRTCMeetError_MeetingTimeout             = 2,
    //Network Unavailable
    MobileRTCMeetError_NetworkUnavailable         = 3,
    //Client Version Incompatible
    MobileRTCMeetError_MeetingClientIncompatible  = 4,
    //User is Full
    MobileRTCMeetError_UserFull                   = 5,
    //Meeting is over
    MobileRTCMeetError_MeetingOver                = 6,
    //Meeting does not exist
    MobileRTCMeetError_MeetingNotExist            = 7,
    //Meeting has been locked
    MobileRTCMeetError_MeetingLocked              = 8,
    //Meeting Restricted
    MobileRTCMeetError_MeetingRestricted          = 9,
    //JBH Meeting Restricted
    MobileRTCMeetError_MeetingJBHRestricted       = 10,
    
    //Invalid Arguments
    MobileRTCMeetError_InvalidArguments           = 99,
    //Invalid Arguments
    MobileRTCMeetError_InvalidUserType            = 100,
    //Already In another ongoing meeting
    MobileRTCMeetError_InAnotherMeeting           = 101,
    //Unknown error
    MobileRTCMeetError_Unknown                    = 102,
internalError, internal error code
- 说明: Designated for Meeting Response.
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**MeetingStateChange**</font>: Designated for Meeting State Change.

- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: tell client meeting state chagne.
     //Idle
    MobileRTCMeetingState_Idle        = 0,
    //Connecting
    MobileRTCMeetingState_Connecting  = 1,
    //In Meeting
    MobileRTCMeetingState_InMeeting   = 2,
- 说明: Designated for Meeting State Change.
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**MobileRTCAuthReturn**</font>: Designated for MobileRTC Auth response.

- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: //Auth Success 
    MobileRTCAuthError_Success = 0,
    //Key or Secret is empty
    MobileRTCAuthError_KeyOrSecretEmpty = 1,
    //Key or Secret is wrong
    MobileRTCAuthError_KeyOrSecretWrong = 2,
    //Client Account does not support
    MobileRTCAuthError_AccountNotSupport = 3,
    //Client account does not enable SDK
    MobileRTCAuthError_AccountNotEnableSDK = 4,
    //Auth Unknown error
    MobileRTCAuthError_Unknown = 5,
- 说明: Designated for MobileRTC Auth response.
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**MobileRTCLoginReturn**</font>: Designated for MobileRTC Login response.

- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: returnValue tell user when the login state changed.
- 说明: Designated for MobileRTC Login response.
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**MobileRTCLogoutReturn**</font>: Designated for MobileRTC Logout response.

- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: returnValue tell user whether the logout success or not.
- 说明: Designated for MobileRTC Logout response.
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <font color ='#e96900'>**onMeetingReady**</font>: Designated for Meeting has been ready.

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 
- 说明: Designated for Meeting has been ready.
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


