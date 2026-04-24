# Ignition 8.1 - system.iec61850 函數文檔


## 📑 目錄

---

1. [system.iec61850.cancel](#systemiec61850cancel) - This function is used inPython Scripting. Cancels the selection of an SBO type control on a configured IEC 61850 device to prevent theoperatecommand from performing.
2. [system.iec61850.getControlParams](#systemiec61850getcontrolparams) - This function is used inPython Scripting. This function returns a list of report control names and their attributes contained in the configured IEC 61850 device.
3. [system.iec61850.listFiles](#systemiec61850listfiles) - This function is used inPython Scripting. This function returns a list of filenames from a remote path for the configured IEC 61850 device.
4. [system.iec61850.operate](#systemiec61850operate) - This function is used inPython Scripting. This function operates on the IEC 61850 device control immediately, such as to change the position of a switch. This can be done directly, or following a select command.
5. [system.iec61850.readFile](#systemiec61850readfile) - This function is used inPython Scripting. This function downloads remote files from the configured IEC 61850 device to an identified local path.
6. [system.iec61850.select](#systemiec61850select) - This function is used inPython Scripting. Select an SBO type control to prepare it for a subsequentoperatecommand for a configured IEC 61850 device. These selections can be removed by using thecancelfunction.
7. [system.iec61850.writeFile](#systemiec61850writefile) - This function is used inPython Scripting. This function uploads a file from a local path to the configured IEC 61850 device remote path.

---

# system.iec61850.cancel

**版本：** 8.1
**型別：** Scripting
**分類：** Iec61850

## 詳述

This function is used inPython Scripting. Cancels the selection of an SBO type control on a configured IEC 61850 device to prevent theoperatecommand from performing.

## 語法

```python
system.iec81650.cancel(deviceName, mapParams)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the configured IEC 61850 device. |
| mapParams | PyDictionary | Control parameters dictionary that requires the following keys to be specified: name, T, orCat, orIdent, Check, and Test. These keys must match the params from the select function. If you do not know the required key value pairs, they can be found using thegetControlParamsfunction. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.iec81650.cancel(deviceName, mapParams)
```


---



---

# system.iec61850.getControlParams

**版本：** 8.1
**型別：** Scripting
**分類：** Iec61850

## 詳述

This function is used inPython Scripting. This function returns a list of report control names and their attributes contained in the configured IEC 61850 device.

## 語法

```python
system.iec81650.getControlParams(deviceName)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the configured IEC 61850 device. |

## 回傳值

**型別：** Object

## 範例

### Example 2

```python
system.iec81650.getControlParams(deviceName)
```


---



---

# system.iec61850.listFiles

**版本：** 8.1
**型別：** Scripting
**分類：** Iec61850

## 詳述

This function is used inPython Scripting. This function returns a list of filenames from a remote path for the configured IEC 61850 device.

## 語法

```python
system.iec61850.listFiles(deviceName, remoteFilePath)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the configured IEC 61850 device. |
| remoteFilePath | String | The remote file path on the server of the configured IEC 61850 device for the file to read. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.iec61850.listFiles(deviceName, remoteFilePath)
```

### Example 3

```python
remoteFilePath
```


---



---

# system.iec61850.operate

**版本：** 8.1
**型別：** Scripting
**分類：** Iec61850

## 詳述

This function is used inPython Scripting. This function operates on the IEC 61850 device control immediately, such as to change the position of a switch. This can be done directly, or following a select command.

## 語法

```python
system.iec61850.operate(deviceName, mapParams, controlValue)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the configured IEC 61850 device. |
| mapParams | PyDictionary | Control parameters dictionary that requires the following keys to be specified: name, T, orCat, orIdent, Check, and Test. Use the same params as theselectfunction when operating on an SBO type control. If you do not know the required key value pairs, they can be found using thegetControlParamsfunction. |
| controlValue | Float | Control value (32-bit float). |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.iec61850.operate(deviceName, mapParams, controlValue)
```


---



---

# system.iec61850.readFile

**版本：** 8.1
**型別：** Scripting
**分類：** Iec61850

## 詳述

This function is used inPython Scripting. This function downloads remote files from the configured IEC 61850 device to an identified local path.

## 語法

```python
system.iec61850.readFile(deviceName, remoteFilePath, localFilePath)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the configured IEC 61850 device. |
| remoteFilePath | String | The remote file path on the server of the file to read. |
| localFilePath | String | The local file path on client to store the file contents. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.iec61850.readFile(deviceName, remoteFilePath, localFilePath)
```

### Example 3

```python
remoteFilePath
```


---



---

# system.iec61850.select

**版本：** 8.1
**型別：** Scripting
**分類：** Iec61850

## 詳述

This function is used inPython Scripting. Select an SBO type control to prepare it for a subsequentoperatecommand for a configured IEC 61850 device. These selections can be removed by using thecancelfunction.

## 語法

```python
system.iec61850.select(device_name, mapParams, value)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the configured IEC 61850 device. |
| mapParams | PyDictionary | Control parameters dictionary that requires the following keys to be specified: name, T, orCat, orIdent, Check, and Test. If you do not know the required key value pairs, they can be found using thegetControlParamsfunction. |
| controlValue | Float | Control value (32-bit float). |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.iec61850.select(device_name, mapParams, value)
```


---



---

# system.iec61850.writeFile

**版本：** 8.1
**型別：** Scripting
**分類：** Iec61850

## 詳述

This function is used inPython Scripting. This function uploads a file from a local path to the configured IEC 61850 device remote path.

## 語法

```python
system.iec61850.writeFile(deviceName, localFilePath, remoteFilePath)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the configured IEC 61850 device. |
| localFilePath | String | The local file path on client to pull the file contents from. |
| remoteFilePath | String | The remote file path on the server of the file to write to. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.iec61850.writeFile(deviceName, localFilePath, remoteFilePath)
```

### Example 3

```python
localFilePath
```


---

