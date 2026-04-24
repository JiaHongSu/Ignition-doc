# Ignition 8.1 - system.bacnet 函數文檔

## 📑 目錄

---

1. [system.bacnet.readRaw](#systembacnetreadraw) - This function is used inPython Scripting. Read from any BACnet object not explicitly supported by the BACnet driver. To use this function, theBACnetdriver must be installed.
2. [system.bacnet.readRawMultiple](#systembacnetreadrawmultiple) - This function is used inPython Scripting. This function is the bulk version ofsystem.bacnet.readRawto allow multiple object/property combinations to be read simultaneously from a single request. Returns a list of corresponding Encodable objects provided equal-length lists of object types, object instance numbers, property IDs, and property array indices. To use this function, theBACnetdriver must be installed.
3. [system.bacnet.synchronizeTime](#systembacnetsynchronizetime) - This function is used inPython Scripting. Notifies the remote device of the correct current time, which is the system time (factoring in time zone and DST) of the server Ignition is running on. To use this function, theBACnetdriver must be installed.
4. [system.bacnet.synchronizeTimeUtc](#systembacnetsynchronizetimeutc) - This function is used inPython Scripting. Notifies the remote device of the correct current time in UTC. To use this function, theBACnetdriver must be installed.
5. [system.bacnet.writeRaw](#systembacnetwriteraw) - This function is used inPython Scripting. Write to any BACnet object not explicitly supported by the BACnet driver.
6. [system.bacnet.writeRawMultiple](#systembacnetwriterawmultiple) - This function is used inPython Scripting. This function is the bulk version ofsystem.bacnet.writeRawby writing properties to objects provided equal-length lists of object types, object instance numbers, property IDs, values, priorities, and property array indices. The system.bacnet.writeRawMultiple() function will accept Encodable values on the value parameter.
7. [system.bacnet.writeWithPriority](#systembacnetwritewithpriority) - This function is used inPython Scripting. Write to the Present_Value attribute of an object with a custom priority level. To use this function, theBACnetdriver must be installed.

---

# system.bacnet.readRaw

**版本：** 8.1
**型別：** Scripting
**分類：** Bacnet

## 詳述

This function is used inPython Scripting. Read from any BACnet object not explicitly supported by the BACnet driver. To use this function, theBACnetdriver must be installed.

## 語法

```python
system.bacnet.readRaw(deviceName, objectType, objectId, propertyId, [propertyArrayIndex])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the configured BACnet/IP device instance to read from. |
| objectType | ObjectType | The numeric id of the objectType of the object instance being read from. See the objectType Reference below. |
| objectId | Integer | The object instance number to read. |
| propertyId | PropertyIdentifier | The PropertyIdentifier of the object instance being read. See the propertyId Reference below. |
| propertyArrayIndex | Integer | [optional] The array index of the property to read from. This parameter is optional and should not be used when reading from the entire array or if the property is not an array. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.bacnet.readRaw(deviceName, objectType, objectId, propertyId, [propertyArrayIndex])
```


---



---

# system.bacnet.readRawMultiple

**版本：** 8.1
**型別：** Scripting
**分類：** Bacnet

## 詳述

This function is used inPython Scripting. This function is the bulk version ofsystem.bacnet.readRawto allow multiple object/property combinations to be read simultaneously from a single request. Returns a list of corresponding Encodable objects provided equal-length lists of object types, object instance numbers, property IDs, and property array indices. To use this function, theBACnetdriver must be installed.

## 語法

```python
system.bacnet.readRawMultiple(deviceName, objectTypes, objectIds, propertyIds)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the configured BACnet/IP device instance to read from. |
| objectTypes | ObjectTypes | The numeric ids of the objectType of the object instances being read from. See the objectType Reference below. |
| objectIds | Integer | The object instance number to read. |
| propertyIds | PropertyIdentifier | The PropertyIdentifier of the object instance being read. See the propertyId Reference below. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.bacnet.readRawMultiple(deviceName, objectTypes, objectIds, propertyIds)
```

### Example 3

```python
objectTypes
```


---



---

# system.bacnet.synchronizeTime

**版本：** 8.1
**型別：** Scripting
**分類：** Bacnet

## 詳述

This function is used inPython Scripting. Notifies the remote device of the correct current time, which is the system time (factoring in time zone and DST) of the server Ignition is running on. To use this function, theBACnetdriver must be installed.

## 語法

```python
system.bacnet.synchronizeTime(deviceName)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the configured BACnet/IP device instance to write from. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.bacnet.synchronizeTime(deviceName)
```

### Example 3

```python
deviceName = "BACnet Remote"
system.bacnet.synchronizeTime(deviceName)
```


---



---

# system.bacnet.synchronizeTimeUtc

**版本：** 8.1
**型別：** Scripting
**分類：** Bacnet

## 詳述

This function is used inPython Scripting. Notifies the remote device of the correct current time in UTC. To use this function, theBACnetdriver must be installed.

## 語法

```python
system.bacnet.synchronizeTimeUtc(deviceName)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the configured BACnet/IP device instance to write from. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.bacnet.synchronizeTimeUtc(deviceName)
```

### Example 3

```python
deviceName = "BACnet Remote"
system.bacnet.synchronizeTimeUtc(deviceName)
```


---



---

# system.bacnet.writeRaw

**版本：** 8.1
**型別：** Scripting
**分類：** Bacnet

## 詳述

This function is used inPython Scripting. Write to any BACnet object not explicitly supported by the BACnet driver.

## 語法

```python
system.bacnet.writeRaw(deviceName, objectType, objectId, propertyId, value, [priority], [propertyArrayIndex])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the configured BACnet/IP device instance to write from. |
| objectType | ObjectType | The numeric id of the objectType of the object instance being written to. See the objectType Reference below. |
| objectId | Integer | The object instance number to write to. |
| propertyId | PropertyIdentifier | The PropertyIdentifier of the object instance being written to. See the propertyId Reference below. |
| value | Object | The value to write. Clearing a value can be accomplished by writing a None value. |
| priority | Integer | [optional] The priority level to use when writing to commandable properties. Must match a level in the standard BACnet priority array (a value from 1 to 16). See the Priority Reference table below. This parameter is optional and defaults to 8 if not specified. |
| propertyArrayIndex | Integer | [optional] The array index of the property to write to. This parameter is optional and should not be used when writing to the entire array or if the property is not an array. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.bacnet.writeRaw(deviceName, objectType, objectId, propertyId, value, [priority], [propertyArrayIndex])
```


---



---

# system.bacnet.writeRawMultiple

**版本：** 8.1
**型別：** Scripting
**分類：** Bacnet

## 詳述

This function is used inPython Scripting. This function is the bulk version ofsystem.bacnet.writeRawby writing properties to objects provided equal-length lists of object types, object instance numbers, property IDs, values, priorities, and property array indices. The system.bacnet.writeRawMultiple() function will accept Encodable values on the value parameter.

## 語法

```python
system.bacnet.writeRawMultiple(deviceName, objectTypes, objectIds, propertyIds, values, [priorities], [propertyArrayIndices])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | Name of the configured BACnet/IP device instance to write from. |
| objectTypes | ObjectType | A list of ObjectType(s) for the object instance being written to. |
| objectIds | Integer | A list of object instance numbers to write to. |
| propertyIds | PropertyIdentifier | A list of PropertyIdentifier(s) for the object instances being written to. |
| values | Object | A list of values to write. |
| priorities[optional] | Integer | An optional list of priority levels to use when writing to commandable properties. All elements must be in the range [1..16]. Defaults to 8 for all properties when this parameter is omitted. |
| propertyArrayIndices[optional] | Integer | An optional list of array indices corresponding to array properties being written. None should be specified as an element when writing to the entire array property or if the property is not an array. Defaults to a list of None when this parameter is omitted. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.bacnet.writeRawMultiple(deviceName, objectTypes, objectIds, propertyIds, values, [priorities], [propertyArrayIndices])
```

### Example 3

```python
objectTypes
```


---



---

# system.bacnet.writeWithPriority

**版本：** 8.1
**型別：** Scripting
**分類：** Bacnet

## 詳述

This function is used inPython Scripting. Write to the Present_Value attribute of an object with a custom priority level. To use this function, theBACnetdriver must be installed.

## 語法

```python
system.bacnet.writeWithPriority(deviceName, objectType, objectId, value, priority)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the configured BACnet/IP device instance to write from. |
| objectType | Integer | The numeric id of the objectType of the object instance being written to. See the objectType Reference table below. |
| objectId | Integer | The object instance number to write to. |
| value | Object | The value to write. Clearing a value can be accomplished by writing a None value. |
| priority | Integer | The priority level to write the value at. Must match a level in the standard BACnet priority array (a value from 1 to 16). See the Priority Reference table below. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.bacnet.writeWithPriority(deviceName, objectType, objectId, value, priority)
```


---

