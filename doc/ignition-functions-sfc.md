# Ignition 8.1 - system.sfc 函數文檔


## 📑 目錄

---

1. [system.sfc.cancelChart](#systemsfccancelchart) - This function is used inPython Scripting. Cancels the execution of a running chart instance. Any running steps will be told to stop, and the SFC chart will enter Canceling state. Will throw a KeyError if the ID does not match any running chart instance. Permission Type: SFC Management
2. [system.sfc.getRunningCharts](#systemsfcgetrunningcharts) - This function is used inPython Scripting. Retrieves information about running charts. Can search all running charts, or be filtered charts at a specific path. This function will return charts that are in a Paused state. This scripting function has noClient Permissionrestrictions.
3. [system.sfc.getVariables](#systemsfcgetvariables) - This function is used inPython Scripting. Get the variables in a chart instance's scope. Commonly used to check the value of a Chart Parameter, or determine how long the chart has been running for. This scripting function has noClient Permissionrestrictions.
4. [system.sfc.pauseChart](#systemsfcpausechart) - This function is used inPython Scripting. Pauses a running chart instance. Any running steps will be told to pause, and the chart will enter Pausing state. Will throw a KeyError if the ID does not match any running chart instance. Permission Type: SFC Management
5. [system.sfc.redundantCheckpoint](#systemsfcredundantcheckpoint) - This function is used inPython Scripting. Synchronizes chart and step variables of the specified chart instance across a redundant cluster, allowing the chart instance to continue where it left off if a redundant failover occurs. Check outredundancy syncfor more information. Permission Type: SFC Management
6. [system.sfc.resumeChart](#systemsfcresumechart) - This function is used inPython Scripting. Resumes a chart that was paused. Steps which were previously paused will be resumed, and chart will enter Resuming state. Will throw a KeyError if the ID does not match any running chart instance. Permission Type: SFC Management
7. [system.sfc.setVariable](#systemsfcsetvariable) - This function is used inPython Scripting. Sets a variable inside a currently runningSFC chart. Permission Type: SFC Management
8. [system.sfc.setVariables](#systemsfcsetvariables) - This function is used inPython Scripting. Sets any number of variables inside a currently running chart. Permission Type: SFC Management
9. [system.sfc.startChart](#systemsfcstartchart) - This function is used inPython Scripting. Starts a new instance of a chart. The chart must be set to "Callable" execution mode. Permission Type: SFC Management

---

# system.sfc.cancelChart

**版本：** 8.1
**型別：** Scripting
**分類：** Sfc

## 詳述

This function is used inPython Scripting. Cancels the execution of a running chart instance. Any running steps will be told to stop, and the SFC chart will enter Canceling state. Will throw a KeyError if the ID does not match any running chart instance. Permission Type: SFC Management

## 語法

```python
system.sfc.cancelChart(id)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| id | String | The ID of the chart instance to cancel. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.sfc.cancelChart(id)
```

### Example 3

```python
# The following attempts to stop an SFC but will alert the user if the id of the chart is not currently running.
id = 'Some long string value. It can be obtained using system.sfc.getRunningCharts()'
try:
    system.sfc.cancelChart(id)
except:
    system.gui.messageBox("Could not stop the SFC")
```


---



---

# system.sfc.getRunningCharts

**版本：** 8.1
**型別：** Scripting
**分類：** Sfc

## 詳述

This function is used inPython Scripting. Retrieves information about running charts. Can search all running charts, or be filtered charts at a specific path. This function will return charts that are in a Paused state. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.sfc.getRunningCharts([chartPath])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| chartPath | String | The path to a chart to filter on: i.e., "folder/chartName". If specified, only charts at the path will be included in the returned dataset. If omitted, the function will return data for all active charts. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.sfc.getRunningCharts([chartPath])
```

### Example 3

```python
# This example will check for all running charts, and return a formatted string detailing each chart instance.

# Check for all running charts. The path may be specified as a string to filter the results.
data = system.sfc.getRunningCharts()
# Create a string to append chart data to. The "\n" is a new line character.
chartData = "The following charts are running:\n"

# Iterate through each chart
for row in range(data.rowCount):

    # Extract the instanceId and chartPath values from the current row
    runningChartId = data.getValueAt(row, "instanceId")
    runningChartPath = data.getValueAt(row, "chartPath")

    # Append a string to chartData with the values extracted above
    chartData += "Id: %s, Path: %s\n" % (runningChartId, runningChartPath)

# Print the string of chart Id's and Paths
print chartData
```


---



---

# system.sfc.getVariables

**版本：** 8.1
**型別：** Scripting
**分類：** Sfc

## 詳述

This function is used inPython Scripting. Get the variables in a chart instance's scope. Commonly used to check the value of a Chart Parameter, or determine how long the chart has been running for. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.sfc.getVariables(instanceId)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| instanceId | String | The instance identifier of the chart. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.sfc.getVariables(instanceId)
```

### Example 3

```python
# This example will show the chart path and start time of a single chart in a messageBox.
# We can make use of the SFC Monitor component to give the users the ability to pick a single running chart

# Fetch the ID of a running chart. In this case, we used the Instance ID property on a SFC Monitor component
id = event.source.parent.getComponent('SFC Monitor').instanceId

# Retrieve the variables from the chart
chartVars = system.sfc.getVariables(id)

# Show the path and starttime of the chart in a messageBox
system.gui.messageBox("Chart Path: %s has been running since %s" % (chartVars["chartPath"], chartVars["startTime"]))
```


---



---

# system.sfc.pauseChart

**版本：** 8.1
**型別：** Scripting
**分類：** Sfc

## 詳述

This function is used inPython Scripting. Pauses a running chart instance. Any running steps will be told to pause, and the chart will enter Pausing state. Will throw a KeyError if the ID does not match any running chart instance. Permission Type: SFC Management

## 語法

```python
system.sfc.pauseChart(id)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| id | String | The ID of the chart instance to pause |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.sfc.pauseChart(id)
```

### Example 3

```python
# The following attempts to pause a SFC.
id = 'Some long string value. It can be obtained using system.sfc.getRunningCharts()'

system.sfc.cancelChart(id)
```


---



---

# system.sfc.redundantCheckpoint

**版本：** 8.1
**型別：** Scripting
**分類：** Sfc

## 詳述

This function is used inPython Scripting. Synchronizes chart and step variables of the specified chart instance across a redundant cluster, allowing the chart instance to continue where it left off if a redundant failover occurs. Check outredundancy syncfor more information. Permission Type: SFC Management

## 語法

```python
system.sfc.redundantCheckpoint(instanceId)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| instanceId | String | The instance identifier of the chart. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.sfc.redundantCheckpoint(instanceId)
```

### Example 3

```python
# This example will create a redundant checkpoint in case the primary Gateway in the redundant pair fails.
instanceId = "The ID of the chart you want to synchronize across the redundant pair"

system.sfc.redundantCheckpoint(instanceId)
```


---



---

# system.sfc.resumeChart

**版本：** 8.1
**型別：** Scripting
**分類：** Sfc

## 詳述

This function is used inPython Scripting. Resumes a chart that was paused. Steps which were previously paused will be resumed, and chart will enter Resuming state. Will throw a KeyError if the ID does not match any running chart instance. Permission Type: SFC Management

## 語法

```python
system.sfc.resumeChart(id)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| id | String | The ID of the chart instance to resume. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.sfc.resumeChart(id)
```

### Example 3

```python
# The following attempts to resume a paused SFC.
id = "The ID of the SFC you want to resume"

system.sfc.resumeChart(id)
```


---



---

# system.sfc.setVariable

**版本：** 8.1
**型別：** Scripting
**分類：** Sfc

## 詳述

This function is used inPython Scripting. Sets a variable inside a currently runningSFC chart. Permission Type: SFC Management

## 語法

```python
system.sfc.setVariable(instanceId, [stepId], variableName, variableValue)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| instanceId | String | The instance identifier of the chart. |
| stepId | String | The id for a step inside of a chart. If omitted the function will target a chart scoped variable. [optional] |
| variableName | String | The name of the variable to set. |
| variableValue | Object | The value for the variable to be set to. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.sfc.setVariable(instanceId, [stepId], variableName, variableValue)
```


---



---

# system.sfc.setVariables

**版本：** 8.1
**型別：** Scripting
**分類：** Sfc

## 詳述

This function is used inPython Scripting. Sets any number of variables inside a currently running chart. Permission Type: SFC Management

## 語法

```python
system.sfc.setVariables(instanceId, [stepId], variableMap)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| instanceId | String | The instance identifier of the chart. |
| stepId | String | The id for a step inside of a cart. If omitted the function will target a chart scoped variable. [optional] |
| variablesMap | Dictionary[String, Any] | A dictionary containing the name:valuepairs of the variables to set. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.sfc.setVariables(instanceId, [stepId], variableMap)
```


---



---

# system.sfc.startChart

**版本：** 8.1
**型別：** Scripting
**分類：** Sfc

## 詳述

This function is used inPython Scripting. Starts a new instance of a chart. The chart must be set to "Callable" execution mode. Permission Type: SFC Management

## 語法

```python
system.sfc.startChart(projectName, chartPath, parameters)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| projectName | String | The name of the project that the chart was created in. |
| chartPath | String | The path to the chart, for example "ChartFolder/ChartName". |
| parameters | Dictionary[String, Any] | A dictionary of arguments. Each key-value pair in the dictionary becomes a variable in the chart scope and will override any default. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.sfc.startChart(projectName, chartPath, parameters)
```

### Example 2

```python
projectName
```


---

