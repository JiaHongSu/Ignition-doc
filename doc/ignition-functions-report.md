# Ignition 8.1 - system.report 函數文檔


## 📑 目錄

---

1. [system.report.executeAndDistribute](#systemreportexecuteanddistribute) - This function is used inPython Scripting. Executes and distributes a report. Similar toscheduling a report to execute, except a schedule is not required to utilize this function. This is a great way to distribute the report on demand from a Client. Throws an IllegalArgumentException when any of the following occurs: If the file type is not recognized, path does not exist, project does not exist, or a key is not valid. The function system.report.executeAndDistribute() does not run on its own thre
2. [system.report.executeReport](#systemreportexecutereport) - This function is used inPython Scripting. Immediately executes an existing report and returns a List[Byte] of the output. Throws an IllegalArgumentException when any of the following occurs: If the file type is not recognized, path does not exist, project does not exist. This scripting function has noClient Permissionrestrictions.
3. [system.report.getReportNamesAsDataset](#systemreportgetreportnamesasdataset) - This function is used inPython Scripting. Gets a data of all reports for a project. Throws an IllegalArgumentException when any of the following occurs: If the project name is omitted in the Gateway scope, project does not exist. This scripting function has noClient Permissionrestrictions.
4. [system.report.getReportNamesAsList](#systemreportgetreportnamesaslist) - This function is used inPython Scripting. Gets a list of all reports for a project. Throws an IllegalArgumentException when any of the following occurs: If the project name is omitted in the Gateway scope or if project does not exist. This scripting function has noClient Permissionrestrictions.

---

# system.report.executeAndDistribute

**版本：** 8.1
**型別：** Scripting
**分類：** Report

## 詳述

This function is used inPython Scripting. Executes and distributes a report. Similar toscheduling a report to execute, except a schedule is not required to utilize this function. This is a great way to distribute the report on demand from a Client. Throws an IllegalArgumentException when any of the following occurs: If the file type is not recognized, path does not exist, project does not exist, or a key is not valid. The function system.report.executeAndDistribute() does not run on its own thre

## 語法

```python
system.report.executeAndDistribute(path, project, [parameters], action, [actionSettings])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| path | String | The path to the existing report. |
| project | String | The name of the project where the report is located. Optional in client scope. |
| parameters | Dictionary[String, Integer] | A dictionary of parameter overrides, in the form name:valuepairs. [optional] |
| action | String | The name of the distribution action to use. The action parameter supports the following keys as strings:emailprintsaveftp |
| actionSettings | Dictionary[List, Any] | A dictionary of settings particular to the action. Missing values will use the default value for that action. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.report.executeAndDistribute(path, project, [parameters], action, [actionSettings])
```


---



---

# system.report.executeReport

**版本：** 8.1
**型別：** Scripting
**分類：** Report

## 詳述

This function is used inPython Scripting. Immediately executes an existing report and returns a List[Byte] of the output. Throws an IllegalArgumentException when any of the following occurs: If the file type is not recognized, path does not exist, project does not exist. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.report.executeReport(path, project, [parameters], fileType)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| path | String | The path to the existing report. |
| project | String | The name of the project where the report is located. Optional in client scope. |
| parameters | Dictionary[String, Integer] | A dictionary of parameter overrides, in the form name:value. [optional] |
| fileType | String | The file type the resulting byte array should represent. Defaults to "pdf". Not case-sensitive |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.report.executeReport(path, project, [parameters], fileType)
```


---



---

# system.report.getReportNamesAsDataset

**版本：** 8.1
**型別：** Scripting
**分類：** Report

## 詳述

This function is used inPython Scripting. Gets a data of all reports for a project. Throws an IllegalArgumentException when any of the following occurs: If the project name is omitted in the Gateway scope, project does not exist. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.report.getReportNamesAsDataset([ project], [includeReportName])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| project | String | The name of the project where the reports are located. Optional in client scope. |
| includeReportName | Boolean | New in8.1.5When set to False, the end of Path does not include the report name. Default is True. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.report.getReportNamesAsDataset([ project], [includeReportName])
```

### Example 3

```python
includeReportName
```


---



---

# system.report.getReportNamesAsList

**版本：** 8.1
**型別：** Scripting
**分類：** Report

## 詳述

This function is used inPython Scripting. Gets a list of all reports for a project. Throws an IllegalArgumentException when any of the following occurs: If the project name is omitted in the Gateway scope or if project does not exist. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.report.getReportNamesAsList(project)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| project | String | The name of the project where the reports are located. Optional in Client scope and Perspective Session scope. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.report.getReportNamesAsList(project)
```

### Example 3

```python
# Gets a list of reports for the current project and prints it.
reports = system.report.getReportNamesAsList()
for report in reports:
    print report

"""Output from the above example looks like the following:
Comparisons
Line Reports/Line 1/Defect rates
Line Reports/Line 1/Production
Line Reports/Line 2/Defect Rates
"""
```


---

