# Ignition 8.1 - system.opcua 函數文檔

﻿# Ignition 8.1 - 函數文檔（PATTERN 規範）

> 根據 FUNCTION_PATTERN 爬蟲生成
> 生成時間: 2026年04月19日 00:56:44
> 總計函式數: 434

## 📑 目錄

---

1. [system.opcua.addConnection](#systemopcuaaddconnection) - This function is used inPython Scripting. Adds a new OPC UA connection.
2. [system.opcua.callMethod](#systemopcuacallmethod) - This function is used inPython Scripting. Calls a method in an OPC UA server. To make the most of this function, you'll need to be familiar with methods in theOPC UA server. This scripting function has noClient Permissionrestrictions.
3. [system.opcua.removeConnection](#systemopcuaremoveconnection) - This function is used inPython Scripting. Removes an OPC UA Connection.

---

# system.opcua.addConnection

**版本：** 8.1
**型別：** Scripting
**分類：** Opcua

## 詳述

This function is used inPython Scripting. Adds a new OPC UA connection.

## 語法

```python
system.opcua.addConnection(name, description, discoveryUrl, endpointUrl, securityPolicy, securityMode, settings)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| name | String | Name to assign to the new connection. |
| description | String | Description assigned to the new OPC UA connection. |
| discoveryUrl | String | Endpoint URL to use for discovery services. |
| endpointUrl | String | Endpoint URL to use for session services. |
| securityPolicy | String | The name of the SecurityPolicy to use. See the Security Policy table below for possible values. |
| securityMode | String | The name of the MessageSecurityMode to use. See the Message Security Mode table below for possible values. |
| settings | Dictionary[String, Any] | A dictionary of additional settings to apply to the connection. See the Settings table for a table of possible keys. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.opcua.addConnection(name, description, discoveryUrl, endpointUrl, securityPolicy, securityMode, settings)
```

### Example 3

```python
description
```


---



---

# system.opcua.callMethod

**版本：** 8.1
**型別：** Scripting
**分類：** Opcua

## 詳述

This function is used inPython Scripting. Calls a method in an OPC UA server. To make the most of this function, you'll need to be familiar with methods in theOPC UA server. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.opcua.callMethod(connectionName, objectId, methodId, inputs)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| connectionName | String | The name of the OPC UA connection to the server that the method resides in. |
| objectId | String | The NodeId of the Object Node the Method is a member of. |
| methodId | String | The NodeId of the Method Node to call. |
| inputs | List | A list of input values expected by the method. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.opcua.callMethod(connectionName, objectId, methodId, inputs)
```

### Example 2

```python
connectionName
```


---



---

# system.opcua.removeConnection

**版本：** 8.1
**型別：** Scripting
**分類：** Opcua

## 詳述

This function is used inPython Scripting. Removes an OPC UA Connection.

## 語法

```python
system.opcua.removeConnection(name)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| name | String | The name of the OPC UA connection to remove. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.opcua.removeConnection(name)
```


---

