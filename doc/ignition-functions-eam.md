# Ignition 8.1 - system.eam 函數文檔


## 📑 目錄

---

1. [system.eam.getGroups](#systemeamgetgroups) - This function is used inPython Scripting. Returns the names of the defined agent organizational groups in the Gateway. This function can only be called from the Controller. This scripting function has noClient Permissionrestrictions.
2. [system.eam.queryAgentHistory](#systemeamqueryagenthistory) - This function is used inPython Scripting. Returns a list of the most recent agent events. This function can only be called from the Controller. This scripting function has noClient Permissionrestrictions.
3. [system.eam.queryAgentStatus](#systemeamqueryagentstatus) - This function is used inPython Scripting. Returns the current state of the matching agents. This function can only be called from the Controller. This scripting function has noClient Permissionrestrictions.
4. [system.eam.runTask](#systemeamruntask) - This function is used inPython Scripting. Takes the name of a task as an argument as a string (must be configured on the Controller before hand), attempts to execute the task. This function can only be called from the Controller. To run in the client, the user needs arole-based permission. This permission is disabled by default.

---

# system.eam.getGroups

**版本：** 8.1
**型別：** Scripting
**分類：** Eam

## 詳述

This function is used inPython Scripting. Returns the names of the defined agent organizational groups in the Gateway. This function can only be called from the Controller. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.eam.getGroups()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.eam.getGroups()
```

### Example 2

```python
# Return and print all of the EAM groups
groups = system.eam.getGroups()
for group in groups:
    print group
```

### Example 3

```python
# Return and print all of the EAM groups
groups = system.eam.getGroups()
for group in groups:
    print group
```


---



---

# system.eam.queryAgentHistory

**版本：** 8.1
**型別：** Scripting
**分類：** Eam

## 詳述

This function is used inPython Scripting. Returns a list of the most recent agent events. This function can only be called from the Controller. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.eam.queryAgentHistory(groupIds, agentIds, startDate, endDate, limit)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| groupIds | List | A list of groups to restrict the results to. If not specified, all groups will be included. |
| agentIds | List | A list of agent names to restrict the results to. If not specified, all agents will be allowed. |
| startDate | Date | The starting time for history events. If null, defaults to 8 hours previous to now. |
| endDate | Date | The ending time for the query range. If null, defaults to "now". |
| limit | int | The limit of results to return. Defaults to 100. A value of 0 means "no limit". |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.eam.queryAgentHistory(groupIds, agentIds, startDate, endDate, limit)
```


---



---

# system.eam.queryAgentStatus

**版本：** 8.1
**型別：** Scripting
**分類：** Eam

## 詳述

This function is used inPython Scripting. Returns the current state of the matching agents. This function can only be called from the Controller. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.eam.queryAgentStatus(groupIds, agentIds, isConnected)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| groupIds | List | A list of groups to restrict the results to. If not specified, all groups will be included. |
| agentIds | List | A list of agent names to restrict the results to. If not specified, all agents will be allowed. |
| isConnected | Boolean | If True, only returns agents that are currently connected. If False, only agents that are considered down will be returned, and if not specified, all agents will be returned. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.eam.queryAgentStatus(groupIds, agentIds, isConnected)
```


---



---

# system.eam.runTask

**版本：** 8.1
**型別：** Scripting
**分類：** Eam

## 詳述

This function is used inPython Scripting. Takes the name of a task as an argument as a string (must be configured on the Controller before hand), attempts to execute the task. This function can only be called from the Controller. To run in the client, the user needs arole-based permission. This permission is disabled by default.

## 語法

```python
system.eam.runTask(taskname)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| taskname | String | Name of the task to run. If more than one task has this name, an error will be returned. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.eam.runTask(taskname)
```


---

