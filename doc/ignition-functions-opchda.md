# Ignition 8.1 - system.opchda 函數文檔

﻿# Ignition 8.1 - 函數文檔（PATTERN 規範）

> 根據 FUNCTION_PATTERN 爬蟲生成
> 生成時間: 2026年04月19日 00:56:44
> 總計函式數: 434

## 📑 目錄

---

1. [system.opchda.browse](#systemopchdabrowse) - This function is used inPython Scripting. Performs a browse at the given root. This scripting function has noClient Permissionrestrictions.
2. [system.opchda.getAggregates](#systemopchdagetaggregates) - This function is used inPython Scripting. Will query the server for aggregates that it supports. This scripting function has noClient Permissionrestrictions.
3. [system.opchda.getAttributes](#systemopchdagetattributes) - This function is used inPython Scripting. Queries the given server for the item attributes that are available withsystem.opchda.readAttributes(). This scripting function has noClient Permissionrestrictions.
4. [system.opchda.getServers](#systemopchdagetservers) - This function is used inPython Scripting. Returns a list of the OPC-HDA servers configured on the system. This call will return all configured and enabled servers, including those that are not currently connected. This scripting function has noClient Permissionrestrictions.
5. [system.opchda.insert](#systemopchdainsert) - This function is used inPython Scripting. Insert values on the OPC-HDA server. Permission Type: OPC Server Management
6. [system.opchda.insertReplace](#systemopchdainsertreplace) - This function is used inPython Scripting. Will insert values on the OPC-HDA server, or replace them if they already exist. Permission Type: OPC Server Management
7. [system.opchda.isServerAvailable](#systemopchdaisserveravailable) - This function is used inPython Scripting. Checks to see if the specified OPC-HDA server is defined, enabled, and connected. This scripting function has noClient Permissionrestrictions.
8. [system.opchda.readAttributes](#systemopchdareadattributes) - This function is used inPython Scripting. Reads the specified attributes for the given item over a time range. Attributes and their IDs are defined in the OPC-HDA specification, and can be discovered by callingsystem.opchda.getAttributes(). This scripting function has noClient Permissionrestrictions.
9. [system.opchda.readProcessed](#systemopchdareadprocessed) - This function is used inPython Scripting. Reads processed values from the OPC-HDA server. Processed values are calculated values, based on the aggregate function requested for each item. The list of aggregates can be obtained by callingsystem.opchda.getAggregates(). This scripting function has noClient Permissionrestrictions.
10. [system.opchda.readRaw](#systemopchdareadraw) - This function is used inPython Scripting. Reads raw values from the OPC-HDA server. This scripting function has noClient Permissionrestrictions.
11. [system.opchda.replace](#systemopchdareplace) - This function is used inPython Scripting. Replaces values on the OPC-HDA server if the given item ID exists. Permission Type: OPC Server Management

---

# system.opchda.browse

**版本：** 8.1
**型別：** Scripting
**分類：** Opchda

## 詳述

This function is used inPython Scripting. Performs a browse at the given root. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.opchda.browse(root)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| root | String | The root at which to browse. Needs to be a qualified path. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.opchda.browse(root)
```


---



---

# system.opchda.getAggregates

**版本：** 8.1
**型別：** Scripting
**分類：** Opchda

## 詳述

This function is used inPython Scripting. Will query the server for aggregates that it supports. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.opchda.getAggregates(serverName)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| serverName | String | The name of the definedOPC-HDAserver to query. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.opchda.getAggregates(serverName)
```


---



---

# system.opchda.getAttributes

**版本：** 8.1
**型別：** Scripting
**分類：** Opchda

## 詳述

This function is used inPython Scripting. Queries the given server for the item attributes that are available withsystem.opchda.readAttributes(). This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.opchda.getAttributes(serverName)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| serverName | String | The name of the defined OPC-HDA server to query. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.opchda.getAttributes(serverName)
```

### Example 3

```python
# This example gets the description of a Matrikon OPC HDA explorer
# Declare a OPC HDA variable using the system function and prints out the results
opcHda = system.opchda.getAttributes('Matrikon HDA')
print opcHda

# Use the getDesc() method to get the description of the attribute and print out the result
getDesc = hda[1].getDesc()
print getDesc
```


---



---

# system.opchda.getServers

**版本：** 8.1
**型別：** Scripting
**分類：** Opchda

## 詳述

This function is used inPython Scripting. Returns a list of the OPC-HDA servers configured on the system. This call will return all configured and enabled servers, including those that are not currently connected. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.opchda.getServers()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.opchda.getServers()
```

### Example 2

```python
# This example will get a list of OPC HDA servers
system.opchda.getServers()
```

### Example 3

```python
# This example will get a list of OPC HDA servers
system.opchda.getServers()
```


---



---

# system.opchda.insert

**版本：** 8.1
**型別：** Scripting
**分類：** Opchda

## 詳述

This function is used inPython Scripting. Insert values on the OPC-HDA server. Permission Type: OPC Server Management

## 語法

```python
system.opchda.insert(serverName, itemId, value, date, quality)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| serverName | String | The name of the defined OPC-HDA server. |
| itemId | String | The item ID to perform the operation on. |
| value | Any | The value to insert. |
| date | Any | The date to insert. |
| quality | Integer | The quality to insert. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.opchda.insert(serverName, itemId, value, date, quality)
```


---



---

# system.opchda.insertReplace

**版本：** 8.1
**型別：** Scripting
**分類：** Opchda

## 詳述

This function is used inPython Scripting. Will insert values on the OPC-HDA server, or replace them if they already exist. Permission Type: OPC Server Management

## 語法

```python
system.opchda.insertReplace(serverName, itemId, value, date, quality)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| serverName | String | The name of the defined OPC-HDA server. |
| itemId | String | The item ID to perform the operation on. |
| value | Object | The value to insert or replace. |
| date | Object | The date to insert or replace. |
| quality | QualityCode | The quality to insert or replace. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.opchda.insertReplace(serverName, itemId, value, date, quality)
```


---



---

# system.opchda.isServerAvailable

**版本：** 8.1
**型別：** Scripting
**分類：** Opchda

## 詳述

This function is used inPython Scripting. Checks to see if the specified OPC-HDA server is defined, enabled, and connected. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.opchda.isServerAvailable()
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| serverName | String | The name of the OPC-HDA server to check. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.opchda.isServerAvailable()
```

### Example 3

```python
# This example will check to see if there is an OPC HDA server called "ServerName" available.
system.opchda.isServerAvailable(“ServerName”)
```


---



---

# system.opchda.readAttributes

**版本：** 8.1
**型別：** Scripting
**分類：** Opchda

## 詳述

This function is used inPython Scripting. Reads the specified attributes for the given item over a time range. Attributes and their IDs are defined in the OPC-HDA specification, and can be discovered by callingsystem.opchda.getAttributes(). This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.opchda.readAttributes(serverName, itemId, attributeIds, startDate, endDate)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| serverName | String | The name of the defined OPC-HDA server to read. |
| itemId | String | The itemID to retrieve attributes for. |
| attributeIds | List[String] | The integer IDs of the attributes to read. The attribute ids are defined in the OPC-HDA specification. The attributes can also be obtained by callingsystem.opchda.getAttributes(). Some servers may not support all attributes. |
| startDate | String (can be other data types, such as int) | The starting date/time of the query. |
| endDate | String (can be other data types, such as int) | The ending date/time of the query. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.opchda.readAttributes(serverName, itemId, attributeIds, startDate, endDate)
```


---



---

# system.opchda.readProcessed

**版本：** 8.1
**型別：** Scripting
**分類：** Opchda

## 詳述

This function is used inPython Scripting. Reads processed values from the OPC-HDA server. Processed values are calculated values, based on the aggregate function requested for each item. The list of aggregates can be obtained by callingsystem.opchda.getAggregates(). This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.opchda.readProcessed(serverName, itemIds, startDate, endDate, resampleIntervalMS, aggregates)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| serverName | String | The name of the defined OPC-HDA server to read. |
| itemIds | List[String] | A list of item ids to read. |
| startDate | Any | The starting date/time of the query. |
| endDate | Any | The ending date/time of the query. |
| resampleIntervalMS | Integer | The interval, in milliseconds, that each value should cover. |
| aggregates | List[Integer] | A list which should be one-to-one with the item ids requested, specifying the integer id of the aggregation function to use. The aggregation ids are defined in the OPC-HDA specification. The list of aggregates can also be obtained by callingsystem.opchda.getAggregates(). |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.opchda.readProcessed(serverName, itemIds, startDate, endDate, resampleIntervalMS, aggregates)
```


---



---

# system.opchda.readRaw

**版本：** 8.1
**型別：** Scripting
**分類：** Opchda

## 詳述

This function is used inPython Scripting. Reads raw values from the OPC-HDA server. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.opchda.readRaw(serverName, itemIds, startDate, endDate, maxValues, boundingValues)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| serverName | String | The name of the defined OPC-HDA server to read. |
| itemIds | List | A list of item ids to read. |
| startDate | Object | The starting date/time of the query. |
| endDate | Object | The ending date/time of the query. |
| maxValues | Integer | The maximum number of values to return. 0 or less means unlimited. |
| boundingValues | Boolean | A boolean indicating whether or not the "bounding values" should be included in the result set. The bounding values provide a value exactly at the start and end dates, but may be resource-intensive to retrieve. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.opchda.readRaw(serverName, itemIds, startDate, endDate, maxValues, boundingValues)
```


---



---

# system.opchda.replace

**版本：** 8.1
**型別：** Scripting
**分類：** Opchda

## 詳述

This function is used inPython Scripting. Replaces values on the OPC-HDA server if the given item ID exists. Permission Type: OPC Server Management

## 語法

```python
system.opchda.replace(serverName, itemId, value, date, quality)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| serverName | String | The name of the defined OPC-HDA server. |
| itemId | String | The item ID to perform the operation on. |
| value | Object | The value to replace. |
| date | Object | The date to replace. |
| quality | Integer | The quality to replace. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.opchda.replace(serverName, itemId, value, date, quality)
```


---

