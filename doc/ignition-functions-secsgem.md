# Ignition 8.1 - system.secsgem 函數文檔


## 📑 目錄

---

1. [system.secsgem.copyEquipment](#systemsecsgemcopyequipment) - This function is used inPython Scripting. Creates a copy of an equipment connection and places it in the Gateway > Config > SECS/GEM > Equipment. Common settings can be overridden for the new connection. An exception is thrown if the new equipment connection cannot be created.
2. [system.secsgem.deleteToolProgram](#systemsecsgemdeletetoolprogram) - This function is used inPython Scripting. Deletes a process program from the Gateway. Permission Type: SECS/GEM Management
3. [system.secsgem.enableDisableEquipment](#systemsecsgemenabledisableequipment) - This function is used inPython Scripting. Enables or disables a Tuple of equipment connections from a script. Permission Type: SECS/GEM Management
4. [system.secsgem.getResponse](#systemsecsgemgetresponse) - This function is used inPython Scripting. Attempts to retrieve a response message from the Gateway. The transaction id from the sent message is used to retrieve the response. This scripting function has noClient Permissionrestrictions.
5. [system.secsgem.getToolProgram](#systemsecsgemgettoolprogram) - This function is used inPython Scripting. Returns a process program from the Gateway that was previously sent by a a tool in an S7F3 message. This scripting function has noClient Permissionrestrictions.
6. [system.secsgem.getToolProgramDataset](#systemsecsgemgettoolprogramdataset) - This function is used inPython Scripting. Returns a Dataset containing information about all stored process programs. This scripting function has noClient Permissionrestrictions.
7. [system.secsgem.sendRequest](#systemsecsgemsendrequest) - This function is used inPython Scripting. Sends a JSON-formatted SECS message to a tool. An equipment connection must be configured for the tool in the Gateway. This scripting function has noClient Permissionrestrictions.
8. [system.secsgem.sendResponse](#systemsecsgemsendresponse) - This function is used inPython Scripting. Sends a JSON-formatted SECS response message to a message sent by a tool. An equipment connection must be configured for the tool in the Gateway, and this must be used within a Message Handler to create aCustom Message Response Handler. This scripting function has noClient Permissionrestrictions.
9. [system.secsgem.startSimEventRun](#systemsecsgemstartsimeventrun) - This function is used inPython Scripting. Starts a configured simulator event run in the Gateway. Note, that this function only works with the simulators that come included with the SECS/GEM module. The function will throw an exception if the specified Event Run cannot be started.
10. [system.secsgem.toDataset](#systemsecsgemtodataset) - This function is used inPython Scripting. Converts a SECS message data structure, as returned by thesystem.secsgem.getResponsefunction, into a dataset and returns it. This scripting function has noClient Permissionrestrictions.
11. [system.secsgem.toTreeDataset](#systemsecsgemtotreedataset) - This function is used inPython Scripting. Changes an existing dataset, as returned by thesystem.secsgem.toDataSetfunction, to make it usable for theTree Viewcomponent. This scripting function has noClient Permissionrestrictions.

---

# system.secsgem.copyEquipment

**版本：** 8.1
**型別：** Scripting
**分類：** Secsgem

## 詳述

This function is used inPython Scripting. Creates a copy of an equipment connection and places it in the Gateway > Config > SECS/GEM > Equipment. Common settings can be overridden for the new connection. An exception is thrown if the new equipment connection cannot be created.

## 語法

```python
system.secsgem.copyEquipment( equipmentSource, newEquipmentName, enabled, activeAddress, activePort, passiveAddress, passivePort, deviceId [, dbTablePrefix] [,description])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| equipmentSource | String | Some new equipment settings will be retrieved from this equipment connection. Specify the source equipment connection name. |
| newEquipmentName | String | The name of the new equipment connection. |
| enabled | Boolean | If set to false, the new equipment connection will be disabled after it is created. |
| activeAddress | String | IP Address of new equipment. Must be specified if the SECS/GEM module is used in Active mode. Otherwise, do not use this parameter. |
| activePort | Integer | Port number of new equipment. Must be specified if the SECS/GEM module is used in Active mode. Otherwise, do not use this parameter. |
| passiveAddress | String | IP Address of new equipment. Must be specified if the SECS/GEM module is used in Passive mode. Otherwise, do not use this parameter. |
| passivePort | Integer | Port number of new equipment. Must be specified if the SECS/GEM module is used in Passive mode. Otherwise, do not use this parameter. |
| deviceId | Integer | Unique identifier of new equipment. This value must be an integer, and is specified within the equipment. |
| dbTablePrefix | String | SECS/GEM database table names will use the specified prefix for the new equipment connection. If no prefix is specified, the description of the source equipment will be used. Optional. |
| description | String | The description for the new equipment connection. If no description is specified, the description of the source equipment will be used. Optional. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.secsgem.copyEquipment( equipmentSource, newEquipmentName, enabled, activeAddress, activePort, passiveAddress, passivePort, deviceId [, dbTablePrefix] [,description])
```

### Example 2

```python
equipmentSource
```

### Example 3

```python
newEquipmentName
```


---



---

# system.secsgem.deleteToolProgram

**版本：** 8.1
**型別：** Scripting
**分類：** Secsgem

## 詳述

This function is used inPython Scripting. Deletes a process program from the Gateway. Permission Type: SECS/GEM Management

## 語法

```python
system.secsgem.deleteToolProgram(ppid)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| ppid | String | The PPID that was sent from the tool when the S7F3 message was saved. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.secsgem.deleteToolProgram(ppid)
```

### Example 3

```python
# Name of the Tool Program that will be deleted
targetProgram = "Old Program"

system.secsgem.deleteToolProgram(targetProgram)
```


---



---

# system.secsgem.enableDisableEquipment

**版本：** 8.1
**型別：** Scripting
**分類：** Secsgem

## 詳述

This function is used inPython Scripting. Enables or disables a Tuple of equipment connections from a script. Permission Type: SECS/GEM Management

## 語法

```python
system.secsgem.enableDisableEquipment(enable, names)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| enable | Boolean | Set to True to enable equipment connections, or set to False to disable them. |
| names | Tuple | A Tuple of Strings. Each String should match an Equipment Connection configured on the Gateway. If this parameter contains the name of an Equipment Connection that does not exist, then a message will be included in the List returned by this function. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.secsgem.enableDisableEquipment(enable, names)
```


---



---

# system.secsgem.getResponse

**版本：** 8.1
**型別：** Scripting
**分類：** Secsgem

## 詳述

This function is used inPython Scripting. Attempts to retrieve a response message from the Gateway. The transaction id from the sent message is used to retrieve the response. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.secsgem.getResponse(transactionID, equipment, [timeout], [poll])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| transactionID | Integer | The transactionID of the request and response. The transactionID is used to retrieve the response. Typically used in conjunction withsystem.secsgem.sendRequestto generate a transactionID. |
| equipment | String | Name of equipment connection. |
| timeout | Integer | Specifies in seconds how long to wait for a response before returning None. If omitted the timeout will be 5 seconds. |
| poll | Integer | Specifies in milliseconds how often to poll the system for a response. If omitted the poll will be 150 milliseconds. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.secsgem.getResponse(transactionID, equipment, [timeout], [poll])
```

### Example 2

```python
transactionID
```


---



---

# system.secsgem.getToolProgram

**版本：** 8.1
**型別：** Scripting
**分類：** Secsgem

## 詳述

This function is used inPython Scripting. Returns a process program from the Gateway that was previously sent by a a tool in an S7F3 message. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.secsgem.getToolProgram(ppid)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| ppid | String | The PPID that was sent from the tool when the S7F3 message was saved. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.secsgem.getToolProgram(ppid)
```


---



---

# system.secsgem.getToolProgramDataset

**版本：** 8.1
**型別：** Scripting
**分類：** Secsgem

## 詳述

This function is used inPython Scripting. Returns a Dataset containing information about all stored process programs. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.secsgem.getToolProgramDataset()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.secsgem.getToolProgramDataset()
```


---



---

# system.secsgem.sendRequest

**版本：** 8.1
**型別：** Scripting
**分類：** Secsgem

## 詳述

This function is used inPython Scripting. Sends a JSON-formatted SECS message to a tool. An equipment connection must be configured for the tool in the Gateway. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.secsgem.sendRequest(streamFunction, reply, body, equipment)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| streamFunction | String | The stream and function of the SECS message to send. Example: "S1F13" |
| reply | Boolean | Whether or not the SECS message expects a reply message. |
| body | Object | This contains the body of a SECS message. The argument can be a Python Object or JSON string representing the body of a SECS message. If this argument is a string then it will be converted to a Python Object using thesystem.util.jsonDecodefunction. |
| equipment | String | Name of the equipment connection to use. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.secsgem.sendRequest(streamFunction, reply, body, equipment)
```

### Example 2

```python
streamFunction
```


---



---

# system.secsgem.sendResponse

**版本：** 8.1
**型別：** Scripting
**分類：** Secsgem

## 詳述

This function is used inPython Scripting. Sends a JSON-formatted SECS response message to a message sent by a tool. An equipment connection must be configured for the tool in the Gateway, and this must be used within a Message Handler to create aCustom Message Response Handler. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.secsgem.sendResponse(transactionID, systemBytes, streamFunction, body, equipment)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| transactionID | Integer | The TxID of the response. The TxID from the received request in the payload of the message handler must be specified here. |
| systemBytes | Integer | The SystemBytes of the response. The SystemBytes from the received request in the payload of the message handler must be specified here. |
| streamFunction | String | The stream and function of the SECS message to send. Example: "S1F14" |
| body | Any | This contains the body of a SECS response. The argument can be a Python Object or JSON string representing the body of a SECS message. If this argument is a string then it will be converted to a Python Object using thesystem.util.jsonDecodefunction. |
| equipment | String | Name of the equipment connection to use. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.secsgem.sendResponse(transactionID, systemBytes, streamFunction, body, equipment)
```

### Example 2

```python
transactionID
```

### Example 3

```python
systemBytes
```


---



---

# system.secsgem.startSimEventRun

**版本：** 8.1
**型別：** Scripting
**分類：** Secsgem

## 詳述

This function is used inPython Scripting. Starts a configured simulator event run in the Gateway. Note, that this function only works with the simulators that come included with the SECS/GEM module. The function will throw an exception if the specified Event Run cannot be started.

## 語法

```python
system.secsgem.startSimEventRun(simulatorName, eventRunName)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| simulatorName | String | The simulator that holds the configured event run. Will throw an exception if the specified simulator can't be found. |
| eventRunName | String | The event run to start. Will throw an exception if the specified simulator can't be found. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.secsgem.startSimEventRun(simulatorName, eventRunName)
```

### Example 2

```python
simulatorName
```

### Example 3

```python
eventRunName
```


---



---

# system.secsgem.toDataset

**版本：** 8.1
**型別：** Scripting
**分類：** Secsgem

## 詳述

This function is used inPython Scripting. Converts a SECS message data structure, as returned by thesystem.secsgem.getResponsefunction, into a dataset and returns it. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.secsgem.toDataset(secsObject)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| secsObject | Any | A Python object, such as Sequence or a Dictionary, representing a SECS message to convert to a dataset. More information on how to format the Python object can be found on theSECS Definition Language (SDL) Filepage. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.secsgem.toDataset(secsObject)
```

### Example 3

```python
# Receive a SECS message.
object = system.secsgem.getResponse(transactionID, "myEquipment", 2)

# Turn the message into a dataset.
dataset = system.secsgem.toDataSet(object)

# Assuming this script was called from a component script, and a Table component was in the same container as the component that called this script, we could pass
# the dataset to the Data property.
event.source.parent.getComponent('Table').data = dataset
```


---



---

# system.secsgem.toTreeDataset

**版本：** 8.1
**型別：** Scripting
**分類：** Secsgem

## 詳述

This function is used inPython Scripting. Changes an existing dataset, as returned by thesystem.secsgem.toDataSetfunction, to make it usable for theTree Viewcomponent. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.secsgem.toTreeDataset(dataset)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| dataset | Dataset | A DataSet containing a SECS message. Note that this parameter cannot take a JSON message, so the object returned bysystem.secsgem.getResponsemust first be processed bysystem.secsgem.toDataSet. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.secsgem.toTreeDataset(dataset)
```

### Example 3

```python
# Assuming the variable named "message" contains a SECS message, we will first convert it to a Dataset.
dataset = system.secsgem.toDataset(message)

# The initial dataset generated by toDataSet will not work with the Tree View component, so we'll modify it...
dataset = system.secsgem.toTreeDataset(dataset)

# ...and now pass the dataset into the Tree View component's data property.
event.source.parent.getComponent('Tree View').data = dataset
```


---

