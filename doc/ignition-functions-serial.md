# Ignition 8.1 - system.serial 函數文檔

﻿# Ignition 8.1 - 函數文檔（PATTERN 規範）

> 根據 FUNCTION_PATTERN 爬蟲生成
> 生成時間: 2026年04月19日 00:56:44
> 總計函式數: 434

## 📑 目錄

---

1. [system.serial.closeSerialPort](#systemserialcloseserialport) - This function is used inPython Scripting. Closes a previously opened serial port. Returns without doing anything if the named serial port is not currently open. Will throw an exception if the port is open and cannot be closed. This scripting function has noClient Permissionrestrictions.
2. [system.serial.configureSerialPort](#systemserialconfigureserialport) - This function is used inPython Scripting. Configure a serial port for use in a later call. This only needs to be done once unless the configuration has changed after the initial call. All access to constants must be prefixed by " system.serial. ". This scripting function has noClient Permissionrestrictions.
3. [system.serial.openSerialPort](#systemserialopenserialport) - This function is used inPython Scripting. Opens a previously configured serial port for use. Will throw an exception if the serial port cannot be opened. This scripting function has noClient Permissionrestrictions.
4. [system.serial.port](#systemserialport) - This function is used inPython Scripting. Returns acontext managerwrapping a serial port, allowing the rest of the system to interact with that port. This function effectively combines thesystem.serial.configureSerialPort,system.serial.openSerialPort, andsystem.serial.closeSerialPortfunctions into a single call. Intended to be used with thePython 'with' statement. The object aliased in the 'with' statement has special access to all of the othersystem.serialfunctions, allowing for reads and write
5. [system.serial.readBytes](#systemserialreadbytes) - This function is used inPython Scripting. ReadnumberOfBytesbytes from a serial port. This scripting function has noClient Permissionrestrictions.
6. [system.serial.readBytesAsString](#systemserialreadbytesasstring) - This function is used inPython Scripting. Read numberOfBytes bytes from a serial port and convert them to a String. If a specific encoding is needed to match the source of the data, usesystem.serial.readBytesand use the desired encoding to decode the byte array returned. This scripting function has noClient Permissionrestrictions.
7. [system.serial.readLine](#systemserialreadline) - This function is used inPython Scripting. Attempts to read a line from a serial port. A "line" is considered to be terminated by either a line feed ('\n'), a carriage return ('\r'), or a carriage return followed immediately by a line feed. The function will wait until the timeout period for a terminator. If the timeout is reached before the line is properly terminated, then the buffer will be dumped, possibly resulting in data loss.
8. [system.serial.readUntil](#systemserialreaduntil) - This function is used inPython Scripting. Reads a byte at a time from a serial port until a delimiter character is encountered. The read will block for up to timeout milliseconds before returning. If the delimiter is not found before the timeout period, then the buffer will dump, potentially resulting in data loss.
9. [system.serial.sendBreak](#systemserialsendbreak) - This function is used inPython Scripting. Sends a break signal for approximately millis milliseconds. This scripting function has noClient Permissionrestrictions.
10. [system.serial.write](#systemserialwrite) - This function is used inPython Scripting. Write a String to a serial port using the platforms default character encoding. This scripting function has noClient Permissionrestrictions.
11. [system.serial.writeBytes](#systemserialwritebytes) - This function is used inPython Scripting. Write a List[Byte] to a serial port. This scripting function has noClient Permissionrestrictions.

---

# system.serial.closeSerialPort

**版本：** 8.1
**型別：** Scripting
**分類：** Serial

## 詳述

This function is used inPython Scripting. Closes a previously opened serial port. Returns without doing anything if the named serial port is not currently open. Will throw an exception if the port is open and cannot be closed. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.serial.closeSerialPort(port)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| port | String | The name of the serial port, e.g., "COM1" or "dev/ttyS0". |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.serial.closeSerialPort(port)
```

### Example 3

```python
# This example will close a port called "COM1".
system.serial.closeSerialPort("COM1")
```


---



---

# system.serial.configureSerialPort

**版本：** 8.1
**型別：** Scripting
**分類：** Serial

## 詳述

This function is used inPython Scripting. Configure a serial port for use in a later call. This only needs to be done once unless the configuration has changed after the initial call. All access to constants must be prefixed by " system.serial. ". This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.serial.configureSerialPort(port, [bitRate], [dataBits], [hardwareFlowControl], [parity], [stopBits])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| port | String | The name of the serial port, e.g., "COM1" or "/dev/ttyS0". This parameter is required. |
| bitRate | Integer | Configure the bit rate. Valid values are defined by the following constants [optional]:system.serial.BIT_RATE_110, system.serial.BIT_RATE_150,system.serial.BIT_RATE_300, system.serial.BIT_RATE_600,system.serial.BIT_RATE_1200, system.serial.BIT_RATE_2400,system.serial.BIT_RATE_4800, system.serial.BIT_RATE_9600,system.serial.BIT_RATE_19200, system.serial.BIT_RATE_38400,system.serial.BIT_RATE_57600, system.serial.BIT_RATE_115200,system.serial.BIT_RATE_230400, system.serial.BIT_RATE_460800,system.serial.BIT_RATE_921600 |
| dataBits | Integer | Configure the data bits. Valid values are defined by the following constants [optional]:system.serial.DATA_BITS_5, system.serial.DATA_BITS_6,system.serial.DATA_BITS_7, system.serial.DATA_BITS_8 |
| hardwareFlowControl | Boolean | Configure hardware flow control. On or off. [optional] |
| parity | Integer | Configure parity. Valid values are defined by the following constants [optional]:system.serial.PARITY_EVEN, system.serial.PARITY_ODD,system.serial.PARITY_MARK, system.serial.PARITY_SPACE, system.serial.PARITY_NONE |
| stopBits | Integer | Configure stop bits.Valid values are defined by the following constants [optional]:system.serial.STOP_BITS_1, system.serial.STOP_BITS_2 |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.serial.configureSerialPort(port, [bitRate], [dataBits], [hardwareFlowControl], [parity], [stopBits])
```


---



---

# system.serial.openSerialPort

**版本：** 8.1
**型別：** Scripting
**分類：** Serial

## 詳述

This function is used inPython Scripting. Opens a previously configured serial port for use. Will throw an exception if the serial port cannot be opened. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.serial.openSerialPort(port)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| port | String | The name of the serial port, e.g., "COM1" or "dev/ttyS0". |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.serial.openSerialPort(port)
```

### Example 3

```python
# This example will open a port called "COM1"
system.serial.openSerialPort("COM1")
```


---



---

# system.serial.port

**版本：** 8.1
**型別：** Scripting
**分類：** Serial

## 詳述

This function is used inPython Scripting. Returns acontext managerwrapping a serial port, allowing the rest of the system to interact with that port. This function effectively combines thesystem.serial.configureSerialPort,system.serial.openSerialPort, andsystem.serial.closeSerialPortfunctions into a single call. Intended to be used with thePython 'with' statement. The object aliased in the 'with' statement has special access to all of the othersystem.serialfunctions, allowing for reads and write

## 語法

```python
system.serial.port(port, [bitRate], [dataBits], [handshake], [hardwareFlowControl], [parity], [stopBits])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| port | String | The name of the serial port, e.g., "COM1" or "/dev/ttyS0". This parameter is required. |
| bitRate | Integer | Configure the bit rate. Valid values are defined by the following constants [optional]:system.serial.BIT_RATE_110, system.serial.BIT_RATE_150,system.serial.BIT_RATE_300, system.serial.BIT_RATE_600,system.serial.BIT_RATE_1200, system.serial.BIT_RATE_2400,system.serial.BIT_RATE_4800, system.serial.BIT_RATE_9600,system.serial.BIT_RATE_19200, system.serial.BIT_RATE_38400,system.serial.BIT_RATE_57600, system.serial.BIT_RATE_115200,system.serial.BIT_RATE_230400, system.serial.BIT_RATE_460800,system.serial.BIT_RATE_921600 |
| dataBits | Integer | Configure the data bits. Valid values are defined by the following constants [optional]:system.serial.DATA_BITS_5, system.serial.DATA_BITS_6,system.serial.DATA_BITS_7, system.serial.DATA_BITS_8 |
| hardwareFlowControl | Boolean | Configure hardware flow control. On or off. [optional] |
| parity | Integer | Configure parity. Valid values are defined by the following constants [optional]:system.serial.PARITY_EVEN, system.serial.PARITY_ODD,system.serial.PARITY_MARK, system.serial.PARITY_SPACE, system.serial.PARITY_NONE |
| stopBits | Integer | Configure stop bits.Valid values are defined by the following constants [optional]:system.serial.STOP_BITS_1, system.serial.STOP_BITS_2 |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.serial.port(port, [bitRate], [dataBits], [handshake], [hardwareFlowControl], [parity], [stopBits])
```


---



---

# system.serial.readBytes

**版本：** 8.1
**型別：** Scripting
**分類：** Serial

## 詳述

This function is used inPython Scripting. ReadnumberOfBytesbytes from a serial port. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.serial.readBytes(port, numberOfBytes [, timeout])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| port | String | The previously configured serial port to use. |
| numberOfBytes | int | The number of bytes to read. |
| timeout | int | Maximum amount of time, in milliseconds, to block before returning. Default is 5000. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
numberOfBytes
```

### Example 2

```python
system.serial.readBytes(port, numberOfBytes [, timeout])
```


---



---

# system.serial.readBytesAsString

**版本：** 8.1
**型別：** Scripting
**分類：** Serial

## 詳述

This function is used inPython Scripting. Read numberOfBytes bytes from a serial port and convert them to a String. If a specific encoding is needed to match the source of the data, usesystem.serial.readBytesand use the desired encoding to decode the byte array returned. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.serial.readBytesAsString(port, numberOfBytes, [timeout], [encoding])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| port | String | The previously configured serial port to use. |
| numberOfBytes | Integer | The number of bytes to read. |
| timeout | Integer | Maximum amount of time, in milliseconds, to block before returning. Default is 5000. [optional] |
| encoding | String | Encoding to use when constructing the string. Defaults to the platform's default character set. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.serial.readBytesAsString(port, numberOfBytes, [timeout], [encoding])
```

### Example 3

```python
numberOfBytes
```


---



---

# system.serial.readLine

**版本：** 8.1
**型別：** Scripting
**分類：** Serial

## 詳述

This function is used inPython Scripting. Attempts to read a line from a serial port. A "line" is considered to be terminated by either a line feed ('\n'), a carriage return ('\r'), or a carriage return followed immediately by a line feed. The function will wait until the timeout period for a terminator. If the timeout is reached before the line is properly terminated, then the buffer will be dumped, possibly resulting in data loss.

## 語法

```python
system.serial.readLine(port [, timeout] [, encoding])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| port | String | The previously configured serial port to use. |
| timeout | Integer | Maximum amount of time, in milliseconds, to block before returning. Default is 5000. [optional] |
| encoding | String | The String encoding to use. Default is UTF8. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.serial.readLine(port [, timeout] [, encoding])
```


---



---

# system.serial.readUntil

**版本：** 8.1
**型別：** Scripting
**分類：** Serial

## 詳述

This function is used inPython Scripting. Reads a byte at a time from a serial port until a delimiter character is encountered. The read will block for up to timeout milliseconds before returning. If the delimiter is not found before the timeout period, then the buffer will dump, potentially resulting in data loss.

## 語法

```python
system.serial.readUntil(port, delimiter, includeDelimiter, [timeout])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| port | String | The previously configured serial port to use. |
| delimiter | Char | The delimiter to read until. |
| includeDelimiter | Boolean | If true, the delimiter will be included in the return value. |
| timeout | Integer | Timeout in milliseconds. Default is 5000. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.serial.readUntil(port, delimiter, includeDelimiter, [timeout])
```


---



---

# system.serial.sendBreak

**版本：** 8.1
**型別：** Scripting
**分類：** Serial

## 詳述

This function is used inPython Scripting. Sends a break signal for approximately millis milliseconds. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.serial.sendBreak(port, millis)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| port | String | The name of the serial port, e.g., "COM1" or "dev/ttyS0". |
| millis | Integer | Approximate length of break signal, in milliseconds. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.serial.sendBreak(port, millis)
```


---



---

# system.serial.write

**版本：** 8.1
**型別：** Scripting
**分類：** Serial

## 詳述

This function is used inPython Scripting. Write a String to a serial port using the platforms default character encoding. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.serial.write(port, toWrite, [timeout], [encoding])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| port | String | The previously configured serial port to use. |
| toWrite | String | The String to write. |
| timeout | Integer | A timeout, in milliseconds. Writes exceeding this period will . Defaults to 5000 [optional] |
| encoding | String | Encoding to decode the string with, for example: UTF-8. Default is the platform default character set. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.serial.write(port, toWrite, [timeout], [encoding])
```


---



---

# system.serial.writeBytes

**版本：** 8.1
**型別：** Scripting
**分類：** Serial

## 詳述

This function is used inPython Scripting. Write a List[Byte] to a serial port. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.serial.writeBytes(port, toWrite)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| port | String | The previously configured serial port to use. |
| toWrite | List[Byte] | The List[Byte] to write. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.serial.writeBytes(port, toWrite)
```


---

