# Ignition 8.1 - system.vision 函數文檔

﻿# Ignition 8.1 - 函數文檔（PATTERN 規範）

> 根據 FUNCTION_PATTERN 爬蟲生成
> 生成時間: 2026年04月19日 00:56:44
> 總計函式數: 434

## 📑 目錄

---

1. [system.vision.getKeyboardLayouts](#systemvisiongetkeyboardlayouts) - This function is used inPython Scripting. Returns a list of keyboard layouts available on this system.
2. [system.vision.updateProject](#systemvisionupdateproject) - This function is used inPython Scripting. Updates the Vision Client project with saved changes. This function is intended to be used in conjunction with the "None" option of Vision Project update modes in the Project Properties, and the Vision Client System TagProjectUpdateAvailable.

---

# system.vision.getKeyboardLayouts

**版本：** 8.1
**型別：** Scripting
**分類：** Vision

## 詳述

This function is used inPython Scripting. Returns a list of keyboard layouts available on this system.

## 語法

```python
system.vision.getKeyboardLayouts()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.vision.getKeyboardLayouts()
```

### Example 2

```python
# list all keyboard layouts that support English
for layout in system.vision.getKeyboardLayouts():
    if "en" in layout.supportedLanguages:
        print layout.name
```

### Example 3

```python
# list all keyboard layouts that support English
for layout in system.vision.getKeyboardLayouts():
    if "en" in layout.supportedLanguages:
        print layout.name
```


---



---

# system.vision.updateProject

**版本：** 8.1
**型別：** Scripting
**分類：** Vision

## 詳述

This function is used inPython Scripting. Updates the Vision Client project with saved changes. This function is intended to be used in conjunction with the "None" option of Vision Project update modes in the Project Properties, and the Vision Client System TagProjectUpdateAvailable.

## 語法

```python
system.vision.updateProject()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.vision.updateProject()
```

### Example 2

```python
# This script is intended to go on a Button component.
# Upon clicking, the Vision Client project will update with the latest changes.
system.vision.updateProject()
```

### Example 3

```python
# This script is intended to go on a Button component.
# Upon clicking, the Vision Client project will update with the latest changes.
system.vision.updateProject()
```


---
