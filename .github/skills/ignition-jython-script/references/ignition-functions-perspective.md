# Ignition 8.1 - system.perspective 函數文檔


## 📑 目錄

---

1. [system.perspective.alterDock](#systemperspectivealterdock) - This function is used inPython Scripting. Changes configuration of a specified dock on a Perspective page.
2. [system.perspective.alterLogging](#systemperspectivealterlogging) - This function is used inPython Scripting. Changes Perspective Session logging attributes and levels. All parameters are optional, with the caveat that at least one of them needs to be used. For thesystem.perspective.alterLoggingfunction to work, the following line needs to be added to theignition.conffile, and the Gateway restarted.  "X" is the next number in the Java Additional Parameters list in theignition.conffile.Warning, this will open potential security holes in the Gateway, and is not ad
3. [system.perspective.authenticationChallenge](#systemperspectiveauthenticationchallenge) - This function is used inPython Scripting. Triggers anauthentication challengeaction.
4. [system.perspective.closeDock](#systemperspectiveclosedock) - This function is used inPython Scripting. Closes a docked view. This function acceptskeyword arguments.
5. [system.perspective.closePage](#systemperspectiveclosepage) - This function is used inPython Scripting. Closes the page with the given page id or the current page if no page id is provided. If a message is provided, it is displayed on the page when the page closes. Otherwise the default message (set in theProject properties) is displayed. system.perspective.closePage([message], [sessionId], [pageID])
6. [system.perspective.closePopup](#systemperspectiveclosepopup) - This function is used inPython Scripting. Closes a popup view. This function acceptskeyword arguments.
7. [system.perspective.closeSession](#systemperspectiveclosesession) - This function is used inPython Scripting. Closes the Perspective Session with the given sessionID or the current Session if no ID is provided. If a message is provided, it is displayed on the page when the Session closes. Otherwise the default message (set in theProject properties) is displayed. In the Perspective App, the user is returned to the launch screen.
8. [system.perspective.download](#systemperspectivedownload) - This function is used inPython Scripting. Downloads data from the Gateway to a device running a Session. When calling from the Gateway scope, the call must include a sessionId.
9. [system.perspective.getProjectInfo](#systemperspectivegetprojectinfo) - This function is used inPython Scripting. Returns a dictionary of meta data from a Perspective Project. Exact fields are as follows:
10. [system.perspective.getSessionInfo](#systemperspectivegetsessioninfo) - This function is used inPython Scripting. Returns information about one or more Perspective Sessions. The information returned by this function is a combination of information available on thePerspective Sessions statuspage on the Gateway, and some Session props (id and userAgent). Exact fields are as follows: This function acceptskeyword arguments.
11. [system.perspective.isAuthorized](#systemperspectiveisauthorized) - This function is used inPython Scripting. Checks if the user in the current Session is authorized against a target collection of security levels. system.perspective.isAuthorized(isAllOf, securityLevels, [sessionID])
12. [system.perspective.login](#systemperspectivelogin) - This function is used inPython Scripting. Triggers a login event that will allow the user to log in with the project's configured Identity Provider (IdP). For this function to work, an IdP must be set in PerspectiveProject properties. This is particularly useful when you want it to be possible to start a session without authentication and sign in to access certain restricted features. Note that calling this function after a user is already logged in willnotlog out the previous user.
13. [system.perspective.logout](#systemperspectivelogout) - This function is used inPython Scripting. Triggers a logout event, which will log the user out. For this function to work, an Identity Provider (IdP) must be set in thePerspective Project properties. Be advised that this function should not be used in the same script, or in the same triggering event assystem.perspective.login. Logging in and Logging out should always be triggered by separate events.
14. [system.perspective.navigate](#systemperspectivenavigate) - This function is used inPython Scripting. Navigate the session to a specified view or mounted page. The function can be used in three different ways, depending on which parameter is specified:
15. [system.perspective.navigateBack](#systemperspectivenavigateback) - This function is used inPython Scripting. Navigate the session to a specified view or mounted page. This is similar to a browser's "back" function.
16. [system.perspective.navigateForward](#systemperspectivenavigateforward) - This function is used inPython Scripting. Navigate the session to a specified view or mounted page. This is similar to a browser's "forward" function.
17. [system.perspective.openDock](#systemperspectiveopendock) - This function is used inPython Scripting. Opens a docked View. Requires the preconfigured dock ID for the view. system.perspective.openDock(id, [sessionId], [pageId])
18. [system.perspective.openPopup](#systemperspectiveopenpopup) - This function is used inPython Scripting. Open apopup viewover the given page. system.perspective.openPopup(id, view, [params], [title], [position], [showCloseIcon], [draggable], [resizable], [modal], [overlayDismiss], [sessionId], [pageId], [viewportBound])
19. [system.perspective.print](#systemperspectiveprint) - This function is used inPython Scripting. Prints the supplied message to the local console (or the gateway logs, as appropriate) - by default, this means the Output Console when in the Designer, and the browser's console when in a live session. system.perspective.print([message], [sessionId], [pageId], [destination])
20. [system.perspective.refresh](#systemperspectiverefresh) - This function is used inPython Scripting. Triggers a refresh of the page. This method should not be confused with therefreshBindingcomponent method, which automatically fires a binding on a Perspective component property.
21. [system.perspective.sendMessage](#systemperspectivesendmessage) - This function is used inPython Scripting. Send a message to acomponent message handlerwithin the same session. This function cannot interact with Session Message Handlers configured in Session Events, even if thescopeof session is specified. Invoked Message Handlersexecute asynchronouslyto the calling script.
22. [system.perspective.setTheme](#systemperspectivesettheme) - This function is used inPython Scripting. Changes the theme in a page to the specified theme. Note that this function only changes the theme for a single page, not the entire session. To change the theme for a session, write directly to thesession.themeproperty instead.
23. [system.perspective.toggleDock](#systemperspectivetoggledock) - This function is used inPython Scripting. Toggles a docked view. system.perspective.toggleDock(id, [sessionId], [pageId])
24. [system.perspective.togglePopup](#systemperspectivetogglepopup) - This function is used inPython Scripting. Toggles apopup view. Will open up the popup if it has not been opened yet. Otherwise, it will close the currently opened popup. system.perspective.togglePopup(id, view, [params], [title], [position], [showCloseIcon], [draggable], [resizable], [modal], [overlayDismiss], [sessionId], [pageId], [viewportBound])
25. [system.perspective.vibrateDevice](#systemperspectivevibratedevice) - This function is used inPython Scripting. When called from thePerspective App, will cause the device to vibrate for the specified number of milliseconds. iOS vibration duration is fixed. This function will cause an iOS device to vibrate for its default duration, 0.4 seconds (400 milliseconds).
26. [system.perspective.workstation](#systemperspectiveworkstation) - The following functions offer various ways to interact with Perspective Workstation from a Python script. Note that the functions here only work when called from a session running in Perspective Workstation. When called from a session running in Workstation, this function will close Workstation. Attempts to put Workstation into Kiosk mode.
27. [system.perspective.workstation.exit](#systemperspectiveworkstationexit) - This function is used inPython Scripting. When called from a session running in Workstation, this function will close Workstation. system.perspective.workstation.exit()
28. [system.perspective.workstation.toKiosk](#systemperspectiveworkstationtokiosk) - This function is used inPython Scripting. When called from a session running inPerspective Workstation, attempts to put Workstation into Kiosk mode. system.perspective.workstation.toKiosk()
29. [system.perspective.workstation.toWindowed](#systemperspectiveworkstationtowindowed) - This function is used inPython Scripting. When called from a Session running inPerspective Workstation, attempts to put Workstation into windowed mode. system.perspective.workstation.toWindowed()

---

# system.perspective.alterDock

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Changes configuration of a specified dock on a Perspective page.

## 語法

```python
system.perspective.alterDock(dockId, [config], [sessionId], [pageId])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| dockId | String | The unique identifier of the dock to be modified. If no dock with the specified ID exists on the current page, a warning will be logged to the console. |
| config | PyDictionary | A PyDictionary containing the dock configuration to be applied when the script is run. If omitted, the dock configuration remains unchanged. [optional]The following properties can included in theconfigobject:view: The view to be displayed in the dock.viewParams: A dictionary of name and value pairs to be passed as parameters to the view.display: The display state of the dock. Accepted values are:visibleonDemandautoresizable: The resizable status of the dock.modal: The modal status of the dock.content: How the dock should interact with the main content. Accepted values are:pushcoverautosize: The width or height of the dock, depending on orientation.autoBreakpoint: The minimum page width at which a dock with "display = auto" remains visible. If the session width is smaller than this value, the dock is hidden and can be displayed on demand.anchor: Determines whether the docked view remains visible while scrolling. Only available for North-docked views. Accepted values are:fixedscrollablehandle: Controls the visibility of a handle that allows users to expand or collapse the dock. Accepted values are:showhideautoHidehandleIcon: The path to an icon used to represent the dock when it is hidden. |
| sessionId | String | The ID of the session in which the dock modification is applied. If omitted, the modification applies to the current session. [optional] |
| pageId | String | The ID of the page where the dock is located. If omitted, the modification applies to the current page. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.alterDock(dockId, [config], [sessionId], [pageId])
```


---



---

# system.perspective.alterLogging

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Changes Perspective Session logging attributes and levels. All parameters are optional, with the caveat that at least one of them needs to be used. For thesystem.perspective.alterLoggingfunction to work, the following line needs to be added to theignition.conffile, and the Gateway restarted.  "X" is the next number in the Java Additional Parameters list in theignition.conffile.Warning, this will open potential security holes in the Gateway, and is not ad

## 語法

```python
system.perspective.alterLogging([remoteLoggingEnabled], [level], [remoteLoggingLevel], [sessionId], [pageId])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| remoteLoggingEnabled | Boolean | Will enable remote logging if True. Remote logging will send log events from the Session to the Gateway under the perspective.client logger if they meet the remoteLevel logging level requirement. [optional] |
| level | String | The desired Session logging level. Possible values are: all, trace, debug, info, warn, error, fatal, or off. The default is info. [optional] |
| remoteLoggingLevel | String | The desired remote logging level. Possible values are: all, trace, debug, info, warn, error, fatal, off. The default is warn. [optional] |
| sessionId | String | Identifier of the Session to target. If omitted, the current Session will be used automatically. When targeting a different session, then the pageId parameter must be included in the call. [optional] |
| pageId | String | Identifier of the page to target. If omitted, the current Page will be used automatically. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.alterLogging
```

### Example 2

```python
ignition.conf
```

### Example 3

```python
ignition.conf
```


---



---

# system.perspective.authenticationChallenge

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Triggers anauthentication challengeaction.

## 語法

```python
system.perspective.authenticationChallenge([sessionId], [pageId], [idp], [forceAuth], [timeout], [payload], [framing])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| sessionId | String | Identifier of the Session to target. If omitted, the current Session will be used automatically. When targeting a different session, then the pageId parameter must be included in the call. [optional] |
| pageId | String | Identifier of the page to target. If omitted, the current page will be used. [optional] |
| idp | String | The name of the IdP to use for this authentication challenge. If omitted, the Project default IdP will be used. [optional] |
| forceAuth | Boolean | True if Ignition should ask the IdP to re-authenticate the user, even if the user is already signed into the IdP. False if Ignition should not ask the IdP to re-authenticate the user. If the IdP supports this option, the IdP will ask the user to re-enter their credentials, even if the user is already signed into the IdP. If omitted, the default value for this argument will fall back to the value in the Project Properties. [optional] |
| timeout | Integer | The number of minutes the system will wait in between the authentication request and the authentication response before timing out the request. If set to any number <= zero, the request is rejected. If omitted, the default of two minutes will be used as the timeout. [optional] |
| payload | Any | An opaque payload object that may contain any information. This object will be passed to theonAuthenticationChallengeCompletedsession event script. The payload should be a JSON-encodable data structure. [optional] |
| framing | String | A string representing the type of framing that should be used. A value ofselfindicates that the same window should be used. A value ofnewindicates that a new tab should be used. A value ofembeddedindicates that an embedded iframe should be used. If omitted, the default value ofself(same window) is used. [optional]Note:Mobile and Workstation Clients do not supportnewand will fall back toself. Mobile Clients do not supportembeddedand will fall back toself. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.authenticationChallenge([sessionId], [pageId], [idp], [forceAuth], [timeout], [payload], [framing])
```


---



---

# system.perspective.closeDock

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Closes a docked view. This function acceptskeyword arguments.

## 語法

```python
system.perspective.closeDock(id, [sessionId], [pageId])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| id | String | The unique, preconfigured dock ID for the docked view. Is specified when a view is assigned as docked for a particular page (in Page Configuration). |
| sessionId | String | Identifier of the Session to target. If omitted, the current Session will be used automatically. When targeting a different session, then the pageId parameter must be included in the call. [optional] |
| pageId | String | Identifier of the page to target. If omitted, the current page will be used automatically. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.closeDock(id, [sessionId], [pageId])
```


---



---

# system.perspective.closePage

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Closes the page with the given page id or the current page if no page id is provided. If a message is provided, it is displayed on the page when the page closes. Otherwise the default message (set in theProject properties) is displayed. system.perspective.closePage([message], [sessionId], [pageID])

## 語法

```python
system.perspective.closePage([message], [sessionId], [pageID])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| message | String | The message to display when the page closes. If omitted, the default message (set in the Project Properties) is shown. [optional] |
| sessionId | String | Identifier of the Session to target. If omitted, the current Session will be used automatically. When targeting a different Session, the pageId parameter must be included in the call. [optional] |
| pageId | String | Identifier of the page to be closed. If omitted, the current pageId is used. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.closePage([message], [sessionId], [pageID])
```


---



---

# system.perspective.closePopup

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Closes a popup view. This function acceptskeyword arguments.

## 語法

```python
system.perspective.closePopup(id, [sessionId], [pageId])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| id | String | The unique identifier for the popup, given to the popup when first opened. If given an empty string, then the most recently focused popup will be closed. |
| sessionId | String | Identifier of the Session to target. If omitted, the current Session will be used automatically. When targeting a different session, then the pageId parameter must be included in the call. [optional] |
| pageId | String | Identifier of the page to target. If omitted, the current Page will be used automatically. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.closePopup(id, [sessionId], [pageId])
```


---



---

# system.perspective.closeSession

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Closes the Perspective Session with the given sessionID or the current Session if no ID is provided. If a message is provided, it is displayed on the page when the Session closes. Otherwise the default message (set in theProject properties) is displayed. In the Perspective App, the user is returned to the launch screen.

## 語法

```python
system.perspective.closeSession([message], [sessionId])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| message | String | The message to display when the Session closes. If omitted, the default message (set in theProject properties) is shown. [optional] |
| sessionId | String | Identifier of the Session to be closed. If omitted, the current sessionId is used. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.closeSession([message], [sessionId])
```


---



---

# system.perspective.download

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Downloads data from the Gateway to a device running a Session. When calling from the Gateway scope, the call must include a sessionId.

## 語法

```python
system.perspective.download(filename, data,  [contentType], sessionId, [pageId])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| filename | String | Suggested name for the downloaded file. |
| data | String | The data to be downloaded. May be a string, a byte[], or an InputStream. Strings will be written in UTF-8 encoding. |
| contentType | String | Value for the "Content-Type" header, for example: "text/plain; charset=utf-8". [optional] |
| sessionId | String | Identifier of the Session to target. If omitted, the current Session will be used automatically. When targeting a different session, then the pageId parameter must be included in the call. |
| pageId | String | Identifier of the page to target. If omitted, the current page will be used automatically. [optional] |
| filename | String | Suggested name for the downloaded file. |
| data | String | The data to be downloaded. May be a string, a byte[], or an InputStream. Strings will be written in UTF-8 encoding. |
| contentType | String | Value for the "Content-Type" header, for example: "text/plain; charset=utf-8". [optional] |
| sessionId | String | Identifier of the Session to target. If omitted, the current Session will be used automatically. When targeting a different session, then the pageId parameter must be included in the call. [optional] |
| pageId | String | Identifier of the page to target. If omitted, the current page will be used automatically. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.download(filename, data,  [contentType], sessionId, [pageId])
```


---



---

# system.perspective.getProjectInfo

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Returns a dictionary of meta data from a Perspective Project. Exact fields are as follows:

## 語法

```python
system.perspective.getProjectInfo()
```

## 回傳值

**型別：** Object

## 範例

### Example 2

```python
primaryView
```

### Example 3

```python
system.perspective.getProjectInfo()
```


---



---

# system.perspective.getSessionInfo

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Returns information about one or more Perspective Sessions. The information returned by this function is a combination of information available on thePerspective Sessions statuspage on the Gateway, and some Session props (id and userAgent). Exact fields are as follows: This function acceptskeyword arguments.

## 語法

```python
system.perspective.getSessionInfo([usernameFilter], [projectFilter])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| usernameFilter | String | A filter based on logged in user. [optional] |
| projectFilter | String | A filter based on the project name. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.getSessionInfo([usernameFilter], [projectFilter])
```

### Example 2

```python
usernameFilter
```

### Example 3

```python
projectFilter
```


---



---

# system.perspective.isAuthorized

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Checks if the user in the current Session is authorized against a target collection of security levels. system.perspective.isAuthorized(isAllOf, securityLevels, [sessionID])

## 語法

```python
system.perspective.isAuthorized(isAllOf, securityLevels, [sessionID])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| isAllOf | Boolean | True if the current user must have all of the given security levels to be authorized. False if the current user must have at least one of the given security levels to be authorized. |
| securityLevels | List[String] | An array of string paths to a security level node in the form of "Path/To/Node". Each level in the tree is delimited by a forward slash character. The public node is never a part of the path. |
| sessionId | String | New in8.1.3Identifier of the Session to target. If omitted, the current Session will be used automatically. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.isAuthorized(isAllOf, securityLevels, [sessionID])
```

### Example 3

```python
securityLevels
```


---



---

# system.perspective.login

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Triggers a login event that will allow the user to log in with the project's configured Identity Provider (IdP). For this function to work, an IdP must be set in PerspectiveProject properties. This is particularly useful when you want it to be possible to start a session without authentication and sign in to access certain restricted features. Note that calling this function after a user is already logged in willnotlog out the previous user.

## 語法

```python
system.perspective.login([sessionId], [pageId], [forceAuth])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| sessionId | String | Identifier of the Session to target. If omitted, the current Session will be used automatically. When targeting a different session, then the pageId parameter must be included in the call. [optional] |
| pageId | String | Identifier of the Page to target. If omitted, the current Page will be used automatically. [optional] |
| forceAuth | Boolean | Determines if Ignition should ask the IdP to re-authenticate the user, even if the user is already signed into the IdP. If set to true, then the IdP will ask the user to re-enter their credentials. If set to false, then the Gateway will request that the IdP use the last provided credentials for the Session, potentially allowing re-authentication without requiring the user to re-type their credentials. Note that support for this argument is determined by the IdP; the IdP may choose to ignore this request. If this parameter is omitted, then the function will use the re-authentication setting defined underProject properties. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.login([sessionId], [pageId], [forceAuth])
```


---



---

# system.perspective.logout

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Triggers a logout event, which will log the user out. For this function to work, an Identity Provider (IdP) must be set in thePerspective Project properties. Be advised that this function should not be used in the same script, or in the same triggering event assystem.perspective.login. Logging in and Logging out should always be triggered by separate events.

## 語法

```python
system.perspective.logout([sessionId], [pageId], [message])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| sessionId | String | Identifier of the Session to target. If omitted, the current Session will be used automatically. When targeting a different Session, then the pageId parameter must be included in the call. [optional] |
| pageId | String | Identifier of the Page to target. If omitted, the current Page will be used automatically. [optional] |
| message | String | New in8.1.8The message to display when the user logs out of their session. This message is only shown when the project requires authentication. If omitted, the default message (set inProject Properties) is shown. [Optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.logout([sessionId], [pageId], [message])
```


---



---

# system.perspective.navigate

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Navigate the session to a specified view or mounted page. The function can be used in three different ways, depending on which parameter is specified:

## 語法

```python
system.perspective.navigate(page, [url], [view], [params], [sessionId], [pageId], [newTab])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| page | String | The URL of a Perspective page to navigate to. The path can include an optional leading slash: "new-page" and "/new-page" both result cause the session to navigate to the "new-page" page. SeePage URLs. |
| url | String | The URL of a web address to navigate to. If the page or view parameters are specified, then this parameter is ignored. [optional] |
| view | String | If specified, will navigate to a specific view. Navigating to a view with this parameter does not change the address in the web browser. Thus the web browser's back button will not be able to return the user to the previous view. If the page parameter is specified, then this parameter is ignored. [optional] |
| params | Dictionary[String, String] | Used only in conjunction with the view parameter, Dictionary of values to pass to any parameters on the view. [optional] |
| sessionId | String | Identifier of the Session to target. If omitted, the current Session will be used automatically. When targeting a different session, then the pageId parameter must be included in the call. [optional] |
| pageId | String | Identifier of the page to target. If omitted, the current page will be used automatically. [optional] |
| newTab | Boolean | New in8.1.5If True, opens the contents in a new tab. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.navigate(page, [url], [view], [params], [sessionId], [pageId], [newTab])
```


---



---

# system.perspective.navigateBack

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Navigate the session to a specified view or mounted page. This is similar to a browser's "back" function.

## 語法

```python
system.perspective.navigateBack([sessionId], [pageId])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| sessionId | String | Identifier of the Session to target. If omitted, the current Session will be used automatically. [optional] |
| pageId | String | Identifier of the page to target. If omitted, the current page will be used automatically. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.navigateBack([sessionId], [pageId])
```


---



---

# system.perspective.navigateForward

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Navigate the session to a specified view or mounted page. This is similar to a browser's "forward" function.

## 語法

```python
system.perspective.navigateForward([sessionId], [pageId])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| sessionId | String | Identifier of the Session to target. If omitted, the current Session will be used automatically. When targeting a different session, then the pageId parameter must be included in the call. [optional] |
| pageId | String | Identifier of the page to target. If omitted, the current page will be used automatically. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.navigateForward([sessionId], [pageId])
```


---



---

# system.perspective.openDock

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Opens a docked View. Requires the preconfigured dock ID for the view. system.perspective.openDock(id, [sessionId], [pageId])

## 語法

```python
system.perspective.openDock(id, [sessionId], [pageId])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| id | String | The unique, preconfigured dock ID for the docked View. Is specified when a View is assigned as docked for a particular Page (in Page Configuration). |
| sessionId | String | Identifier of the Session to target. If omitted, the current Session will be used automatically. When targeting a different Session, then the pageId parameter must be included in the call. [optional] |
| pageId | String | Identifier of the Page to target. If omitted, the current Page will be used automatically. [optional] |
| params | Dictionary[String, String] | Parameters that can be passed into the docked view. Must match the docked views View Parameters. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.openDock(id, [sessionId], [pageId])
```


---



---

# system.perspective.openPopup

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Open apopup viewover the given page. system.perspective.openPopup(id, view, [params], [title], [position], [showCloseIcon], [draggable], [resizable], [modal], [overlayDismiss], [sessionId], [pageId], [viewportBound])

## 語法

```python
system.perspective.openPopup(id, view, [params], [title], [position], [showCloseIcon], [draggable], [resizable], [modal], [overlayDismiss], [sessionId], [pageId], [viewportBound])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| id | String | A unique popup string. Will be used to close the popup from other popup or script actions. |
| view | String | The path to the View to use in the popup. |
| params | Dictionary[String, Any] | Dictionary of key-value pairs to use as input parameters to the View. [optional] |
| title | String | Text to display in the title bar. Defaults to an empty string. [optional] |
| position | Dictionary[String, Integer] | Dictionary of key-value pairs to use for position. Possible position keys are: left, top, right, bottom, width, height. Defaults to the center of the window. [optional] |
| showCloseIcon | Boolean | Shows the close icon if True. Defaults to True. [optional] |
| draggable | Boolean | Allows the popup to be dragged if True. Defaults to True. [optional] |
| resizable | Boolean | Allows the popup to be resized if True. Defaults to False. [optional] |
| modal | Boolean | Makes the popup modal if True. A modal popup is the only view the user can interact with. Defaults to False. [optional] |
| overlayDismiss | Boolean | Allows the user to dismiss and close a modal popup by clicking outside of it if True. Defaults to False.[optional] |
| sessionId | String | Identifier of the Session to target. If omitted, the current Session will be used automatically. [optional] |
| pageId | String | Identifier of the Page to target. If omitted, the current Page will be used automatically. When targeting a different session, then this parameter must be included in the call. [optional] |
| viewportBound | Boolean | New in8.1.3If True,  popups will be "shifted" to always open within the bounds of the viewport. If the popup would be larger than the viewport, then it will be resized to fit within the bounds. Default is False. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.openPopup(id, view, [params], [title], [position], [showCloseIcon], [draggable], [resizable], [modal], [overlayDismiss], [sessionId], [pageId], [viewportBound])
```


---



---

# system.perspective.print

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Prints the supplied message to the local console (or the gateway logs, as appropriate) - by default, this means the Output Console when in the Designer, and the browser's console when in a live session. system.perspective.print([message], [sessionId], [pageId], [destination])

## 語法

```python
system.perspective.print([message], [sessionId], [pageId], [destination])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| message | String | The print statement that will be displayed on the console. [optional] |
| sessionId | String | Identifier of the Session to target. If omitted, the current Session will be used automatically. When targeting a different session, then the pageId parameter must be included in the call. [optional] |
| pageId | String | Identifier of the page to target. If omitted, the current Page will be used automatically. [optional] |
| destination | String | Where the message should be printed. If specified, must be "client", "gateway", or "all". Default is "client". [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.print([message], [sessionId], [pageId], [destination])
```


---



---

# system.perspective.refresh

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Triggers a refresh of the page. This method should not be confused with therefreshBindingcomponent method, which automatically fires a binding on a Perspective component property.

## 語法

```python
system.perspective.refresh([sessionId], [pageId])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| sessionId | String | Identifier of the Session to target. If omitted, the current Session will be used automatically. When targeting a different session, then the pageId parameter must be included in the call. [optional] |
| pageId | String | Identifier of the page to target. If omitted, the current Page will be used automatically. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.refresh([sessionId], [pageId])
```


---



---

# system.perspective.sendMessage

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Send a message to acomponent message handlerwithin the same session. This function cannot interact with Session Message Handlers configured in Session Events, even if thescopeof session is specified. Invoked Message Handlersexecute asynchronouslyto the calling script.

## 語法

```python
system.perspective.sendMessage(messageType, payload, [scope], [sessionId], [pageId])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| messageType | String | The message type that will be invoked. Message handlers configured within the project are listening for messages of a specific messageType. |
| payload | Dictionary[String, String] | A Python dictionary representing any parameters that will be passed to the message handler. |
| scope | String | The scope that the message should be delivered to. Valid values are "session", "page", or "view". If omitted, "page" will be used. [optional] |
| sessionId | String | Identifier of the Session to target. If omitted, the current Session will be used automatically. When targeting a different session, then the pageId parameter must be included in the call. [optional] |
| pageId | String | Identifier of the page to target. If omitted, the current page will be used. [optional] |

## 回傳值

**型別：** Object


---



---

# system.perspective.setTheme

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Changes the theme in a page to the specified theme. Note that this function only changes the theme for a single page, not the entire session. To change the theme for a session, write directly to thesession.themeproperty instead.

## 語法

```python
system.perspective.setTheme(name, [sessionId], [pageId])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| name | String | The theme name to switch to. Possible values are "dark" or "light". |
| sessionId | String | Identifier of the Session to target. If omitted, the current Session will be used automatically. When targeting a different session, then the pageId parameter must be included in the call. [optional] |
| pageId | String | Identifier of the page to target. If omitted, the current page will be used automatically. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
session.theme
```

### Example 2

```python
system.perspective.setTheme(name, [sessionId], [pageId])
```


---



---

# system.perspective.toggleDock

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Toggles a docked view. system.perspective.toggleDock(id, [sessionId], [pageId])

## 語法

```python
system.perspective.toggleDock(id, [sessionId], [pageId])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| id | String | The unique, preconfigured 'Dock ID' for the docked view. Is specified when a view is assigned as docked for a particular page (in Page Configuration). |
| sessionId | String | Identifier of the Session to target. If omitted, the current Session will be used automatically. When targeting a different session, then the pageId parameter must be included in the call. [optional] |
| pageId | String | Identifier of the Page to target. If omitted, the current Page will be used automatically. [optional] |
| params | Dictionary[String, String] | Parameters that can be passed into the docked view. Must match the docked views View Parameters. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.toggleDock(id, [sessionId], [pageId])
```


---



---

# system.perspective.togglePopup

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Toggles apopup view. Will open up the popup if it has not been opened yet. Otherwise, it will close the currently opened popup. system.perspective.togglePopup(id, view, [params], [title], [position], [showCloseIcon], [draggable], [resizable], [modal], [overlayDismiss], [sessionId], [pageId], [viewportBound])

## 語法

```python
system.perspective.togglePopup(id, view, [params], [title], [position], [showCloseIcon], [draggable], [resizable], [modal], [overlayDismiss], [sessionId], [pageId], [viewportBound])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| id | String | A unique popup string. Will be used to close the popup from other popup or script actions. |
| view | String | The path to the view to use in the popup. |
| params- Dictionary of key-value pairs to us as input parameters to the View. [optional] | Dictionary[String, Any] |  |
| title | String | Text to display in the title bar. Defaults to an empty string. [optional] |
| position | Dictionary[String, Integer] | Dictionary of key-value pairs to use for position. Possible position keys are: left, top, right, bottom, width, height. Defaults to the center of the window. [optional] |
| showCloseIcon | Boolean | Will show the close icon if True. Defaults to True. [optional] |
| draggable | Boolean | Will allow the popup to be dragged if True. Defaults to True. [optional] |
| resizable | Boolean | Will allow the popup to be resized if True. Defaults to False. [optional] |
| modal | Boolean | Will make the popup modal if True. A modal popup is the only view the user can interact with. Defaults to False. [optional] |
| overlayDismiss | Boolean | Will allow the user to dismiss and close a modal popup by clicking outside of it if True. Defaults to False. [optional] |
| sessionId | String | Identifier of the Session to target. If omitted, the current Session will be used automatically. When targeting a different session, then the pageId parameter must be included in the call. [optional] |
| pageId | String | Identifier of the page to target. If omitted, the current Page will be used automatically. [optional] |
| viewportBound | Boolean | New in8.1.3If True,  popups will be "shifted" to open within the bounds of the viewport. If the popup would be larger than the viewport, then it will be resized to fit within the bounds. Default is False. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.togglePopup(id, view, [params], [title], [position], [showCloseIcon], [draggable], [resizable], [modal], [overlayDismiss], [sessionId], [pageId], [viewportBound])
```


---



---

# system.perspective.vibrateDevice

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. When called from thePerspective App, will cause the device to vibrate for the specified number of milliseconds. iOS vibration duration is fixed. This function will cause an iOS device to vibrate for its default duration, 0.4 seconds (400 milliseconds).

## 語法

```python
system.perspective.vibrateDevice(integer, [sessionId])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| duration | String | The duration in milliseconds to vibrate the device.Note:iOS vibration duration is fixed. Thus, this parameter will not impact the vibration duration on devices running iOS. |
| sessionId | String | Identifier of the Session to target. If omitted, the current Session will be used automatically. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.vibrateDevice(integer, [sessionId])
```


---



---

# system.perspective.workstation

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

The following functions offer various ways to interact with Perspective Workstation from a Python script. Note that the functions here only work when called from a session running in Perspective Workstation. When called from a session running in Workstation, this function will close Workstation. Attempts to put Workstation into Kiosk mode.

## 回傳值

**型別：** Object


---



---

# system.perspective.workstation.exit

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. When called from a session running in Workstation, this function will close Workstation. system.perspective.workstation.exit()

## 語法

```python
system.perspective.workstation.exit()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.workstation.exit()
```

### Example 2

```python
# This example will close the current Perspective Workstation Session.
system.perspective.workstation.exit()
```

### Example 3

```python
# This example will close the current Perspective Workstation Session.
system.perspective.workstation.exit()
```


---



---

# system.perspective.workstation.toKiosk

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. When called from a session running inPerspective Workstation, attempts to put Workstation into Kiosk mode. system.perspective.workstation.toKiosk()

## 語法

```python
system.perspective.workstation.toKiosk()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.workstation.toKiosk()
```

### Example 2

```python
# This example will set a Perspective Workstation Session into Kiosk mode.
system.perspective.workstation.toKiosk()
```

### Example 3

```python
# This example will set a Perspective Workstation Session into Kiosk mode.
system.perspective.workstation.toKiosk()
```


---



---

# system.perspective.workstation.toWindowed

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. When called from a Session running inPerspective Workstation, attempts to put Workstation into windowed mode. system.perspective.workstation.toWindowed()

## 語法

```python
system.perspective.workstation.toWindowed()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.workstation.toWindowed()
```

### Example 2

```python
# This example will set the Perspective Workstation Session to windowed mode.
system.perspective.workstation.toWindowed()
```

### Example 3

```python
# This example will set the Perspective Workstation Session to windowed mode.
system.perspective.workstation.toWindowed()
```


---

