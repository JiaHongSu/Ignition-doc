# Ignition 8.1 - system.dnp 函數文檔


## 📑 目錄

---

1. [system.dnp.demandPoll](#systemdnpdemandpoll) - The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Issues a poll request for one or more classes.
2. [system.dnp.directOperateAnalog](#systemdnpdirectoperateanalog) - The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Performs a Direct Operate command on an analog point.
3. [system.dnp.directOperateBinary](#systemdnpdirectoperatebinary) - The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Performs a Direct Operate command on a binary point.
4. [system.dnp.freezeAnalogs](#systemdnpfreezeanalogs) - The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Issues an Immediate Freeze command targeting one or more analog points.
5. [system.dnp.freezeAtTimeAnalogs](#systemdnpfreezeattimeanalogs) - The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Issues a Freeze at Time command targeting one or more analog points.
6. [system.dnp.freezeAtTimeCounters](#systemdnpfreezeattimecounters) - The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Issues a Freeze at Time command targeting one or more counters.
7. [system.dnp.freezeClearAnalogs](#systemdnpfreezeclearanalogs) - The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Issues a Freeze and Clear command targeting one or more analog points.
8. [system.dnp.freezeClearCounters](#systemdnpfreezeclearcounters) - The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Issues a Freeze and Clear command targeting one or more counters.
9. [system.dnp.freezeCounters](#systemdnpfreezecounters) - The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Issues an Immediate Freeze command targeting one or more counters.
10. [system.dnp.selectOperateAnalog](#systemdnpselectoperateanalog) - The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Performs a Select then Operate command on an analog point.
11. [system.dnp.selectOperateBinary](#systemdnpselectoperatebinary) - The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Performs a Select then Operate command on a binary point.
12. [system.dnp.synchronizeTime](#systemdnpsynchronizetime) - The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Issues a Synchronize Time command using the current Ignition Gateway time.

---

# system.dnp.demandPoll

**版本：** 8.1
**型別：** Scripting
**分類：** Dnp

## 詳述

The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Issues a poll request for one or more classes.

## 語法

```python
system.dnp.demandPoll(deviceName, classList)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the DNP3 device instance. |
| classList | List | A List of classes (1, 2, 3) to issue polls. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dnp.demandPoll(deviceName, classList)
```


---



---

# system.dnp.directOperateAnalog

**版本：** 8.1
**型別：** Scripting
**分類：** Dnp

## 詳述

The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Performs a Direct Operate command on an analog point.

## 語法

```python
system.dnp.directOperateAnalog(deviceName, variation, index, value)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the DNP3 device instance. |
| variation | Integer | The Group 41 variation to use during the operation. |
| index | Integer | The index of the analog point. |
| value | Numeric | The requested value. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dnp.directOperateAnalog(deviceName, variation, index, value)
```


---



---

# system.dnp.directOperateBinary

**版本：** 8.1
**型別：** Scripting
**分類：** Dnp

## 詳述

The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Performs a Direct Operate command on a binary point.

## 語法

```python
system.dnp.directOperateBinary(deviceName, index, tcc, opType, count, onTime, offTime)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the DNP3 device instance. |
| index | Integer | The index of the binary point. |
| tcc | Integer | Trip Close Code: 0=NUL, 1=CLOSE, 2=TRIP. |
| opType | Integer | Operation Type: 0=NUL, 1=PULSE_ON, 2=PULSE_OFF, 3=LATCH_ON, 4=LATCH_OFF. |
| count | Integer | The number of times the outstation shall execute the operation. |
| onTime | Integer | Duration (in milliseconds) the output drive remains active. |
| offTime | Integer | Duration (in milliseconds) the output drive remains non-active. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dnp.directOperateBinary(deviceName, index, tcc, opType, count, onTime, offTime)
```


---



---

# system.dnp.freezeAnalogs

**版本：** 8.1
**型別：** Scripting
**分類：** Dnp

## 詳述

The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Issues an Immediate Freeze command targeting one or more analog points.

## 語法

```python
system.dnp.freezeAnalogs(deviceName, indexes)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the DNP3 device instance. |
| indexes | List | The indices of the analog points to freeze. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dnp.freezeAnalogs(deviceName, indexes)
```


---



---

# system.dnp.freezeAtTimeAnalogs

**版本：** 8.1
**型別：** Scripting
**分類：** Dnp

## 詳述

The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Issues a Freeze at Time command targeting one or more analog points.

## 語法

```python
system.dnp.freezeAtTimeAnalogs(deviceName, absoluteTime, intervalTime, indexes)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the DNP3 device instance. |
| absoluteTime | Long | Absolute time (in milliseconds since epoch UTC) when the initial action should occur. |
| intervalTime | Long | Interval time (in milliseconds) between periodic actions. |
| indexes | List | The indices of the analog points to freeze. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dnp.freezeAtTimeAnalogs(deviceName, absoluteTime, intervalTime, indexes)
```

### Example 3

```python
absoluteTime
```


---



---

# system.dnp.freezeAtTimeCounters

**版本：** 8.1
**型別：** Scripting
**分類：** Dnp

## 詳述

The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Issues a Freeze at Time command targeting one or more counters.

## 語法

```python
system.dnp.freezeAtTimeCounters(deviceName, absoluteTime, intervalTime, indexes)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the DNP3 device instance. |
| absoluteTime | Long | Absolute time (in milliseconds since epoch UTC) when the initial action should occur. |
| intervalTime | Long | Interval time (in milliseconds) between periodic actions. |
| indexes | List | The indices of the counters to freeze. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dnp.freezeAtTimeCounters(deviceName, absoluteTime, intervalTime, indexes)
```

### Example 3

```python
absoluteTime
```


---



---

# system.dnp.freezeClearAnalogs

**版本：** 8.1
**型別：** Scripting
**分類：** Dnp

## 詳述

The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Issues a Freeze and Clear command targeting one or more analog points.

## 語法

```python
system.dnp.freezeClearAnalogs(deviceName, indexes)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the DNP3 device instance. |
| indexes | List | The indices of the analog points to freeze. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dnp.freezeClearAnalogs(deviceName, indexes)
```


---



---

# system.dnp.freezeClearCounters

**版本：** 8.1
**型別：** Scripting
**分類：** Dnp

## 詳述

The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Issues a Freeze and Clear command targeting one or more counters.

## 語法

```python
system.dnp.freezeClearCounters(deviceName, indexes)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the DNP3 device instance. |
| indexes | List | The indices of the counters to freeze. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dnp.freezeClearCounters(deviceName, indexes)
```


---



---

# system.dnp.freezeCounters

**版本：** 8.1
**型別：** Scripting
**分類：** Dnp

## 詳述

The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Issues an Immediate Freeze command targeting one or more counters.

## 語法

```python
system.dnp.freezeCounters(deviceName, indexes)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the DNP3 device instance. |
| indexes | List | The indices of the counters to freeze. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dnp.freezeCounters(deviceName, indexes)
```


---



---

# system.dnp.selectOperateAnalog

**版本：** 8.1
**型別：** Scripting
**分類：** Dnp

## 詳述

The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Performs a Select then Operate command on an analog point.

## 語法

```python
system.dnp.selectOperateAnalog(deviceName, variation, index, value)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the DNP3 device instance. |
| variation | Integer | The Group 41 variation to use during the operation. |
| index | Integer | The index of the analog point. |
| value | Numeric | The requested value. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dnp.selectOperateAnalog(deviceName, variation, index, value)
```


---



---

# system.dnp.selectOperateBinary

**版本：** 8.1
**型別：** Scripting
**分類：** Dnp

## 詳述

The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Performs a Select then Operate command on a binary point.

## 語法

```python
system.dnp.selectOperateBinary(deviceName, index, tcc, opType, count, onTime, offTime)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the DNP3 device instance. |
| index | Integer | The index of the binary point. |
| tcc | Integer | Trip Close Code: 0=NUL, 1=CLOSE, 2=TRIP. |
| opType | Integer | Operation Type: 0=NUL, 1=PULSE_ON, 2=PULSE_OFF, 3=LATCH_ON, 4=LATCH_OFF. |
| count | Integer | The number of times the outstation shall execute the operation. |
| onTime | Integer | Duration (in milliseconds) the output drive remains active. |
| offTime | Integer | Duration (in milliseconds) the output drive remains non-active. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dnp.selectOperateBinary(deviceName, index, tcc, opType, count, onTime, offTime)
```


---



---

# system.dnp.synchronizeTime

**版本：** 8.1
**型別：** Scripting
**分類：** Dnp

## 詳述

The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Issues a Synchronize Time command using the current Ignition Gateway time.

## 語法

```python
system.dnp.synchronizeTime(deviceName)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the DNP3 device instance. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dnp.synchronizeTime(deviceName)
```

### Example 3

```python
system.dnp.synchronizeTime("DNP3")
```


---

