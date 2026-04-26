# Ignition 8.1 - system.opc 函數文檔


## 📑 目錄

---

1. [system.opc.browse](#systemopcbrowse) - This function is used inPython Scripting. Allows browsing of the OPC servers in the runtime, returning a list of tags. This function performs a fully recursive browse that can't be terminated, which can be especially problematic in larger systems. It is highly advised to usesystem.opc.browseServerinstead since recursion with that function is driven by subsequent calls.
2. [system.opc.browseServer](#systemopcbrowseserver) - This function is used inPython Scripting. When called from a Vision Client, Perspective Session, or the Designer, returns a list of OPCBrowseElement objects for the given server. Otherwise returns a list of PyOPCTagEx objects.
3. [system.opc.browseSimple](#systemopcbrowsesimple) - This function is used inPython Scripting. Allows browsing of OPC servers in the runtime returning a list of tags. browseSimple() takes mandatory parameters, which can be null, while browse() uses keyword-style arguments. The spelling on theopcServeranddeviceparameters must be exact. This function performs a fully recursive browse that can't be terminated, which can be especially problematic in larger systems. It is highly advised to usesystem.opc.browseServerinstead since recursion with that fun
4. [system.opc.getServerState](#systemopcgetserverstate) - This function is used inPython Scripting. Retrieves the current state of the given OPC server connection. If the given server is not found, the return value will be None. Otherwise, the return value will be one of these strings: This scripting function has noClient Permissionrestrictions.
5. [system.opc.getServers](#systemopcgetservers) - This function is used inPython Scripting. Returns a list of server names. This scripting function has noClient Permissionrestrictions.
6. [system.opc.isServerEnabled](#systemopcisserverenabled) - This function is used inPython Scripting. Checks if an OPC server connection is enabled or disabled. This scripting function has noClient Permissionrestrictions.
7. [system.opc.readValue](#systemopcreadvalue) - This function is used inPython Scripting. Reads a single value directly from an OPC server connection. The address is specified as a string, for example, [MyDevice]N11/N11:0The object returned from this function has three attributes: value, quality, and timestamp. The value attribute represents the current value for the address specified. The quality attribute is an OPC UA status code. You can easily check a good quality vs a bad quality by calling the isGood() function on the quality object. Th
8. [system.opc.readValues](#systemopcreadvalues) - This function is used inPython Scripting. This function is equivalent to the system.opc.readValue function, except that it can operate in bulk. You can specify a list of multiple addresses to read from, and you will receive a list of the same length, where each entry is the qualified value object for the corresponding address. This scripting function has noClient Permissionrestrictions.
9. [system.opc.setServerEnabled](#systemopcsetserverenabled) - This function is used inPython Scripting. Enables or disables an OPC server connection. Permission Type: OPC Server Management
10. [system.opc.writeValue](#systemopcwritevalue) - This function is used inPython Scripting. Writes a value directly through an OPC server connection synchronously. Will return an OPC UA status code object. You can quickly check if the write succeeded by calling isGood() on the return value from this function.
11. [system.opc.writeValues](#systemopcwritevalues) - This function is used inPython Scripting. This function is a bulk version ofsystem.opc.writeValue. It takes a list of addresses and a list of objects, which must be the same length. It will write the corresponding object to the corresponding address in bulk. It will return a list of status codes representing the individual write success or failure for each corresponding address. Permission Type: OPC Server Management

---

# system.opc.browse

**版本：** 8.1
**型別：** Scripting
**分類：** Opc

## 詳述

This function is used inPython Scripting. Allows browsing of the OPC servers in the runtime, returning a list of tags. This function performs a fully recursive browse that can't be terminated, which can be especially problematic in larger systems. It is highly advised to usesystem.opc.browseServerinstead since recursion with that function is driven by subsequent calls.

## 語法

```python
system.opc.browse(opcServer, device, folderPath, opcItemPath)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| opcServer | String | The name of the OPC server to browse |
| device | String | The name of the device to browse |
| folderPath | String | Filters on a folder path. Use * as a wildcard for any number of characters and a ? for a single character. |
| opcItemPath | String | Filters on a OPC item path. Use * as a wildcard for any number of characters and a ? for a single character. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.opc.browse(opcServer, device, folderPath, opcItemPath)
```


---



---

# system.opc.browseServer

**版本：** 8.1
**型別：** Scripting
**分類：** Opc

## 詳述

This function is used inPython Scripting. When called from a Vision Client, Perspective Session, or the Designer, returns a list of OPCBrowseElement objects for the given server. Otherwise returns a list of PyOPCTagEx objects.

## 語法

```python
system.opc.browseServer(opcServer, nodeId)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| opcServer | String | The name of the OPC server connection. |
| nodeId | String | The node ID to browse. |
| opcServer | String | The name of the OPC server connection. |
| nodeId | String | The node ID to browse. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.opc.browseServer(opcServer, nodeId)
```


---



---

# system.opc.browseSimple

**版本：** 8.1
**型別：** Scripting
**分類：** Opc

## 詳述

This function is used inPython Scripting. Allows browsing of OPC servers in the runtime returning a list of tags. browseSimple() takes mandatory parameters, which can be null, while browse() uses keyword-style arguments. The spelling on theopcServeranddeviceparameters must be exact. This function performs a fully recursive browse that can't be terminated, which can be especially problematic in larger systems. It is highly advised to usesystem.opc.browseServerinstead since recursion with that fun

## 語法

```python
system.opc.browseSimple(opcServer, device, folderPath, opcItemPath)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| opcServer | String | The name of the OPC server to browse |
| device | String | The name of the device to browse |
| folderPath | String | Filters on a folder path. Use * as a wildcard for any number of characters and a ? for a single character. |
| opcItemPath | String | Filters on a OPC item path. Use * as a wildcard for any number of characters and a ? for a single character. |

## 回傳值

**型別：** Object

## 範例

### Example 3

```python
system.opc.browseSimple(opcServer, device, folderPath, opcItemPath)
```


---



---

# system.opc.getServerState

**版本：** 8.1
**型別：** Scripting
**分類：** Opc

## 詳述

This function is used inPython Scripting. Retrieves the current state of the given OPC server connection. If the given server is not found, the return value will be None. Otherwise, the return value will be one of these strings: This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.opc.getServerState(opcServer)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| opcServer | String | The name of an OPC server connection. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.opc.getServerState(opcServer)
```

### Example 3

```python
# The following will check the state of all configured servers, and show them in a message box.
# This code interacts in the client scope, so it should be placed on a component, such as a Button.

# Retrieve a list of all servers in the gateway
allServers = system.opc.getServers()

# Initialize a message. The example will append the state of each server to this message.
# The "\n" at the end of the string adds a new line
message = "Server State:\n"

# Iterate through each server.
for server in allServers:

    # for each server, append the server name, a colon, the state of the server, and a new line
    message += server + ": " + system.opc.getServerState(server) + "\n"

# Show the state of the servers in a message box.
system.gui.messageBox(message)
```


---



---

# system.opc.getServers

**版本：** 8.1
**型別：** Scripting
**分類：** Opc

## 詳述

This function is used inPython Scripting. Returns a list of server names. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.opc.getServers()
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| includeDisabled | Boolean | If set to True, enabled and disabled servers will be returned. If set to False, only enabled servers will be returned. Defaults to False. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.opc.getServers()
```

### Example 2

```python
includeDisabled
```

### Example 3

```python
# print a list of all server names found
servers = system.opc.getServers()
if not servers:
 print "No servers found"
else:
 for server in servers:
     print server
```


---



---

# system.opc.isServerEnabled

**版本：** 8.1
**型別：** Scripting
**分類：** Opc

## 詳述

This function is used inPython Scripting. Checks if an OPC server connection is enabled or disabled. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.opc.isServerEnabled(serverName)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| serverName | String | The name of an OPC server connection. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.opc.isServerEnabled(serverName)
```

### Example 3

```python
# The following will iterate through all configured OPC servers, and check if they are enabled or disabled
# This code interacts in the client scope, so it should be placed on a component, such as a Button.

# Retrieve a list of all servers in the gateway
allServers = system.opc.getServers()

# Initialize a message. The example will append the state of each server to this message.
# The "\n" at the end of the string adds a new line
message = "Server Status:\n"

# Iterate through each server.
for server in allServers:

    # for each server, append the server name, a colon, the state of the server, and a new line.
    # isServerEnabled returns a boolean, but may use the string format specifier (%s)
    message += "%s : %s \n" % (server, system.opc.isServerEnabled(server))

# Show the state of the servers in a message box.
system.gui.messageBox(message)
```


---



---

# system.opc.readValue

**版本：** 8.1
**型別：** Scripting
**分類：** Opc

## 詳述

This function is used inPython Scripting. Reads a single value directly from an OPC server connection. The address is specified as a string, for example, [MyDevice]N11/N11:0The object returned from this function has three attributes: value, quality, and timestamp. The value attribute represents the current value for the address specified. The quality attribute is an OPC UA status code. You can easily check a good quality vs a bad quality by calling the isGood() function on the quality object. Th

## 語法

```python
system.opc.readValue(opcServer, itemPath)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| opcServer | String | The name of the OPC server connection in which the item resides. |
| itemPath | String | The item path, or address, to read from. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.opc.readValue(opcServer, itemPath)
```


---



---

# system.opc.readValues

**版本：** 8.1
**型別：** Scripting
**分類：** Opc

## 詳述

This function is used inPython Scripting. This function is equivalent to the system.opc.readValue function, except that it can operate in bulk. You can specify a list of multiple addresses to read from, and you will receive a list of the same length, where each entry is the qualified value object for the corresponding address. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.opc.readValues(opcServer, itemPaths)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| opcServer | String | The name of the OPC server connection in which the items reside. |
| itemPaths | List[String] | A list of strings, each representing an item path, or address to read from. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.opc.readValues(opcServer, itemPaths)
```


---



---

# system.opc.setServerEnabled

**版本：** 8.1
**型別：** Scripting
**分類：** Opc

## 詳述

This function is used inPython Scripting. Enables or disables an OPC server connection. Permission Type: OPC Server Management

## 語法

```python
system.opc.setServerEnabled(serverName, enabled)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| serverName | String | The name of an OPC server connection. |
| enabled | Boolean | The new state the connection should be set to: true to enable the connection, false to disable. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.opc.setServerEnabled(serverName, enabled)
```


---



---

# system.opc.writeValue

**版本：** 8.1
**型別：** Scripting
**分類：** Opc

## 詳述

This function is used inPython Scripting. Writes a value directly through an OPC server connection synchronously. Will return an OPC UA status code object. You can quickly check if the write succeeded by calling isGood() on the return value from this function.

## 語法

```python
system.opc.writeValue(opcServer, itemPath, value)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| opcServer | String | The name of the OPC server connection in which the item resides. |
| itemPath | String | The item path, or address, to write to. |
| value | Object | The value to write to the OPC item. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.opc.writeValue(opcServer, itemPath, value)
```


---



---

# system.opc.writeValues

**版本：** 8.1
**型別：** Scripting
**分類：** Opc

## 詳述

This function is used inPython Scripting. This function is a bulk version ofsystem.opc.writeValue. It takes a list of addresses and a list of objects, which must be the same length. It will write the corresponding object to the corresponding address in bulk. It will return a list of status codes representing the individual write success or failure for each corresponding address. Permission Type: OPC Server Management

## 語法

```python
system.opc.writeValues(opcServer, itemPaths, values)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| opcServer | String | The name of the OPC server connection in which the items reside. |
| itemPaths | List[String] | A list of item paths, or addresses, to write to. |
| values | List[Any] | A list of values to write to each address specified. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.opc.writeValues(opcServer, itemPaths, values)
```


---

