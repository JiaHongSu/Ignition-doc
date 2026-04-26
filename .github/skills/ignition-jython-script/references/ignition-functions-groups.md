# Ignition 8.1 - system.groups 函數文檔


## 📑 目錄

---

1. [system.groups.loadFromFile](#systemgroupsloadfromfile) - This function is used inPython Scripting. Loads a transaction group configuration from an xml export, into the specified project (creating the project if necessary). The mode parameter dictates how overwrites occur. This function is scoped for Perspective Sessions, but since all scripts in Perspective run on the Gateway, the file must be located on the Gateway's file system.
2. [system.groups.removeGroups](#systemgroupsremovegroups) - This function is used inPython Scripting. Removes the specified groups from the project. The group paths areFolder/Path/To/GroupName, separated by forward slashes. This scripting function has noClient Permissionrestrictions.

---

# system.groups.loadFromFile

**版本：** 8.1
**型別：** Scripting
**分類：** Groups

## 詳述

This function is used inPython Scripting. Loads a transaction group configuration from an xml export, into the specified project (creating the project if necessary). The mode parameter dictates how overwrites occur. This function is scoped for Perspective Sessions, but since all scripts in Perspective run on the Gateway, the file must be located on the Gateway's file system.

## 語法

```python
 system.groups.loadFromFile(filePath, projectName, mode)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| filePath | String | The path to a valid transaction group xml or csv file. |
| projectName | String | The name of the project to load into. |
| mode | int | How duplicates will be handled. 0 = Overwrite, 1 = Ignore, 2 = Replace the existing project with this one. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
 system.groups.loadFromFile(filePath, projectName, mode)
```

### Example 3

```python
projectName
```


---



---

# system.groups.removeGroups

**版本：** 8.1
**型別：** Scripting
**分類：** Groups

## 詳述

This function is used inPython Scripting. Removes the specified groups from the project. The group paths areFolder/Path/To/GroupName, separated by forward slashes. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.groups.removeGroups(projectName, paths)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| projectName | String | The project to remove from. If the project does not exist, throws an IllegalArgumentException. |
| paths | List[String] | A list of paths to remove. Group paths are the full path to the resource, separated by forward slashes, e.g., "Folder/Path/To/GroupName". |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
Folder/Path/To/GroupName
```

### Example 2

```python
system.groups.removeGroups(projectName, paths)
```

### Example 3

```python
projectName
```


---

