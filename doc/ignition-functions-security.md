# Ignition 8.1 - system.security 函數文檔

﻿# Ignition 8.1 - 函數文檔（PATTERN 規範）

> 根據 FUNCTION_PATTERN 爬蟲生成
> 生成時間: 2026年04月19日 00:56:44
> 總計函式數: 434

## 📑 目錄

---

1. [system.security.getRoles](#systemsecuritygetroles) - This function is used inPython Scripting. Finds the roles that the currently logged in user has, returns them as a Python tuple of strings. This scripting function has noClient Permissionrestrictions.
2. [system.security.getUserRoles](#systemsecuritygetuserroles) - This function is used inPython Scripting. Fetches the roles for a user from the Gateway. This may not be the currently logged in user. Requires the password for that user. If the authentication profile name is omitted, then the current project's default authentication profile is used. This scripting function has noClient Permissionrestrictions.
3. [system.security.getUsername](#systemsecuritygetusername) - This function is used inPython Scripting. Returns the currently logged-in username. This scripting function has noClient Permissionrestrictions.
4. [system.security.isScreenLocked](#systemsecurityisscreenlocked) - This function is used inPython Scripting. Returns whether or not the screen is currently locked. This scripting function has noClient Permissionrestrictions.
5. [system.security.lockScreen](#systemsecuritylockscreen) - This function is used inPython Scripting. Used to put a running client in lock-screen mode. The screen can be unlocked by the user with the proper credentials, or by scripting via thesystem.security.unlockScreen()function. This scripting function has noClient Permissionrestrictions.
6. [system.security.logout](#systemsecuritylogout) - This function is used inPython Scripting. Logs out of the Client for the current user and brings the Client to the login screen. This scripting function has noClient Permissionrestrictions.
7. [system.security.switchUser](#systemsecurityswitchuser) - This function is used inPython Scripting. Attempts to switch the current user on the fly. If the given username and password fail, this function will return false. If it succeeds, then all currently opened windows are closed, the user is switched, and windows are then re-opened in the states that they were in. If an event object is passed to this function, the parent window of the event object will not be re-opened after a successful user switch. This is to support the common case of having a sw
8. [system.security.unlockScreen](#systemsecurityunlockscreen) - This function is used inPython Scripting. Unlocks the client, if it is currently in lock-screen mode. This scripting function has noClient Permissionrestrictions.
9. [system.security.validateUser](#systemsecurityvalidateuser) - This function is used inPython Scripting. Tests credentials (username and password) against an authentication profile. Returns a boolean based upon whether or not the authentication profile accepts the credentials. If the authentication profile name is omitted, then the current project's default authentication profile is used. This scripting function has noClient Permissionrestrictions.

---

# system.security.getRoles

**版本：** 8.1
**型別：** Scripting
**分類：** Security

## 詳述

This function is used inPython Scripting. Finds the roles that the currently logged in user has, returns them as a Python tuple of strings. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.security.getRoles()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.security.getRoles()
```

### Example 2

```python
# This would run on a button to prevent certain users from opening a window

if "Supervisor" in system.security.getRoles():
   system.nav.openWindow("ManagementOnly")
else:
   system.gui.errorBox("You don't have sufficient privileges to continue")
```

### Example 3

```python
# This would run on a button to prevent certain users from opening a window

if "Supervisor" in system.security.getRoles():
   system.nav.openWindow("ManagementOnly")
else:
   system.gui.errorBox("You don't have sufficient privileges to continue")
```


---



---

# system.security.getUserRoles

**版本：** 8.1
**型別：** Scripting
**分類：** Security

## 詳述

This function is used inPython Scripting. Fetches the roles for a user from the Gateway. This may not be the currently logged in user. Requires the password for that user. If the authentication profile name is omitted, then the current project's default authentication profile is used. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.security.getUserRoles(username, password, [authProfile], [timeout])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| username | String | The username to fetch roles for |
| password | String | The password for the user |
| authProfile | String | The name of the authentication profile to run against. Optional. Leaving this out will use the project's default profile. [optional] |
| timeout | Integer | Timeout for client-to-gateway communication. Default is 60,000ms.  [optional] |
| username | String | The username to fetch roles for. |
| password | String | The password for the user. |
| authProfile | String | The name of the authentication profile to run against. Leaving this out will use the project's default profile. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.security.getUserRoles(username, password, [authProfile], [timeout])
```


---



---

# system.security.getUsername

**版本：** 8.1
**型別：** Scripting
**分類：** Security

## 詳述

This function is used inPython Scripting. Returns the currently logged-in username. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.security.getUsername()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.security.getUsername()
```

### Example 2

```python
# This code would run on a startup script and does special logic based upon who was logging in
name = system.security.getUsername()
if name == 'Bob':
   system.nav.openWindow("BobsHomepage")
else:
   system.nav.openWindow("NormalHomepage")
```

### Example 3

```python
# This code would run on a startup script and does special logic based upon who was logging in
name = system.security.getUsername()
if name == 'Bob':
   system.nav.openWindow("BobsHomepage")
else:
   system.nav.openWindow("NormalHomepage")
```


---



---

# system.security.isScreenLocked

**版本：** 8.1
**型別：** Scripting
**分類：** Security

## 詳述

This function is used inPython Scripting. Returns whether or not the screen is currently locked. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.security.isScreenLocked()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.security.isScreenLocked()
```

### Example 2

```python
# This would run in a timer script to lock the screen after 15 seconds of inactivity, and then log the user out after 30 seconds of inactivity.

if system.util.getInactivitySeconds() > 15 and not system.security.isScreenLocked():
   system.security.lockScreen()
elif system.util.getInactivitySeconds() > 30:
   system.security.logout()
```

### Example 3

```python
# This would run in a timer script to lock the screen after 15 seconds of inactivity, and then log the user out after 30 seconds of inactivity.

if system.util.getInactivitySeconds() > 15 and not system.security.isScreenLocked():
   system.security.lockScreen()
elif system.util.getInactivitySeconds() > 30:
   system.security.logout()
```


---



---

# system.security.lockScreen

**版本：** 8.1
**型別：** Scripting
**分類：** Security

## 詳述

This function is used inPython Scripting. Used to put a running client in lock-screen mode. The screen can be unlocked by the user with the proper credentials, or by scripting via thesystem.security.unlockScreen()function. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.security.lockScreen([obscure])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| obscure | Boolean | If true(1), the locked screen will be opaque, otherwise it will be partially visible. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.security.lockScreen([obscure])
```

### Example 3

```python
# This would run in a timer script to lock the screen after 15 seconds of inactivity, and then log the user out after 30 seconds of inactivity.

if system.util.getInactivitySeconds() > 15 and not system.security.isScreenLocked():
   system.security.lockScreen()
elif system.util.getInactivitySeconds() > 30:
   system.security.logout()
```


---



---

# system.security.logout

**版本：** 8.1
**型別：** Scripting
**分類：** Security

## 詳述

This function is used inPython Scripting. Logs out of the Client for the current user and brings the Client to the login screen. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.security.logout()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.security.logout()
```

### Example 2

```python
# This would run in a timer script to log the user out after 30 seconds of inactivity.
if system.util.getInactivitySeconds() > 30:
   system.security.logout()
```

### Example 3

```python
# This would run in a timer script to log the user out after 30 seconds of inactivity.
if system.util.getInactivitySeconds() > 30:
   system.security.logout()
```


---



---

# system.security.switchUser

**版本：** 8.1
**型別：** Scripting
**分類：** Security

## 詳述

This function is used inPython Scripting. Attempts to switch the current user on the fly. If the given username and password fail, this function will return false. If it succeeds, then all currently opened windows are closed, the user is switched, and windows are then re-opened in the states that they were in. If an event object is passed to this function, the parent window of the event object will not be re-opened after a successful user switch. This is to support the common case of having a sw

## 語法

```python
system.security.switchUser(username, password, [event], [hideError])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| username | String | The username to try and switch to. |
| password | String | The password to authenticate with. |
| event | EventObject | If specified, the enclosing window for this event's component will be closed in the switch user process. Refer to the list ofEventobjects. [optional] |
| hideError | Boolean | If true (1), no error will be shown if the switch user function fails. Default is False. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.security.switchUser(username, password, [event], [hideError])
```


---



---

# system.security.unlockScreen

**版本：** 8.1
**型別：** Scripting
**分類：** Security

## 詳述

This function is used inPython Scripting. Unlocks the client, if it is currently in lock-screen mode. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.security.unlockScreen()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.security.unlockScreen()
```

### Example 2

```python
# This code would go in a global script to automatically unlock the screen on a specific computer

comp = system.net.getHostName()
if comp == 'Line 1':
   system.security.unlockScreen()
```

### Example 3

```python
# This code would go in a global script to automatically unlock the screen on a specific computer

comp = system.net.getHostName()
if comp == 'Line 1':
   system.security.unlockScreen()
```


---



---

# system.security.validateUser

**版本：** 8.1
**型別：** Scripting
**分類：** Security

## 詳述

This function is used inPython Scripting. Tests credentials (username and password) against an authentication profile. Returns a boolean based upon whether or not the authentication profile accepts the credentials. If the authentication profile name is omitted, then the current project's default authentication profile is used. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.security.validateUser(username, password, [authProfile], [timeout])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| username | String | The username to validate |
| password | String | The password for the user |
| authProfile | String | The name of the authentication profile to run against. Leaving this out will use the project's default profile. [optional] |
| timeout | Integer | Timeout for Client-to-Gateway communication. Default is 60,000ms. [optional] |
| username | String | The username to validate. |
| password | String | The password for the user. |
| authProfile | String | The name of the authentication profile to run against. Optional. Leaving this out will use the project's default profile. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.security.validateUser(username, password, [authProfile], [timeout])
```


---

