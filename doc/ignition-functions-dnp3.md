# Ignition 8.1 - system.dnp3 函數文檔

﻿# Ignition 8.1 - 函數文檔（PATTERN 規範）

> 根據 FUNCTION_PATTERN 爬蟲生成
> 生成時間: 2026年04月19日 00:56:44
> 總計函式數: 434

## 📑 目錄

---

1. [system.dnp3.directOperateAnalog](#systemdnp3directoperateanalog) - The following function usessystem.dnp3and theLegacy DNP3 driver. Seesystem.dnpforDNP3functions using theDNP3 driver. This function is used inPython Scripting. Issues a Select-And-Operate command to set an analog value in an analog output point.
2. [system.dnp3.directOperateBinary](#systemdnp3directoperatebinary) - The following function usessystem.dnp3and theLegacy DNP3 driver. Seesystem.dnpforDNP3functions using theDNP3 driver. This function is used inPython Scripting. Issues a Direct-Operate command for digital control operations at binary output points (CROB).
3. [system.dnp3.freezeAnalogs](#systemdnp3freezeanalogs) - The following function usessystem.dnp3and theLegacy DNP3 driver. Seesystem.dnpforDNP3functions using theDNP3 driver. This function is used inPython Scripting. Issues a freeze command on the given analog outputs.
4. [system.dnp3.freezeAnalogsAtTime](#systemdnp3freezeanalogsattime) - The following function usessystem.dnp3and theLegacy DNP3 driver. Seesystem.dnpforDNP3functions using theDNP3 driver. This function is used inPython Scripting. Issues a freeze command on the given analog outputs at the given time for the specified duration.
5. [system.dnp3.freezeCounters](#systemdnp3freezecounters) - The following function usessystem.dnp3and theLegacy DNP3 driver. Seesystem.dnpforDNP3functions using theDNP3 driver. This function is used inPython Scripting. Issues a freeze command on the given counters.
6. [system.dnp3.freezeCountersAtTime](#systemdnp3freezecountersattime) - The following function usessystem.dnp3and theLegacy DNP3 driver. Seesystem.dnpforDNP3functions using theDNP3 driver. This function is used inPython Scripting. Issues a freeze command on the given counters at the given time for the specified duration.
7. [system.dnp3.selectOperateAnalog](#systemdnp3selectoperateanalog) - The following function usessystem.dnp3and theLegacy DNP3 driver. Seesystem.dnpforDNP3functions using theDNP3 driver. This function is used inPython Scripting. Issues a Select-And-Operate command to set an analog value in an analog output point.
8. [system.dnp3.selectOperateBinary](#systemdnp3selectoperatebinary) - The following function usessystem.dnp3and theLegacy DNP3 driver. Seesystem.dnpforDNP3functions using theDNP3 driver. This function is used inPython Scripting. Issues a Select-And-Operate command for digital control operations at binary output points (CROB).

---

# system.dnp3.directOperateAnalog

**版本：** 8.1
**型別：** Scripting
**分類：** Dnp3

## 詳述

The following function usessystem.dnp3and theLegacy DNP3 driver. Seesystem.dnpforDNP3functions using theDNP3 driver. This function is used inPython Scripting. Issues a Select-And-Operate command to set an analog value in an analog output point.

## 語法

```python
system.dnp3.directOperateAnalog(deviceName, index, value, [variation])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the DNP3 device driver. |
| index | Integer | The index of the object to be modified in the outstation. |
| value | Numeric | The analog value that is requested (of type int, short, float, or double). |
| variation | Integer | The DNP3 object variation to use in the request. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dnp3.directOperateAnalog(deviceName, index, value, [variation])
```


---



---

# system.dnp3.directOperateBinary

**版本：** 8.1
**型別：** Scripting
**分類：** Dnp3

## 詳述

The following function usessystem.dnp3and theLegacy DNP3 driver. Seesystem.dnpforDNP3functions using theDNP3 driver. This function is used inPython Scripting. Issues a Direct-Operate command for digital control operations at binary output points (CROB).

## 語法

```python
system.dnp3.directOperateBinary(deviceName, indexes, opType, tcCode, count, onTime, offTime)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the DNP3 device driver. |
| indexes | List | A list of indexes of the objects to be modified in the outstation. |
| opType | Integer | The type of the operation. 0=NUL, 1=PULSE_ON, 2=PULSE_OFF, 3=LATCH_ON, 4=LATCH_OFF |
| tcCode | Integer | The Trip-Close code, used in conjunction with the opType. 0=NUL, 1=CLOSE, 2=TRIP |
| count | Integer | The number of times the outstation shall execute the operation. |
| onTime | Long | The duration that the output drive remains active, in millis. [optional] |
| offTime | Long | The duration that the output drive remains non-active, in millis. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dnp3.directOperateBinary(deviceName, indexes, opType, tcCode, count, onTime, offTime)
```


---



---

# system.dnp3.freezeAnalogs

**版本：** 8.1
**型別：** Scripting
**分類：** Dnp3

## 詳述

The following function usessystem.dnp3and theLegacy DNP3 driver. Seesystem.dnpforDNP3functions using theDNP3 driver. This function is used inPython Scripting. Issues a freeze command on the given analog outputs.

## 語法

```python
system.dnp3.freezeAnalogs(deviceName, [indexes])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the DNP3 device driver. |
| indexes | List | A list of specific indexes on which to issue the freeze command. An empty list can be passed to freeze all analogs. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dnp3.freezeAnalogs(deviceName, [indexes])
```


---



---

# system.dnp3.freezeAnalogsAtTime

**版本：** 8.1
**型別：** Scripting
**分類：** Dnp3

## 詳述

The following function usessystem.dnp3and theLegacy DNP3 driver. Seesystem.dnpforDNP3functions using theDNP3 driver. This function is used inPython Scripting. Issues a freeze command on the given analog outputs at the given time for the specified duration.

## 語法

```python
system.dnp3.freezeAnalogsAtTime(deviceName, absoluteTime, intervalTime, indexes)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the DNP3 device driver. |
| absoluteTime | Integer | The absolute time at which to freeze, in millis. |
| intervalTime | Integer | The interval at which to periodically freeze, in millis. |
| indexes | List | A list of specific indexes on which to issue the freeze command. An empty list will freeze all points. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dnp3.freezeAnalogsAtTime(deviceName, absoluteTime, intervalTime, indexes)
```

### Example 3

```python
absoluteTime
```


---



---

# system.dnp3.freezeCounters

**版本：** 8.1
**型別：** Scripting
**分類：** Dnp3

## 詳述

The following function usessystem.dnp3and theLegacy DNP3 driver. Seesystem.dnpforDNP3functions using theDNP3 driver. This function is used inPython Scripting. Issues a freeze command on the given counters.

## 語法

```python
system.dnp3.freezeCounters(deviceName, [indexes])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the DNP3 device driver. |
| indexes | List | A list of specific indexes on which to issue the freeze command. An empty list can be passed to freeze all counters. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dnp3.freezeCounters(deviceName, [indexes])
```


---



---

# system.dnp3.freezeCountersAtTime

**版本：** 8.1
**型別：** Scripting
**分類：** Dnp3

## 詳述

The following function usessystem.dnp3and theLegacy DNP3 driver. Seesystem.dnpforDNP3functions using theDNP3 driver. This function is used inPython Scripting. Issues a freeze command on the given counters at the given time for the specified duration.

## 語法

```python
system.dnp3.freezeCountersAtTime(deviceName, absoluteTime, intervalTime, indexes)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the DNP3 device driver. |
| absoluteTime | Integer | The absolute time at which to freeze, in millis. |
| intervalTime | Integer | The interval at which to periodically freeze, in millis. |
| indexes | List | A list of specific indexes on which to issue the freeze command. An empty list will freeze all counters. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dnp3.freezeCountersAtTime(deviceName, absoluteTime, intervalTime, indexes)
```

### Example 3

```python
absoluteTime
```


---



---

# system.dnp3.selectOperateAnalog

**版本：** 8.1
**型別：** Scripting
**分類：** Dnp3

## 詳述

The following function usessystem.dnp3and theLegacy DNP3 driver. Seesystem.dnpforDNP3functions using theDNP3 driver. This function is used inPython Scripting. Issues a Select-And-Operate command to set an analog value in an analog output point.

## 語法

```python
system.dnp3.selectOperateAnalog(deviceName, index, value, [variation])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the DNP3 device driver. |
| index | Integer | The index of the object to be modified in the outstation. |
| value | Numeric | The analog value that is requested (of type int, short, float, or double). |
| variation | Integer | The DNP3 object variation to use in the request. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dnp3.selectOperateAnalog(deviceName, index, value, [variation])
```


---



---

# system.dnp3.selectOperateBinary

**版本：** 8.1
**型別：** Scripting
**分類：** Dnp3

## 詳述

The following function usessystem.dnp3and theLegacy DNP3 driver. Seesystem.dnpforDNP3functions using theDNP3 driver. This function is used inPython Scripting. Issues a Select-And-Operate command for digital control operations at binary output points (CROB).

## 語法

```python
system.dnp3.selectOperateBinary(deviceName, indexes, opType, tcCode, [count], [onTime], [offTime])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of theDNP3 driver. |
| indexes | List | A list of indexes of the objects to be modified in the outstation. |
| opType | Integer | The type of operation. 0=NUL, 1=PULSE_ON, 2=PULSE_OFF, 3=LATCH_ON, 4=LATCH_OFF |
| tcCode | Integer | The Trip-Close code, used in conjunction with the opType. 0=NUL, 1=CLOSE, 2=TRIP |
| count | Integer | The number of times the outstation shall execute the operation. [optional] |
| onTime | Integer | The duration that the output drive remains active, in millis. [optional] |
| offTime | Integer | The duration that the output drive remains non-active, in millis. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dnp3.selectOperateBinary(deviceName, indexes, opType, tcCode, [count], [onTime], [offTime])
```


---

