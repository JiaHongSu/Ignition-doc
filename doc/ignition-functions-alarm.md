# Ignition 8.1 - system.alarm 函數文檔

﻿# Ignition 8.1 - 函數文檔（PATTERN 規範）

> 根據 FUNCTION_PATTERN 爬蟲生成
> 生成時間: 2026年04月19日 00:56:44
> 總計函式數: 434

## 📑 目錄

---

1. [system.alarm.acknowledge](#systemalarmacknowledge) - This function is used inPython Scripting. Acknowledges any number of alarms, specified by their event ids. The event id is generated for an alarm when it becomes active, and it is used to identify a particular event from other events for the same source. The alarms will be acknowledged by the logged in user making the call. Additionally, acknowledgement notes may be included and will be stored along with the acknowledgement. This function uses different parameters based on the scope of the scrip
2. [system.alarm.cancel](#systemalarmcancel) - This function is used inPython Scripting. Cancels any number of alarm pipelines, specified by their event ids. Event ids can be obtains from thesystem.alarm.queryStatusfunction. Canceling a pipeline will not impact the alarm that triggered the pipeline. The alarm will still be active, but will drop out of alarm pipelines. Permission Type: Alarm Management
3. [system.alarm.createRoster](#systemalarmcreateroster) - This function is used inPython Scripting. This function creates a new roster. Users may be added to the roster through the Gateway or the Roster Management component Permission Type: Alarm Management
4. [system.alarm.getRosters](#systemalarmgetrosters) - This function is used inPython Scripting. This function returns a mapping of roster names to a list of usernames contained in the roster. This scripting function has noClient Permissionrestrictions.
5. [system.alarm.getShelvedPaths](#systemalarmgetshelvedpaths) - This function is used inPython Scripting. Returns a list of ShelvedPath objects, which each represent a shelved alarm. This scripting function has noClient Permissionrestrictions.
6. [system.alarm.listPipelines](#systemalarmlistpipelines) - This function is used inPython Scripting. Will return a list of the available Alarm Notification Pipelines in a project. The order of the returned list is not guaranteed. The legacy behavior of this function (7.9 and prior) did not have any parameters, and it would always check all projects for pipelines. Upon upgrade to version 8.#+, alarm pipelines were migrated to a project named "alarm-pipelines". See theUpgrade Guidefor more details.
7. [system.alarm.queryJournal](#systemalarmqueryjournal) - This function is used inPython Scripting. Queries the specified journal for historical alarm events. The result is a list of alarm events, which can be parsed for individual properties. Click herefor more information on alarm properties.
8. [system.alarm.queryStatus](#systemalarmquerystatus) - This function is used inPython Scripting. Queries the current state of alarms. The result is a list of alarm events, which can be parsed for individual properties. The results provided by this function represent the current state of alarms, in contrast to the historical alarm events retrieved by thesystem.alarm.queryJournalfunction. Depending on the number of alarm events in the system, this function can be fairly intensive and take a while to finish executing. This can be problematic if the app
9. [system.alarm.shelve](#systemalarmshelve) - This function is used inPython Scripting. This function shelves the specified alarms for the specified amount of time. The time can be specified in minutes (timeoutMinutes) or seconds (timeoutSeconds). If an alarm is already shelved, this will overwrite the remaining time. If no timeout is specified, will default to 15 minutes. Client Permission: Alarm Management
10. [system.alarm.unshelve](#systemalarmunshelve) - This function is used inPython Scripting. Unshelves a list of alarms based on the source paths provided. Client Permission: Alarm Management

---

# system.alarm.acknowledge

**版本：** 8.1
**型別：** Scripting
**分類：** Alarm

## 詳述

This function is used inPython Scripting. Acknowledges any number of alarms, specified by their event ids. The event id is generated for an alarm when it becomes active, and it is used to identify a particular event from other events for the same source. The alarms will be acknowledged by the logged in user making the call. Additionally, acknowledgement notes may be included and will be stored along with the acknowledgement. This function uses different parameters based on the scope of the scrip

## 語法

```python
system.alarm.acknowledge(alarmIds, [notes])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| alarmIds | String[] | List of alarm event ids (uuids) to acknowledge. |
| notes | String | A string that will be used as the Ack Note on each acknowledged alarm event. If set to None , then an Ack Note note will not be assigned to the alarm event |
| alarmIds | List[String] | List of alarm event ids (UUIDs) to acknowledge. |
| notes | String | A string that will be used as the Ack Note on each acknowledged alarm event. If set to None , then an Ack Note note will not be assigned to the alarm event. |
| username | String | The user that acknowledged the alarm. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.alarm.acknowledge(alarmIds, [notes])
```


---



---

# system.alarm.cancel

**版本：** 8.1
**型別：** Scripting
**分類：** Alarm

## 詳述

This function is used inPython Scripting. Cancels any number of alarm pipelines, specified by their event ids. Event ids can be obtains from thesystem.alarm.queryStatusfunction. Canceling a pipeline will not impact the alarm that triggered the pipeline. The alarm will still be active, but will drop out of alarm pipelines. Permission Type: Alarm Management

## 語法

```python
system.alarm.cancel(alarmIds)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| alarmIds | List[String] | List of alarm pipeline event ids (UUIDs) to cancel. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.alarm.cancel(alarmIds)
```

### Example 3

```python
# This example shows the basic syntax for cancelling an alarm.

system.alarm.cancel(['c27c06d8-698f-4814-af89-3c22944f58c5'])
```


---



---

# system.alarm.createRoster

**版本：** 8.1
**型別：** Scripting
**分類：** Alarm

## 詳述

This function is used inPython Scripting. This function creates a new roster. Users may be added to the roster through the Gateway or the Roster Management component Permission Type: Alarm Management

## 語法

```python
system.alarm.createRoster(name, description)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| name | String | The name for the new roster |
| description | String | A description for the new roster. Required, but can be blank. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.alarm.createRoster(name, description)
```

### Example 3

```python
description
```


---



---

# system.alarm.getRosters

**版本：** 8.1
**型別：** Scripting
**分類：** Alarm

## 詳述

This function is used inPython Scripting. This function returns a mapping of roster names to a list of usernames contained in the roster. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.alarm.getRosters()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.alarm.getRosters()
```

### Example 2

```python
# This script will get all the rosters and list the users in them.
rosters = system.alarm.getRosters()
for key, values in rosters.iteritems():
    # key is the roster name, values is a dict of usernames
    print 'Roster', key, 'contains these users:'
    for value in values:
        print '  ', value
```

### Example 3

```python
# This script will get all the rosters and list the users in them.
rosters = system.alarm.getRosters()
for key, values in rosters.iteritems():
    # key is the roster name, values is a dict of usernames
    print 'Roster', key, 'contains these users:'
    for value in values:
        print '  ', value
```


---



---

# system.alarm.getShelvedPaths

**版本：** 8.1
**型別：** Scripting
**分類：** Alarm

## 詳述

This function is used inPython Scripting. Returns a list of ShelvedPath objects, which each represent a shelved alarm. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.alarm.getShelvedPaths()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.alarm.getShelvedPaths()
```

### Example 2

```python
# The following code prints a list of the shelved alarms paths and prints them to the console.
paths = system.alarm.getShelvedPaths()
for p in paths:
   print "Path: %s, Shelved by: %s, expires: %s, is expired? %s" % (p.getPath(), p.getUser(), p.getExpiration(), p.isExpired())
```

### Example 3

```python
# The following code prints a list of the shelved alarms paths and prints them to the console.
paths = system.alarm.getShelvedPaths()
for p in paths:
   print "Path: %s, Shelved by: %s, expires: %s, is expired? %s" % (p.getPath(), p.getUser(), p.getExpiration(), p.isExpired())
```


---



---

# system.alarm.listPipelines

**版本：** 8.1
**型別：** Scripting
**分類：** Alarm

## 詳述

This function is used inPython Scripting. Will return a list of the available Alarm Notification Pipelines in a project. The order of the returned list is not guaranteed. The legacy behavior of this function (7.9 and prior) did not have any parameters, and it would always check all projects for pipelines. Upon upgrade to version 8.#+, alarm pipelines were migrated to a project named "alarm-pipelines". See theUpgrade Guidefor more details.

## 語法

```python
system.alarm.listPipelines([projectName])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| projectName | String | The project to check alarm pipelines for. If omitted, will look for a project named "alarm-pipelines". [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.alarm.listPipelines([projectName])
```

### Example 2

```python
projectName
```

### Example 3

```python
# This script will print a list of all alarm pipeline names in the current project.
project = system.util.getProjectName()
pipelines = system.alarm.listPipelines(project)
for pipeline in pipelines:
    print pipeline
```


---



---

# system.alarm.queryJournal

**版本：** 8.1
**型別：** Scripting
**分類：** Alarm

## 詳述

This function is used inPython Scripting. Queries the specified journal for historical alarm events. The result is a list of alarm events, which can be parsed for individual properties. Click herefor more information on alarm properties.

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| startDate | Date | The start of the time range to query. Defaults to 8 hours previous to now if omitted. Time range is inclusive. [optional] |
| endDate | Date | The end of the time range to query. Defaults to now if omitted. [optional] |
| journalName | String | The journal name to query. If only one journal exists on the Gateway, can be omitted. [optional] |
| priority | List[Integer/String] | A list of possible priorities to match. Priorities can be specified by name or number, with the values: Diagnostic(0), Low(1), Medium(2), High(3), Critical(4). [optional] |
| state | List[Integer/String] | A list of event states to match. Valid values can either be integers or strings, representing a number of states. SeeState Parameter Valuesfor a listing of possible values. [optional] |
| path | List[String] | A list of possible source paths to search at. The wildcard*may be used. [optional] |
| source | List[String] | A list of possible source paths to search at. The wildcard*may be used. [optional] |
| displaypath | List[String] | A list of display paths to search at. Display paths are separated by/, and if a path ends in/*, everything below that path will be searched as well. [optional] |
| all_properties | List[Tuple[String, String, Any]] | A set of property conditions, all of which must be met for the condition to pass. This parameter is a list of tuples, in the form (propName,condition, value). Valid propName values can be either associated data or the keys listed on thePyAlarmEvent object. Valid condition values:=,!=,<,<=,>,>=. String values can only be compared using=and!=conditions. [optional] |
| any_properties | List[Tuple[String, String, Any]] | A set of property conditions, any of which will cause the overall condition to pass. This parameter is a list of tuples, in the form (propName,condition, value). Valid propName values can be either associated data or the keys listed on thePyAlarmEvent object. Valid condition values:=,!=,<,<=,>,>=. String values can only be compared using=and!=conditions. [optional] |
| defined | List[String] | A list of string property names, all of which must be present on an event for it to pass. [optional] |
| includeData | Boolean | Whether or not event data should be included in the return. If True, returns Python dictionaries (or nulls) for Active, Clear, Ack, Event Value, and Runtime data inside of the AlarmQueryResult object. Not required when definingall_propertiesorany_properties. [optional]SeeExample #6below for how to return Event Value data. |
| includeSystem | Boolean | Specifies whether system events are included in the return. [optional] |
| includeShelved | Boolean | A flag indicating whether shelved events should be included in the results. Defaults to false. [optional] |
| isSystem | Boolean | Specifies whether the returned event must or must not be a system event. [optional] |
| provider | List[String] | A list of tag providers to include in the query. Omitting this parameter will query all providers. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.alarm.queryJournal([startDate], [endDate], [journalName], [priority], [state], [path], [source], [displaypath], [all_properties], [any_properties], [defined], [includeData], [includeSystem], [includeShelved], [isSystem], [provider])
```


---



---

# system.alarm.queryStatus

**版本：** 8.1
**型別：** Scripting
**分類：** Alarm

## 詳述

This function is used inPython Scripting. Queries the current state of alarms. The result is a list of alarm events, which can be parsed for individual properties. The results provided by this function represent the current state of alarms, in contrast to the historical alarm events retrieved by thesystem.alarm.queryJournalfunction. Depending on the number of alarm events in the system, this function can be fairly intensive and take a while to finish executing. This can be problematic if the app

## 語法

```python
system.alarm.queryStatus([priority], [state], [path], [source], [displaypath], [all_properties], [any_properties], [defined], [includeShelved], [provider])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| priority | List[Integer/String] | A list of possible priorities to match. Priorities can be specified by name or number, with the values: Diagnostic(0), Low(1), Medium(2), High(3), Critical(4). [optional] |
| state | List[Integer/String] | A list of states to allow. SeeState Valuesfor a list of options. [optional] |
| path | List[String] | A list of possible source paths to search at. The wildcard*may be used. Works the same as the source argument, and either can be used. [optional] |
| source | List[String] | A list of possible source paths to search at. The wildcard*may be used. Works the same as the path argument, and either can be used. [optional] |
| displaypath | List[String] | A list of display paths to search at. Display paths are separated by/, and if a path ends in/*, everything below that path will be searched as well. [optional] |
| all_properties | List[Tuple[String, String, Any]] | A set of property conditions, all of which must be met for the condition to pass. This parameter is a list of tuples, in the form (propName,condition, value). Valid propName values can be either associated data or the keys listed on thePyAlarmEvent object. Valid condition values:=,!=,<,<=,>,>=. String values can only be compared using=and!=conditions. [optional] |
| any_properties | List[Tuple[String, String, Any]] | A set of property conditions, any of which will cause the overall condition to pass. This parameter is a list of tuples, in the form (propName,condition, value). Valid propName values can be either associated data or the keys listed on thePyAlarmEvent object. Valid condition values:=,!=,<,<=,>,>=. String values can only be compared using=and!=conditions.  [optional] |
| defined | List[String] | A list of string property names, all of which must be present on an event for it to pass. [optional] |
| includeShelved | Boolean | A flag indicating whether shelved events should be included in the results. Defaults to false. [optional] |
| provider | List[String] | A list of tag providers to include in the query. Omitting this parameter will query all providers. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.alarm.queryStatus([priority], [state], [path], [source], [displaypath], [all_properties], [any_properties], [defined], [includeShelved], [provider])
```


---



---

# system.alarm.shelve

**版本：** 8.1
**型別：** Scripting
**分類：** Alarm

## 詳述

This function is used inPython Scripting. This function shelves the specified alarms for the specified amount of time. The time can be specified in minutes (timeoutMinutes) or seconds (timeoutSeconds). If an alarm is already shelved, this will overwrite the remaining time. If no timeout is specified, will default to 15 minutes. Client Permission: Alarm Management

## 語法

```python
system.alarm.shelve(path, [timeoutSeconds], [timeoutMinutes])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| path | List[String] | A list of possible source paths to search at. If a path ends in "/*", the results will include anything below that path. |
| timeoutSeconds | Integer | The amount of time to shelve the matching alarms for, specified in seconds. Setting this to 0 will unshelve the alarms. [optional] |
| timeoutMinutes | Integer | The amount of time to shelve the matching alarms for, specified in minutes. Setting this to 0 will unshelve the alarms. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.alarm.shelve(path, [timeoutSeconds], [timeoutMinutes])
```

### Example 3

```python
timeoutSeconds
```


---



---

# system.alarm.unshelve

**版本：** 8.1
**型別：** Scripting
**分類：** Alarm

## 詳述

This function is used inPython Scripting. Unshelves a list of alarms based on the source paths provided. Client Permission: Alarm Management

## 語法

```python
system.alarm.unshelve(path)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| path | List[String] | A list of possible source paths to search at. If a path ends in "/*", the results will include anything below that path. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.alarm.unshelve(path)
```

### Example 3

```python
# Unshelve an Alarm at a Path

testPath = "prov:TAG_PROVIDER_NAME:/tag:TAG_PATH:/alm:ALARM_NAME"
system.alarm.unshelve(path= [testPath])
```


---

