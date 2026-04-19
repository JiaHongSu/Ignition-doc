# Ignition 8.1 - system.device 函數文檔

﻿# Ignition 8.1 - 函數文檔（PATTERN 規範）

> 根據 FUNCTION_PATTERN 爬蟲生成
> 生成時間: 2026年04月19日 00:56:44
> 總計函式數: 434

## 📑 目錄

---

1. [system.device.addDevice](#systemdeviceadddevice) - This function is used inPython Scripting. Adds a new device connection in Ignition. Accepts a dictionary of parameters to configure the connection. Acceptable parameters differ by device type: i.e., a Modbus/TCP connection requires a hostname and port, but a simulator doesn't require any parameters. When using this function, the argumentsMUSTbe passed in askeyword arguments.
2. [system.device.addDevice - deviceProps Listing](#systemdeviceadddevice---deviceprops-listing) - Below is a table of properties callable by system.device.addDevice. TheDescriptionandEnabledproperties may not be configured with this function, although a device connection could be disabled with a call to system.device.setDeviceEnabled() after creating the connection.
3. [system.device.getDeviceHostname](#systemdevicegetdevicehostname) - This function is used in Python Scripting. Returns the hostname of the device. This scripting function has noClient Permissionrestrictions.
4. [system.device.listDevices](#systemdevicelistdevices) - This function is used inPython Scripting. Returns a dataset of information about each configured device. Each row represents a single device. This scripting function has noClient Permissionrestrictions.
5. [system.device.refreshBrowse](#systemdevicerefreshbrowse) - This function is used inPython Scripting. Forces Ignition to browse the controller. Only works for Allen-Bradley controllers using legacy Allen-Bradley drivers, such as CompactLogix and ControlLogix. This scripting function has noClient Permissionrestrictions.
6. [system.device.removeDevice](#systemdeviceremovedevice) - This function is used inPython Scripting. Removes a given device from Ignition. Permission Type: Device Management
7. [system.device.restart](#systemdevicerestart) - This function is used inPython Scripting. Restarts the named device connection.
8. [system.device.setDeviceEnabled](#systemdevicesetdeviceenabled) - This function is used inPython Scripting. Enables/disables a device in Ignition. Permission Type: Device Management
9. [system.device.setDeviceHostname](#systemdevicesetdevicehostname) - This function is used inPython Scripting. Changes the hostname of a device. Used for all ethernet based drivers. Permission Type: Device Management

---

# system.device.addDevice

**版本：** 8.1
**型別：** Scripting
**分類：** Device

## 詳述

This function is used inPython Scripting. Adds a new device connection in Ignition. Accepts a dictionary of parameters to configure the connection. Acceptable parameters differ by device type: i.e., a Modbus/TCP connection requires a hostname and port, but a simulator doesn't require any parameters. When using this function, the argumentsMUSTbe passed in askeyword arguments.

## 語法

```python
system.device.addDevice(deviceType, deviceName, deviceProps, [description])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceType | String | The device driver type. Possible values are listed in the Device Types table below. |
| deviceName | String | The name that will be given to the new device connection. |
| deviceProps | Dictionary[String, Any] | A dictionary of device connection properties and values. Each deviceType has different properties, but most require at least a hostname. Keys in the dictionary are case-insensitive, spaces are omitted, and the names of the properties that appear when manually creating a device connection. |
| description | String | New in8.1.10The description that will be given to the new device connection. [optional] |
| LogixDriver | Allen-Bradley Logix Driver |  |
| com.inductiveautomation.Micro800DeviceType | Allen-Bradley Micro800 |  |
| MicroLogix | Allen-Bradley MicroLogix |  |
| PLC5 | Allen-Bradley PLC5 |  |
| SLC | Allen-Bradley SLC |  |
| com.inductiveautomation.Dnp3DeviceType | DNP3 Driver |  |
| Dnp3Driver | Legacy DNP3 Driver |  |
| CompactLogix | Legacy Allen-Bradley CompactLogix |  |
| ControlLogix | Legacy Allen-Bradley ControlLogix |  |
| com.inductiveautomation.MitsubishiTcpDeviceType | Mitsubishi TCP |  |
| ModbusRtu | Modbus RTU |  |
| ModbusRtuOverTcp | Modbus RTU over TCP |  |
| ModbusTcp | Modbus TCP |  |
| com.inductiveautomation.FinsTcpDeviceType | Omron FINS TCP(requires manual configuration) |  |
| com.inductiveautomation.FinsUdpDeviceType | Omron FINS UDP(requires manual configuration) |  |
| com.inductiveautomation.omron.NjDriver | Omron NJ Driver |  |
| com.inductiveautomation.Iec61850DeviceType | IEC 61850 Driver |  |
| S7300 | Siemens S7-300 |  |
| S7400 | Siemens S7-400 |  |
| S71200 | Siemens S7-1200 |  |
| S71500 | Siemens S7-1500 |  |
| DairyDemoSimulator | Simulators Dairy Demo Simulator |  |
| Simulator | Simulators Generic Simulator |  |
| SLCSimulator | Simulators SLC Simulator |  |
| TCPDriver | TCP Driver |  |
| UDPDriver | UDP Driver |  |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.device.addDevice(deviceType, deviceName, deviceProps, [description])
```


---



---

# system.device.addDevice - deviceProps Listing

**版本：** 8.1
**型別：** Scripting
**分類：** Device

## 詳述

Below is a table of properties callable by system.device.addDevice. TheDescriptionandEnabledproperties may not be configured with this function, although a device connection could be disabled with a call to system.device.setDeviceEnabled() after creating the connection.

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
Description
```


---



---

# system.device.getDeviceHostname

**版本：** 8.1
**型別：** Scripting
**分類：** Device

## 詳述

This function is used in Python Scripting. Returns the hostname of the device. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.device.getDeviceHostname()
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the device in Ignition. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.device.getDeviceHostname()
```

### Example 3

```python
# The following example displays the device hostname
# for the device as entered in Ignition.

print system.device.getDeviceHostname(deviceName)
```


---



---

# system.device.listDevices

**版本：** 8.1
**型別：** Scripting
**分類：** Device

## 詳述

This function is used inPython Scripting. Returns a dataset of information about each configured device. Each row represents a single device. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.device.listDevices()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.device.listDevices()
```

### Example 2

```python
deviceDataset = system.device.listDevices()

# Assign the deviceDataset to a Power Table. This example assumes
# the Power Table is in the same container as the component that called this script
event.source.parent.getComponent('Power Table').data = deviceDataset
```

### Example 3

```python
deviceDataset = system.device.listDevices()

# Assign the deviceDataset to a Power Table. This example assumes
# the Power Table is in the same container as the component that called this script
event.source.parent.getComponent('Power Table').data = deviceDataset
```


---



---

# system.device.refreshBrowse

**版本：** 8.1
**型別：** Scripting
**分類：** Device

## 詳述

This function is used inPython Scripting. Forces Ignition to browse the controller. Only works for Allen-Bradley controllers using legacy Allen-Bradley drivers, such as CompactLogix and ControlLogix. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.device.refreshBrowse(deviceName)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the device in Ignition. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.device.refreshBrowse(deviceName)
```

### Example 3

```python
# Example 1:
system.device.refreshBrowse("CLX")
```


---



---

# system.device.removeDevice

**版本：** 8.1
**型別：** Scripting
**分類：** Device

## 詳述

This function is used inPython Scripting. Removes a given device from Ignition. Permission Type: Device Management

## 語法

```python
system.device.removeDevice(deviceName)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the device in Ignition. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.device.removeDevice(deviceName)
```

### Example 3

```python
# Example 1:
system.device.removeDevice("CLX")
```


---



---

# system.device.restart

**版本：** 8.1
**型別：** Scripting
**分類：** Device

## 詳述

This function is used inPython Scripting. Restarts the named device connection.

## 語法

```python
system.device.restart(deviceName)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the device connection to restart. The function will throw an error if the specified deviceName does not exist on the host gateway. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.device.restart(deviceName)
```

### Example 3

```python
system.device.restart("my_device")
```


---



---

# system.device.setDeviceEnabled

**版本：** 8.1
**型別：** Scripting
**分類：** Device

## 詳述

This function is used inPython Scripting. Enables/disables a device in Ignition. Permission Type: Device Management

## 語法

```python
system.device.setDeviceEnabled(deviceName, enabled)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the device in Ignition. |
| enabled | Boolean | Specifies whether the device connection will be set to enabled or disabled state. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.device.setDeviceEnabled(deviceName, enabled)
```


---



---

# system.device.setDeviceHostname

**版本：** 8.1
**型別：** Scripting
**分類：** Device

## 詳述

This function is used inPython Scripting. Changes the hostname of a device. Used for all ethernet based drivers. Permission Type: Device Management

## 語法

```python
system.device.setDeviceHostname(deviceName, hostname)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the device in Ignition. |
| hostname | String | The new IP address or hostname. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.device.setDeviceHostname(deviceName, hostname)
```


---

