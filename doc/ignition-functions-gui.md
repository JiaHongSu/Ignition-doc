# Ignition 8.1 - system.gui 函數文檔

﻿# Ignition 8.1 - 函數文檔（PATTERN 規範）

> 根據 FUNCTION_PATTERN 爬蟲生成
> 生成時間: 2026年04月19日 00:56:44
> 總計函式數: 434

## 📑 目錄

---

1. [system.gui.chooseColor](#systemguichoosecolor) - This function is used inPython Scripting. Prompts the user to pick a color using the default color-chooser dialog box. This scripting function has noClient Permissionrestrictions.
2. [system.gui.closeDesktop](#systemguiclosedesktop) - This function is used inPython Scripting. Allows you to close any of the open desktops associated with the current client. See theMulti-Monitor Clientspage for more details about using multiple monitors. This scripting function has noClient Permissionrestrictions.
3. [system.gui.color](#systemguicolor) - This function is used inPython Scripting. Creates a new color object, either by parsing a string or by having the RGB[A] channels specified explicitly. SeetoColorto see a list of available color names. This scripting function has noClient Permissionrestrictions.
4. [system.gui.confirm](#systemguiconfirm) - This function is used inPython Scripting. Displays a confirmation dialog box to the user with "Yes" and "No" options, and a custom message. This scripting function has noClient Permissionrestrictions.
5. [system.gui.convertPointToScreen](#systemguiconvertpointtoscreen) - This function is used inPython Scripting. Converts a pair of coordinates that are relative to the upper-left corner of a component to be relative to the upper-left corner of the entire screen. This scripting function has noClient Permissionrestrictions.
6. [system.gui.createPopupMenu](#systemguicreatepopupmenu) - This function is used inPython Scripting. Creates a new popup menu, which can then be shown over a component on a mouse event. To use this function, first create a Python sequence whose entries are strings, and another sequence whose entries are function objects. The strings will be the items that are displayed in your popup menu, and when an item is clicked, its corresponding function will be run. Your functions must accept an event object as an argument. See also:Functions. The function return
7. [system.gui.desktop](#systemguidesktop) - This function is used inPython Scripting. Allows for invoking system.gui functions on a specific desktop. See theMulti-Monitor Clientspage for more details.
8. [system.gui.errorBox](#systemguierrorbox) - This function is used inPython Scripting. Displays an error-style message box to the user. This scripting function has noClient Permissionrestrictions.
9. [system.gui.findWindow](#systemguifindwindow) - This function is used inPython Scripting. Finds and returns a list of windows with the given path. If the window is not open, an empty list will be returned. Useful for finding all instances of an open window that were opened withsystem.nav.openWindowInstance. This scripting function has noClient Permissionrestrictions.
10. [system.gui.getCurrentDesktop](#systemguigetcurrentdesktop) - This function is used inPython Scripting. Returns the handle of the desktop this function was called from. Commonly used with thesystem.gui.desktopandsystem.nav.desktopfunctions. This scripting function has noClient Permissionrestrictions.
11. [system.gui.getDesktopHandles](#systemguigetdesktophandles) - This function is used inPython Scripting. Gets a list of allsecondaryhandles of the open desktops associated with the current client. In this case,secondarymeans any desktop frame opened by the original client frame. For example, if the original client opened two new frames ('left client' and 'right client'), then this function would return ['left client', 'right client'].
12. [system.gui.getOpenedWindowNames](#systemguigetopenedwindownames) - This function is used inPython Scripting. Finds all of the currently open windows and returns a tuple of their paths. This scripting function has noClient Permissionrestrictions.
13. [system.gui.getOpenedWindows](#systemguigetopenedwindows) - This function is used inPython Scripting. Finds all of the currently open windows and returns a tuple of references to them. This scripting function has noClient Permissionrestrictions.
14. [system.gui.getParentWindow](#systemguigetparentwindow) - This function is used inPython Scripting. Finds the parent (enclosing) window for the component that fired an event and returns a reference to it. This scripting function has noClient Permissionrestrictions.
15. [system.gui.getQuality](#systemguigetquality) - This function is used inPython Scripting. Returns the data quality for the property of the given component as an integer. This function can be used to check the quality of a Tag binding on a component in the middle of the script so that alternative actions can be taken in the event of device disconnections. A description of the quality codes can be found on theQuality Codes and Overlayspage.
16. [system.gui.getScreenIndex](#systemguigetscreenindex) - This function is used inPython Scripting. Returns an integer value representing the current screen index based on the screen from which this function was called. This scripting function has noClient Permissionrestrictions.
17. [system.gui.getScreens](#systemguigetscreens) - This function is used inPython Scripting. Get a list of all the monitors on the computer this client is open on. Use withsystem.gui.setScreenIndex()to move the client. This scripting function has noClient Permissionrestrictions.
18. [system.gui.getSibling](#systemguigetsibling) - This function is used inPython Scripting. Given a component event object, looks up a sibling component. Shortcut forevent.source.parent.getComponent("siblingName"). If no such sibling is found, the special value None is returned. This scripting function has noClient Permissionrestrictions.
19. [system.gui.getWindow](#systemguigetwindow) - This function is used inPython Scripting. Finds a reference to an open window with the given name. Throws a ValueError if the named window is not open or not found. This scripting function has noClient Permissionrestrictions.
20. [system.gui.getWindowNames](#systemguigetwindownames) - This function is used inPython Scripting. Returns a list of the paths of all windows in the current project, sorted alphabetically. This scripting function has noClient Permissionrestrictions.
21. [system.gui.inputBox](#systemguiinputbox) - This function is used inPython Scripting. Opens up a popup input dialog box. This dialog box will show a prompt message and allow the user to type in a string. When the user is done, they can clickOKorCancel. If OK is pressed, this function will return with the value that they typed in. If Cancel is pressed, this function will return the value None. This scripting function has noClient Permissionrestrictions.
22. [system.gui.isTouchscreenModeEnabled](#systemguiistouchscreenmodeenabled) - This function is used inPython Scripting. Checks whether or not the running Client's Touch Screen mode is currently enabled. This scripting function has noClient Permissionrestrictions.
23. [system.gui.messageBox](#systemguimessagebox) - This function is used inPython Scripting. Displays an informational-style message popup box to the user. This scripting function has noClient Permissionrestrictions.
24. [system.gui.openDesktop](#systemguiopendesktop) - This function is used inPython Scripting. Creates an additional Desktop in a new frame. For more details, see theMulti-Monitor Clientspage. This function acceptskeyword arguments.
25. [system.gui.openDiagnostics](#systemguiopendiagnostics) - This function is used inPython Scripting. Opens the Client runtime Diagnostics window, which provides information regarding performance, logging, active threads, connection status, and the console. This provides an opportunity to open the Diagnostics window in situations where the menu bar in the client is hidden, and the keyboard shortcut (Ctrl+Shift+F7) can not be used. This scripting function has noClient Permissionrestrictions.
26. [system.gui.passwordBox](#systemguipasswordbox) - This function is used inPython Scripting. Pops up a special input box that uses a password field, so the text isn't echoed back in clear-text to the user. Returns the text they entered, or None if they canceled the dialog box. This scripting function has noClient Permissionrestrictions.
27. [system.gui.setScreenIndex](#systemguisetscreenindex) - This function is used inPython Scripting. Moves an open client to a specific monitor. Use withsystem.gui.getScreens()to identify monitors before moving. This scripting function has noClient Permissionrestrictions.
28. [system.gui.setTouchscreenModeEnabled](#systemguisettouchscreenmodeenabled) - This function is used inPython Scripting. Alters a running Client's Touch Screen mode on the fly. This scripting function has noClient Permissionrestrictions.
29. [system.gui.showNumericKeypad](#systemguishownumerickeypad) - This function is used inPython Scripting. Displays a modal on-screen numeric keypad, allowing for arbitrary numeric entry using the mouse, or a finger on a touch screen monitor. Returns the number that the user entered. This scripting function has noClient Permissionrestrictions.
30. [system.gui.showTouchscreenKeyboard](#systemguishowtouchscreenkeyboard) - This function is used inPython Scripting. Displays a modal on-screen keyboard, allowing for arbitrary text entry using the mouse, or a finger on a touchscreen monitor. Returns the text that the user entered. This scripting function has noClient Permissionrestrictions.
31. [system.gui.transform](#systemguitransform) - This function is used inPython Scripting. Sets a component's position and size at runtime.  Additional arguments for the duration, framesPerSecond, and acceleration of the operation exist for animation.  An optional callback argument will be executed when the transformation is complete. The transformation is performed in Designer coordinate space on components that are centered or have more than two anchors.
32. [system.gui.warningBox](#systemguiwarningbox) - This function is used inPython Scripting. Displays a message to the user in a warning style popup dialog. This scripting function has noClient Permissionrestrictions.

---

# system.gui.chooseColor

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Prompts the user to pick a color using the default color-chooser dialog box. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.chooseColor(initialColor, [dialogTitle])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| initialColor | Color | A color to use as a starting point in the color choosing popup. |
| dialogTitle | String | The title for the color choosing popup. Defaults to "Choose Color". [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.chooseColor(initialColor, [dialogTitle])
```

### Example 2

```python
initialColor
```

### Example 3

```python
dialogTitle
```


---



---

# system.gui.closeDesktop

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Allows you to close any of the open desktops associated with the current client. See theMulti-Monitor Clientspage for more details about using multiple monitors. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.closeDesktop(handle)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| handle | String | The handle for the desktop to close. The screen index cast as a string may be used instead of the handle. If omitted, this will default to the primary desktop. Alternatively, the handle "primary" can be used to refer to the primary desktop. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.closeDesktop(handle)
```

### Example 3

```python
# The following example will close this desktop
system.gui.closeDesktop()
```


---



---

# system.gui.color

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Creates a new color object, either by parsing a string or by having the RGB[A] channels specified explicitly. SeetoColorto see a list of available color names. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.color(color)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| color | String | A string that will be coerced into a color. Can accept many formats, such as "red" or "#FF0000" or "255,0,0". |
| red | Integer | The red component of the color, an integer 0-255. |
| green | Integer | The green component of the color, an integer 0-255. |
| blue | Integer | The blue component of the color, an integer 0-255. |
| alpha | Integer | The alpha component of the color, an integer 0-255. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.color(color)
```

### Example 3

```python
system.gui.color(red, green, blue, [alpha])
```


---



---

# system.gui.confirm

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Displays a confirmation dialog box to the user with "Yes" and "No" options, and a custom message. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.confirm(message, [title], [allowCancel])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| message | String | The message to show in the confirmation dialog. |
| title | String | The title for the confirmation dialog. [optional] |
| allowCancel | Boolean | Show a cancel button in the dialog. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.confirm(message, [title], [allowCancel])
```


---



---

# system.gui.convertPointToScreen

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Converts a pair of coordinates that are relative to the upper-left corner of a component to be relative to the upper-left corner of the entire screen. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.convertPointToScreen(x, y, event)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| x | Integer | The X-coordinate, relative to the component that fired the event. |
| y | Integer | The Y-coordinate, relative to the component that fired the event. |
| event | EventObject | An event object for a component event. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.convertPointToScreen(x, y, event)
```


---



---

# system.gui.createPopupMenu

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Creates a new popup menu, which can then be shown over a component on a mouse event. To use this function, first create a Python sequence whose entries are strings, and another sequence whose entries are function objects. The strings will be the items that are displayed in your popup menu, and when an item is clicked, its corresponding function will be run. Your functions must accept an event object as an argument. See also:Functions. The function return

## 語法

```python
system.gui.createPopupMenu(itemNames, itemFunctions)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| itemNames | List[String] | A list of names to create popup menu items with. |
| itemFunctions | List[String] | A list of functions to match up with the names. Passing in a None object will cause a separator line to appear in the popup menu, and the corresponding string will not be displayed (note that a corresponding string must be supplied, since the number of elements in the itemFunctions parameter must always match the number of elements in the itemNames parameter). |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.createPopupMenu(itemNames, itemFunctions)
```

### Example 3

```python
itemFunctions
```


---



---

# system.gui.desktop

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Allows for invoking system.gui functions on a specific desktop. See theMulti-Monitor Clientspage for more details.

## 語法

```python
system.gui.desktop(handle)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| handle | String | The handle for the desktop to use. The screen index cast as a string may be used instead of the handle. If omitted, this will default to the primary desktop. Alternatively, the handle "primary" can be used to refer to the primary desktop. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.desktop(handle)
```

### Example 3

```python
# The following example makes a message box appear on the primary desktop,
# regardless of where the script originates.


---

# system.gui.desktop() function requires a handle be passed to it for this example
# to work properly.

system.gui.desktop().messageBox("This will appear on the Primary Desktop")
```


---



---

# system.gui.errorBox

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Displays an error-style message box to the user. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.errorBox(message, [title])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| message | String | The message to display in an error box. Will accept HTML formatting. |
| title | String | The title for the error box. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.errorBox(message, [title])
```


---



---

# system.gui.findWindow

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Finds and returns a list of windows with the given path. If the window is not open, an empty list will be returned. Useful for finding all instances of an open window that were opened withsystem.nav.openWindowInstance. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.findWindow(path)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| path | String | The path of the window to search for. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.findWindow(path)
```

### Example 3

```python
# This example finds all open instances of the window named "Popup" and closes them all.

allInstances = system.gui.findWindow("Popup")
for window in allInstances:
    system.nav.closeWindow(window)
```


---



---

# system.gui.getCurrentDesktop

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Returns the handle of the desktop this function was called from. Commonly used with thesystem.gui.desktopandsystem.nav.desktopfunctions. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.getCurrentDesktop( )
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.getCurrentDesktop( )
```

### Example 2

```python
# Shows the desktop's handle in a message box.
system.gui.messageBox("This desktop's handle is: %s" % system.gui.getCurrentDesktop())
```

### Example 3

```python
# Shows the desktop's handle in a message box.
system.gui.messageBox("This desktop's handle is: %s" % system.gui.getCurrentDesktop())
```


---



---

# system.gui.getDesktopHandles

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Gets a list of allsecondaryhandles of the open desktops associated with the current client. In this case,secondarymeans any desktop frame opened by the original client frame. For example, if the original client opened two new frames ('left client' and 'right client'), then this function would return ['left client', 'right client'].

## 語法

```python
system.gui.getDesktopHandles()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.getDesktopHandles()
```

### Example 2

```python
# The following example list all handles (except the main client)
# in the client console (Help -> Diagnostics -> Console)

print system.gui.getDesktopHandles()
```

### Example 3

```python
# The following example list all handles (except the main client)
# in the client console (Help -> Diagnostics -> Console)

print system.gui.getDesktopHandles()
```


---



---

# system.gui.getOpenedWindowNames

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Finds all of the currently open windows and returns a tuple of their paths. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.getOpenedWindowNames()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.getOpenedWindowNames()
```

### Example 2

```python
# This example prints out into the console the full path for each opened window.

windows = system.gui.getOpenedWindowNames()
print 'There are %d windows open' % len(windows)
for path in windows:
    print path
```

### Example 3

```python
# This example prints out into the console the full path for each opened window.

windows = system.gui.getOpenedWindowNames()
print 'There are %d windows open' % len(windows)
for path in windows:
    print path
```


---



---

# system.gui.getOpenedWindows

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Finds all of the currently open windows and returns a tuple of references to them. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.getOpenedWindows()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.getOpenedWindows()
```

### Example 2

```python
# This example prints out the path of each currently opened window to the console.

windows = system.gui.getOpenedWindows()
print 'There are %d windows open' % len(windows)
for window in windows:
    print window.getPath()
```

### Example 3

```python
# This example prints out the path of each currently opened window to the console.

windows = system.gui.getOpenedWindows()
print 'There are %d windows open' % len(windows)
for window in windows:
    print window.getPath()
```


---



---

# system.gui.getParentWindow

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Finds the parent (enclosing) window for the component that fired an event and returns a reference to it. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.getParentWindow(event)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| event | EventObject | A component event object. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.getParentWindow(event)
```

### Example 3

```python
# Use this in an event script to change the window's title.

window = system.gui.getParentWindow(event)
window.title='This is a new title'
```


---



---

# system.gui.getQuality

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Returns the data quality for the property of the given component as an integer. This function can be used to check the quality of a Tag binding on a component in the middle of the script so that alternative actions can be taken in the event of device disconnections. A description of the quality codes can be found on theQuality Codes and Overlayspage.

## 語法

```python
system.gui.getQuality(component, propertyName)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| component | JComponent | The component whose property is being checked. |
| propertyName | String | The name of the property as a string value. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.getQuality(component, propertyName)
```

### Example 3

```python
propertyName
```


---



---

# system.gui.getScreenIndex

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Returns an integer value representing the current screen index based on the screen from which this function was called. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.getScreenIndex()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.getScreenIndex()
```

### Example 2

```python
# Prints an integer representing the screen from which the function was called.
print system.gui.getScreenIndex()
```

### Example 3

```python
# Prints an integer representing the screen from which the function was called.
print system.gui.getScreenIndex()
```


---



---

# system.gui.getScreens

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Get a list of all the monitors on the computer this client is open on. Use withsystem.gui.setScreenIndex()to move the client. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.getScreens()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.getScreens()
```

### Example 2

```python
# This example fetches monitor data and pushes it to a table in the same container.

screens = system.gui.getScreens()
pyData = []
for screen in screens:
    pyData.append([screen[0], screen[1], screen[2]])

# Push data to 'Table'.
event.source.parent.getComponent('Table').data = system.dataset.toDataSet(["screen","width","height"], pyData)
```

### Example 3

```python
# This example fetches monitor data and pushes it to a table in the same container.

screens = system.gui.getScreens()
pyData = []
for screen in screens:
    pyData.append([screen[0], screen[1], screen[2]])

# Push data to 'Table'.
event.source.parent.getComponent('Table').data = system.dataset.toDataSet(["screen","width","height"], pyData)
```


---



---

# system.gui.getSibling

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Given a component event object, looks up a sibling component. Shortcut forevent.source.parent.getComponent("siblingName"). If no such sibling is found, the special value None is returned. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.getSibling(event, name)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| event | EventObject | A component event object. |
| name | String | The name of the sibling component. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.getSibling(event, name)
```


---



---

# system.gui.getWindow

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Finds a reference to an open window with the given name. Throws a ValueError if the named window is not open or not found. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.getWindow(name)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| name | String | The path to the window to field. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.getWindow(name)
```

### Example 3

```python
# This example will get the window named 'Overview' and then close it.

try:
   window = system.gui.getWindow('Overview')
   system.gui.closeWindow(window)

except ValueError:
   system.gui.warningBox("The Overview window isn't open")
```


---



---

# system.gui.getWindowNames

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Returns a list of the paths of all windows in the current project, sorted alphabetically. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.getWindowNames()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.getWindowNames()
```

### Example 2

```python
# This example would open windows that begin with "Motor" and pass in the currently selected motor number.

motor = event.source.parent.number
windows = system.gui.getWindowNames()
for path in windows:
   if name[:5] == "Motor":
      system.nav.openWindow(path, {"motorNumber":motor})
```

### Example 3

```python
# This example would open windows that begin with "Motor" and pass in the currently selected motor number.

motor = event.source.parent.number
windows = system.gui.getWindowNames()
for path in windows:
   if name[:5] == "Motor":
      system.nav.openWindow(path, {"motorNumber":motor})
```


---



---

# system.gui.inputBox

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Opens up a popup input dialog box. This dialog box will show a prompt message and allow the user to type in a string. When the user is done, they can clickOKorCancel. If OK is pressed, this function will return with the value that they typed in. If Cancel is pressed, this function will return the value None. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.inputBox(message, defaultText)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| message | String | The message to display for the input box. Will accept HTML formatting. |
| defaultText | String | The default text to initialize the input box with. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.inputBox(message, defaultText)
```

### Example 3

```python
defaultText
```


---



---

# system.gui.isTouchscreenModeEnabled

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Checks whether or not the running Client's Touch Screen mode is currently enabled. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.isTouchscreenModeEnabled()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.isTouchscreenModeEnabled()
```

### Example 2

```python
# This example is used in the Client Startup script to check if this Client is being run on a touch screen computer (judged by an IP address) and set Touch Screen mode.

ipAddress = system.net.getIpAddress()
query = "SELECT COUNT(*) FROM touchscreen_computer_ips WHERE ip_address = '%s' "
isTouchscreen = system.db.runScalarQuery(query %(ipAddress))
if isTouchscreen and not system.gui.isTouchscreenModeEnabled():
   system.gui.setTouchscreenModeEnabled(1)
```

### Example 3

```python
# This example is used in the Client Startup script to check if this Client is being run on a touch screen computer (judged by an IP address) and set Touch Screen mode.

ipAddress = system.net.getIpAddress()
query = "SELECT COUNT(*) FROM touchscreen_computer_ips WHERE ip_address = '%s' "
isTouchscreen = system.db.runScalarQuery(query %(ipAddress))
if isTouchscreen and not system.gui.isTouchscreenModeEnabled():
   system.gui.setTouchscreenModeEnabled(1)
```


---



---

# system.gui.messageBox

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Displays an informational-style message popup box to the user. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.messageBox(message, title)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| message | String | The message to display. Will accept HTML formatting. |
| title | String | A title for the message box. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.messageBox(message, title)
```


---



---

# system.gui.openDesktop

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Creates an additional Desktop in a new frame. For more details, see theMulti-Monitor Clientspage. This function acceptskeyword arguments.

## 語法

```python
system.gui.openDesktop ([screen], [handle], [title], [width], [height], [x], [y], [windows])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| screen | Integer | The screen index of which screen to place the new frame on. If omitted, screen 0 will be used. [optional] |
| handle | String | A name for the desktop. If omitted, the screen index will be used. [optional] |
| title | String | The title for the new frame. If omitted, the index handle will be used. If the handle and title are omitted, the screen index will be used. [optional] |
| width | Integer | The width for the new desktop's frame. If omitted, frame will become maximized on the specified monitor. [optional] |
| height | Integer | The height for the new desktop's frame. If omitted, frame will become maximized on the specified monitor. [optional] |
| x | Integer | The x coordinate for the new desktop's frame. Only used if both width and height are specified. If omitted, defaults to 0. [optional] |
| y | Integer | The y coordinate for the new desktop's frame. Only used if both width and height are specified. If omitted, defaults to 0. [optional] |
| windows | PySequence | A list of window paths to open in the new Desktop frame. If omitted, the desktop will open without any opened windows. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.openDesktop ([screen], [handle], [title], [width], [height], [x], [y], [windows])
```


---



---

# system.gui.openDiagnostics

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Opens the Client runtime Diagnostics window, which provides information regarding performance, logging, active threads, connection status, and the console. This provides an opportunity to open the Diagnostics window in situations where the menu bar in the client is hidden, and the keyboard shortcut (Ctrl+Shift+F7) can not be used. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.openDiagnostics()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.openDiagnostics()
```

### Example 2

```python
# Opens the diagnostics window in a running client
system.gui.openDiagnostics()
```

### Example 3

```python
# Opens the diagnostics window in a running client
system.gui.openDiagnostics()
```


---



---

# system.gui.passwordBox

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Pops up a special input box that uses a password field, so the text isn't echoed back in clear-text to the user. Returns the text they entered, or None if they canceled the dialog box. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.passwordBox(message, [title], [echoChar])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| message | String | The message for the password prompt. Will accept HTML formatting. |
| title | String | A title for the password prompt. [optional] |
| echoChar | String | A custom echo character. Defaults to:*[optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.passwordBox(message, [title], [echoChar])
```


---



---

# system.gui.setScreenIndex

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Moves an open client to a specific monitor. Use withsystem.gui.getScreens()to identify monitors before moving. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.setScreenIndex(index)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| index | Integer | The new monitor index for this client to move to. 0 based. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.setScreenIndex(index)
```

### Example 3

```python
# This example could be used on a startup script to move the client to a 2nd monitor.

system.gui.setScreenIndex(1)
```


---



---

# system.gui.setTouchscreenModeEnabled

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Alters a running Client's Touch Screen mode on the fly. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.setTouchscreenModeEnabled(enabled)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| enabled | Boolean | The new value for touchscreen mode being enabled. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.setTouchscreenModeEnabled(enabled)
```

### Example 3

```python
# This example could be used on an input heavy window's internalFrameActivated event to remove Touch Screen mode.

if system.gui.isTouchscreenModeEnabled():
   system.gui.setTouchscreenModeEnabled(False)
```


---



---

# system.gui.showNumericKeypad

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Displays a modal on-screen numeric keypad, allowing for arbitrary numeric entry using the mouse, or a finger on a touch screen monitor. Returns the number that the user entered. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.showNumericKeypad(initialValue, [fontSize], [usePasswordMode])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| initialValue | Number | The value to start the on-screen keypad with. |
| fontSize | Integer | The font size to display in the keypad. [optional] |
| usePasswordMode | Boolean | If True, display a*for each digit. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.showNumericKeypad(initialValue, [fontSize], [usePasswordMode])
```

### Example 2

```python
initialValue
```


---



---

# system.gui.showTouchscreenKeyboard

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Displays a modal on-screen keyboard, allowing for arbitrary text entry using the mouse, or a finger on a touchscreen monitor. Returns the text that the user entered. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.showTouchscreenKeyboard(initialText, [fontSize], [passwordMode])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| initialText | String | The text to start the on-screen keyboard with. |
| fontSize | Integer | The font size to display in the keyboard. [optional] |
| passwordMode | Boolean | A True value will activate password mode, where the text entered is not echoed back in cleartext. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.showTouchscreenKeyboard(initialText, [fontSize], [passwordMode])
```

### Example 2

```python
initialText
```


---



---

# system.gui.transform

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Sets a component's position and size at runtime.  Additional arguments for the duration, framesPerSecond, and acceleration of the operation exist for animation.  An optional callback argument will be executed when the transformation is complete. The transformation is performed in Designer coordinate space on components that are centered or have more than two anchors.

## 語法

```python
system.gui.transform(component, [newX], [newY], [newWidth], [newHeight], [duration], [callback], [framesPerSecond], [acceleration], [coordSpace])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| component | JComponent | The component to move or resize. |
| newX | Integer | An x-coordinate to move to, relative to the upper-left corner of the component's parent container. [optional] |
| newY | Integer | A y-coordinate to move to, relative to the upper-left corner of the component's parent container. [optional] |
| newWidth | Integer | A width for the component. [optional] |
| newHeight | Integer | A height for the component. [optional] |
| duration | Integer | A duration over which the transformation will take place.  If omitted or 0, the transform will take place immediately. [optional] |
| callback | Callable | Function to be called when the transformation is complete. [optional] |
| framesPerSecond | Integer | Frame rate argument which dictates how often the transformation updates over the given duration.  The default is 60 frames per second. [optional] |
| acceleration | Integer | An optional modifier to the acceleration of the transformation over the given duration. Seesystem.gui constantsfor valid arguments. [optional] |
| coordSpace | Integer | The coordinate space to use. When the default screen coordinates are used, the given size and position are absolute, as they appear in the Client at runtime. When Designer Coordinates are used, the given size and position are pre-runtime adjusted values, as they would appear in the Designer. Seesystem.gui constantsfor valid arguments. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.transform(component, [newX], [newY], [newWidth], [newHeight], [duration], [callback], [framesPerSecond], [acceleration], [coordSpace])
```


---



---

# system.gui.warningBox

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Displays a message to the user in a warning style popup dialog. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.warningBox(message, [title])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| message | String | The message to display in the warning box. Will accept HTML formatting if the message parameter is encapsulated in an <html> tag. |
| title | String | The title for the warning box. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.warningBox(message, [title])
```


---

