# Ignition 8.1 - system.project 函數文檔


## 📑 目錄

---

1. [system.project.getProjectName](#systemprojectgetprojectname) - This function is used inPython Scripting. Returns the name of the project where the function was called from. When called from the Gateway scope from a resource that originates from a singular project (reports, SFCs, etc.), will return that resources project. Resources that run in the Gateway scope, but are configured in a singular project (such as a report), will use that project's name. When called from a scope that does not have an associated project (a Tag Event Script), the function will re
2. [system.project.getProjectNames](#systemprojectgetprojectnames) - This function is used inPython Scripting. Returns an unsorted collection of strings, where each string represents the name of a project on the Gateway. If no projects exist, returns an empty list. This function only ever returns project names, ignoring project titles. The function also ignores the "enabled" property, including disabled projects in the results.
3. [system.project.requestScan](#systemprojectrequestscan) - This function is used inPython Scripting. Requests a manual scan of the projects directory in order to refresh projects and their resources. If a scan is currently running, this method has no effect and will return when the in-progress scan has finished. This function blocks the current thread until a scan has completed. This scripting function has noClient Permissionrestrictions.

---

# system.project.getProjectName

**版本：** 8.1
**型別：** Scripting
**分類：** Project

## 詳述

This function is used inPython Scripting. Returns the name of the project where the function was called from. When called from the Gateway scope from a resource that originates from a singular project (reports, SFCs, etc.), will return that resources project. Resources that run in the Gateway scope, but are configured in a singular project (such as a report), will use that project's name. When called from a scope that does not have an associated project (a Tag Event Script), the function will re

## 語法

```python
system.project.getProjectName()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.project.getProjectName()
```

### Example 2

```python
# This code displays the name of the currently running project to the appropriate console,
# depending on scope (Designer console, Gateway console, etc.).
system.util.getLogger("myLogger").warn("You are running project: %s" % system.project.getProjectName())
```

### Example 3

```python
# This code displays the name of the currently running project to the appropriate console,
# depending on scope (Designer console, Gateway console, etc.).
system.util.getLogger("myLogger").warn("You are running project: %s" % system.project.getProjectName())
```


---



---

# system.project.getProjectNames

**版本：** 8.1
**型別：** Scripting
**分類：** Project

## 詳述

This function is used inPython Scripting. Returns an unsorted collection of strings, where each string represents the name of a project on the Gateway. If no projects exist, returns an empty list. This function only ever returns project names, ignoring project titles. The function also ignores the "enabled" property, including disabled projects in the results.

## 語法

```python
system.project.getProjectNames()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.project.getProjectNames()
```

### Example 2

```python
# Calling this from the Script Console prints out each project name.
print system.project.getProjectNames()
```

### Example 3

```python
# Calling this from the Script Console prints out each project name.
print system.project.getProjectNames()
```


---



---

# system.project.requestScan

**版本：** 8.1
**型別：** Scripting
**分類：** Project

## 詳述

This function is used inPython Scripting. Requests a manual scan of the projects directory in order to refresh projects and their resources. If a scan is currently running, this method has no effect and will return when the in-progress scan has finished. This function blocks the current thread until a scan has completed. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.project.requestScan([timeout])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| timeout | Integer | The amount of time, in seconds, to block the current thread before timing out. Default is 10 seconds. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.project.requestScan([timeout])
```

### Example 3

```python
# This example requests a manual scan of the project directory
# while blocking the current thread for 30 seconds before timing out.
system.project.requestScan(30)
```


---

