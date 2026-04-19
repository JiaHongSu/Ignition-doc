# Ignition 8.1 - system.nav 函數文檔

﻿# Ignition 8.1 - 函數文檔（PATTERN 規範）

> 根據 FUNCTION_PATTERN 爬蟲生成
> 生成時間: 2026年04月19日 00:56:44
> 總計函式數: 434

## 📑 目錄

---

1. [system.nav.centerWindow](#systemnavcenterwindow) - This function is used inPython Scripting. Given a window path, or a reference to a window itself, it will center the window. The window should be floating an non-maximized. If the window can't be found, this function will do nothing. This scripting function has noClient Permissionrestrictions.
2. [system.nav.closeParentWindow](#systemnavcloseparentwindow) - This function is used inPython Scripting. Closes the parent window given a component event object. This scripting function has noClient Permissionrestrictions.
3. [system.nav.closeWindow](#systemnavclosewindow) - This function is used inPython Scripting. Given a window path, or a reference to a window itself, it will close the window. If the window can't be found, this function will do nothing. This scripting function has noClient Permissionrestrictions.
4. [system.nav.desktop](#systemnavdesktop) - This function is used inPython Scripting. Allows for invokingsystem.navfunctions on a specific desktop. See theMulti-Monitor Clientspage for more details.
5. [system.nav.getCurrentWindow](#systemnavgetcurrentwindow) - This function is used inPython Scripting. Returns the path of the current "main screen" window, which is defined as the maximized window. With theTypical Navigation Strategy, there is only ever one maximized window at a time. This scripting function has noClient Permissionrestrictions.
6. [system.nav.goBack](#systemnavgoback) - This function is used inPython Scripting. When using theTypical Navigation Strategy, this function will navigate back to the previous main screen window. This scripting function has noClient Permissionrestrictions.
7. [system.nav.goForward](#systemnavgoforward) - This function is used inPython Scripting. When using thetypical navigation strategy, this function will navigate "forward" to the last main-screen window the user was on when they executed asystem.nav.goBack(). This scripting function has noClient Permissionrestrictions.
8. [system.nav.goHome](#systemnavgohome) - This function is used inPython Scripting. When using thetypical navigation strategy, this function will navigate to the "home" window. This is automatically detected as the first main-screen window shown in a project. If you are using this system function withsystem.nav.openWindow(), your home window should be closed before navigating to it, or system.nav.goHome() may not work. This scripting function has noClient Permissionrestrictions.
9. [system.nav.openWindow](#systemnavopenwindow) - This function is used inPython Scripting. Opens the window with the given path. If the window is already open, brings it to the front. The optional params dictionary contains key:valuepairs which will be used to set the target window's root container's dynamic variables. For instance, if the window that you are opening is namedTankDisplayand has a dynamic variable in its root container named "TankNumber", then callingsystem.nav.openWindow("TankDisplay", {"TankNumber" : 4})will open the TankDispl
10. [system.nav.openWindowInstance](#systemnavopenwindowinstance) - This function is used inPython Scripting. When called in a Vision Client, it operates exactly likesystem.nav.openWindow(), except that if the named window is already open, then an additional instance of the window will be opened. There is no limit to the number of additional instances of a window that you can open. When called in the Designer, it operates similar to system.nav.openWindow(), except that if the named window is already open the function will swap to the opened window. Additional in
11. [system.nav.swapTo](#systemnavswapto) - This function is used inPython Scripting. Performs a window swap from the current main screen window to the window specified. Swapping means that the opened window will take the place of the closing window - in this case it will be maximized. See also:Navigation Strategies. This function works likesystem.nav.swapWindow, except that you cannot specify the source for the swap.
12. [system.nav.swapWindow](#systemnavswapwindow) - This function is used inPython Scripting. Performs a window swap. This means that one window is closed, and another is opened and takes its place - assuming its size, floating state, and maximization state. This gives a seamless transition - one window seems to simply turn into another. This function works likesystem.nav.swapTo, except that you can specify the source and destination for the swap.

---

# system.nav.centerWindow

**版本：** 8.1
**型別：** Scripting
**分類：** Nav

## 詳述

This function is used inPython Scripting. Given a window path, or a reference to a window itself, it will center the window. The window should be floating an non-maximized. If the window can't be found, this function will do nothing. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.nav.centerWindow(windowPath)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| windowPath | String | The path of the window to center. |
| window | FPMIWindow | A reference to the window to center. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.nav.centerWindow(windowPath)
```

### Example 3

```python
system.nav.centerWindow(window)
```


---



---

# system.nav.closeParentWindow

**版本：** 8.1
**型別：** Scripting
**分類：** Nav

## 詳述

This function is used inPython Scripting. Closes the parent window given a component event object. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.nav.closeParentWindow(event)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| event | EventObject | A component event object. The enclosing window for the component will be closed. Refer toEventObject. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.nav.closeParentWindow(event)
```

### Example 3

```python
# This code would be placed in the actionPerformed event of a button,
# and would close the window that contained the button.
system.nav.closeParentWindow(event)
```


---



---

# system.nav.closeWindow

**版本：** 8.1
**型別：** Scripting
**分類：** Nav

## 詳述

This function is used inPython Scripting. Given a window path, or a reference to a window itself, it will close the window. If the window can't be found, this function will do nothing. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.nav.closeWindow(window)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| window | FPMIWindow | A reference to the window to close. |
| windowPath | String | The path of a window to close. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.nav.closeWindow(window)
```

### Example 3

```python
system.nav.closeWindow(windowPath)
```


---



---

# system.nav.desktop

**版本：** 8.1
**型別：** Scripting
**分類：** Nav

## 詳述

This function is used inPython Scripting. Allows for invokingsystem.navfunctions on a specific desktop. See theMulti-Monitor Clientspage for more details.

## 語法

```python
system.nav.desktop(handle)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| handle | String | The handle for the desktop to use. May be omitted for the primary desktop. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.nav.desktop(handle)
```

### Example 3

```python
# The following example will close a window at path "Main Windows/Overview" in the Primary Desktop,
# regardless of where the script originates from.
system.nav.desktop().closeWindow("Main Windows/Overview")
```


---



---

# system.nav.getCurrentWindow

**版本：** 8.1
**型別：** Scripting
**分類：** Nav

## 詳述

This function is used inPython Scripting. Returns the path of the current "main screen" window, which is defined as the maximized window. With theTypical Navigation Strategy, there is only ever one maximized window at a time. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.nav.getCurrentWindow()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.nav.getCurrentWindow()
```

### Example 2

```python
# This code could run in a global timer script.
# After a 5-minute timeout, navigate back to the home screen.
if system.util.getInactivitySeconds()>300 and system.nav.getCurrentWindow()!="Home":
   system.nav.swapTo("Home")
```

### Example 3

```python
# This code could run in a global timer script.
# After a 5-minute timeout, navigate back to the home screen.
if system.util.getInactivitySeconds()>300 and system.nav.getCurrentWindow()!="Home":
   system.nav.swapTo("Home")
```


---



---

# system.nav.goBack

**版本：** 8.1
**型別：** Scripting
**分類：** Nav

## 詳述

This function is used inPython Scripting. When using theTypical Navigation Strategy, this function will navigate back to the previous main screen window. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.nav.goBack()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.nav.goBack()
```

### Example 2

```python
# This code would go in a button to move to the previous screen.
system.nav.goBack()
```

### Example 3

```python
# This code would go in a button to move to the previous screen.
system.nav.goBack()
```


---



---

# system.nav.goForward

**版本：** 8.1
**型別：** Scripting
**分類：** Nav

## 詳述

This function is used inPython Scripting. When using thetypical navigation strategy, this function will navigate "forward" to the last main-screen window the user was on when they executed asystem.nav.goBack(). This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.nav.goForward()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.nav.goForward()
```

### Example 2

```python
# This code would go in a button to move to the last screen that used system.nav.goBack().
system.nav.goForward()
```

### Example 3

```python
# This code would go in a button to move to the last screen that used system.nav.goBack().
system.nav.goForward()
```


---



---

# system.nav.goHome

**版本：** 8.1
**型別：** Scripting
**分類：** Nav

## 詳述

This function is used inPython Scripting. When using thetypical navigation strategy, this function will navigate to the "home" window. This is automatically detected as the first main-screen window shown in a project. If you are using this system function withsystem.nav.openWindow(), your home window should be closed before navigating to it, or system.nav.goHome() may not work. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.nav.goHome()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.nav.goHome()
```

### Example 2

```python
# This code would go in a button to move to the Home screen.
system.nav.goHome()
```

### Example 3

```python
# This code would go in a button to move to the Home screen.
system.nav.goHome()
```


---



---

# system.nav.openWindow

**版本：** 8.1
**型別：** Scripting
**分類：** Nav

## 詳述

This function is used inPython Scripting. Opens the window with the given path. If the window is already open, brings it to the front. The optional params dictionary contains key:valuepairs which will be used to set the target window's root container's dynamic variables. For instance, if the window that you are opening is namedTankDisplayand has a dynamic variable in its root container named "TankNumber", then callingsystem.nav.openWindow("TankDisplay", {"TankNumber" : 4})will open the TankDispl

## 語法

```python
system.nav.openWindow("TankDisplay", {"TankNumber" : 4})
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| path | String | The path to the window to open. |
| params | Dictionary[String, Any] | A dictionary of parameters to pass into the window. The keys in the dictionary must match dynamic property names on the target window's root container. The values for each key will be used to set those properties. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.nav.openWindow("TankDisplay", {"TankNumber" : 4})
```

### Example 2

```python
system.nav.openWindow(path, [params])
```


---



---

# system.nav.openWindowInstance

**版本：** 8.1
**型別：** Scripting
**分類：** Nav

## 詳述

This function is used inPython Scripting. When called in a Vision Client, it operates exactly likesystem.nav.openWindow(), except that if the named window is already open, then an additional instance of the window will be opened. There is no limit to the number of additional instances of a window that you can open. When called in the Designer, it operates similar to system.nav.openWindow(), except that if the named window is already open the function will swap to the opened window. Additional in

## 語法

```python
system.nav.openWindowInstance(path, [params])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| path | String | The path to the window to open. |
| params | Dictionary[String, Any] | A dictionary of parameters to pass into the window. The keys in the dictionary must match dynamic property names on the target window's root container. The values for each key will be used to set those properties. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.nav.openWindowInstance(path, [params])
```


---



---

# system.nav.swapTo

**版本：** 8.1
**型別：** Scripting
**分類：** Nav

## 詳述

This function is used inPython Scripting. Performs a window swap from the current main screen window to the window specified. Swapping means that the opened window will take the place of the closing window - in this case it will be maximized. See also:Navigation Strategies. This function works likesystem.nav.swapWindow, except that you cannot specify the source for the swap.

## 語法

```python
system.nav.swapTo(path, [params])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| path | String | The path of a window to swap to. |
| params | Dictionary[String, Any] | A dictionary of parameters to pass into the window. The keys in the dictionary must match dynamic property names on the target window's root container. The values for each key will be used to set those properties. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.nav.swapTo(path, [params])
```


---



---

# system.nav.swapWindow

**版本：** 8.1
**型別：** Scripting
**分類：** Nav

## 詳述

This function is used inPython Scripting. Performs a window swap. This means that one window is closed, and another is opened and takes its place - assuming its size, floating state, and maximization state. This gives a seamless transition - one window seems to simply turn into another. This function works likesystem.nav.swapTo, except that you can specify the source and destination for the swap.

## 語法

```python
system.nav.swapWindow(swapFromPath, swapToPath, [params])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| swapFromPath | String | The path of the window to swap from. Must be a currently open window, otherwise this will act like an openWindow. |
| swapToPath | String | The name of the window to swap to. |
| params | Dictionary[String, Any] | A dictionary of parameters to pass into the window. The keys in the dictionary must match dynamic property names on the target window's root container. The values for each key will be used to set those properties. [optional] |
| event | EventObject | A component event whose enclosing window will be used as the "swap-from" window. |
| swapToPath | String | The name of the window to swap to. |
| params | Dictionary[String, Any] | A dictionary of parameters to pass into the window. The keys in the dictionary must match dynamic property names on the target window's root container. The values for each key will be used to set those properties. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.nav.swapWindow(swapFromPath, swapToPath, [params])
```

### Example 2

```python
swapFromPath
```


---

