# Ignition 8.1 - system.util 函數文檔

﻿# Ignition 8.1 - 函數文檔（PATTERN 規範）

> 根據 FUNCTION_PATTERN 爬蟲生成
> 生成時間: 2026年04月19日 00:56:44
> 總計函式數: 434

## 📑 目錄

---

1. [system.util.audit](#systemutilaudit) - This function is used inPython Scripting. Inserts a record into an audit profile. This scripting function has noClient Permissionrestrictions.
2. [system.util.beep](#systemutilbeep) - This function is used inPython Scripting. Tells the computer where the script is running to make a "beep" sound. The computer must have a way of producing sound. While this function is technically scoped for Gateway and Perspective Sessions, it's intended for use in Vision Clients.
3. [system.util.execute](#systemutilexecute) - This function is used inPython Scripting. Executes the given commands via the operating system, in a separate process. The commands argument is an array of strings. The first string is the program to execute, with subsequent strings being the arguments to that command. This scripting function has noClient Permissionrestrictions.
4. [system.util.exit](#systemutilexit) - This function is used inPython Scripting. Exits the running client, as long as the shutdown intercept script doesn't cancel the shutdown event. Set force to true to not give the shutdown intercept script a chance to cancel the exit. Note that this will quit the Client completely. you can use system.security.logout() to return to the login screen. This scripting function has noClient Permissionrestrictions.
5. [system.util.getAvailableLocales](#systemutilgetavailablelocales) - This function is used inPython Scripting. Returns a collection of strings representing the Locales added to the Translation Manager, such as 'en' for English. This scripting function has noClient Permissionrestrictions.
6. [system.util.getAvailableTerms](#systemutilgetavailableterms) - This function is used inPython Scripting. Returns a collection of available terms defined in the translation system. This scripting function has noClient Permissionrestrictions.
7. [system.util.getClientId](#systemutilgetclientid) - This function is used inPython Scripting. Returns a hex-string that represents a number unique to the running client's session. You are guaranteed that this number is unique between all running clients. This scripting function has noClient Permissionrestrictions.
8. [system.util.getConnectTimeout](#systemutilgetconnecttimeout) - This function is used inPython Scripting. Returns the connect timeout in milliseconds for all client-to-gateway communication. This is the maximum amount of time that communication operations to the Gateway will be given to connect. The default is 10,000ms (10 seconds). This scripting function has noClient Permissionrestrictions.
9. [system.util.getConnectionMode](#systemutilgetconnectionmode) - This function is used inPython Scripting. Retrieves this client session's current connection mode. 3 is read/write, 2 is read-only, and 1 is disconnected. This scripting function has noClient Permissionrestrictions.
10. [system.util.getEdition](#systemutilgetedition) - This function is used inPython Scripting. Returns the "edition" of the Vision client - "standard", "limited", or "panel". This scripting function has noClient Permissionrestrictions.
11. [system.util.getGatewayAddress](#systemutilgetgatewayaddress) - This function is used inPython Scripting. Returns the address of the Gateway with which the Client is currently communicating. This scripting function has noClient Permissionrestrictions.
12. [system.util.getGatewayStatus](#systemutilgetgatewaystatus) - This function is used inPython Scripting. Returns a string that indicates the status of a Gateway. A status ofRUNNINGmeans the Gateway is fully functional. If an exception occurs, the function returnsERRORwith the associated error message appended. This function can be used to test the availability and operational state of a remote Gateway. This scripting function has noClient Permissionrestrictions.
13. [system.util.getGlobals](#systemutilgetglobals) - This function is used inPython Scripting. This method returns a dictionary that provides access to the legacy global namespace. As of version 7.7.0, most new scripts use the modern style of scoping, which makes the 'global' keyword act very differently. Most importantly, the modern scoping rules mean that variables declared as 'global' are only global within that one module. The system.util.getGlobals() method can be used to interact with older scripts that used the old meaning of the 'global' k
14. [system.util.getInactivitySeconds](#systemutilgetinactivityseconds) - This function is used inPython Scripting. Returns the number of seconds since any keyboard or mouse activity. This function will always return zero in the Designer.
15. [system.util.getLocale](#systemutilgetlocale) - This function is used inPython Scripting. Returns the current string representing the user's Locale, such as 'en' for English. This scripting function has noClient Permissionrestrictions.
16. [system.util.getLogger](#systemutilgetlogger) - This function is used inPython Scripting. Returns a Logger object that can be used to log messages to the console. Each Logger has a name, which is typically structured hierarchically using periods, indicating where in the project the Logger is used. You can use any naming scheme you like, however a well-planned naming scheme makes finding  log entries and setting log levels much easier. Loggers can be shared between scripts simply by giving them the same name. Six levels of logging are availabl
17. [system.util.getModules](#systemutilgetmodules) - This function is used inPython Scripting. Returns a dataset of information about each installed module. Each row represents a single module. This scripting function has noClient Permissionrestrictions.
18. [system.util.getProjectName](#systemutilgetprojectname) - This function is used inPython Scripting. Returns the name of the project that is currently being run. When run from the Gateway scope from a resource that originates from a singular project (reports, SFCs, etc.), will return that resources project. When called from a scope that does not have an associated project (a Tag Event Script), the function will return the name of the Gateway scripting project. If a Gateway scripting project has not been configured, then returns an empty string.
19. [system.util.getProperty](#systemutilgetproperty) - This function is used inPython Scripting. Retrieves the value of a named system property. Some of the available properties are: This scripting function has noClient Permissionrestrictions.
20. [system.util.getReadTimeout](#systemutilgetreadtimeout) - This function is used inPython Scripting. Returns the read timeout in milliseconds for all client-to-gateway communication. This is the maximum amount of time allowed for a communication operation to complete. The default is 60,000ms (1 minute). This scripting function has noClient Permissionrestrictions.
21. [system.util.getSessionInfo](#systemutilgetsessioninfo) - This function is used inPython Scripting. Returns a PyDataSet holding information about all of the open Designer sessions and Vision Clients. Optional regular-expression based filters can be provided to filter the username or the username and the project returned. This function will not return all sessions across a cluster - only the cluster node that is being communicated with by the client who makes the call.
22. [system.util.getSystemFlags](#systemutilgetsystemflags) - This function is used inPython Scripting. Returns an integer that represents a bit field containing information about the currently running system. Each bit corresponds to a specific flag as defined in the bitmask below. The integer return will be a total of all of the bits that are currently active. See the example for tips on how to extract the information in this bit field. Note that the tag[System]Client/System/SystemFlagscontains the same value. This scripting function has noClient Permissi
23. [system.util.getVersion](#systemutilgetversion) - This function is used inPython Scripting. Returns the Ignition version number that is currently being run. If the version is from a nightly build or developer version that is not yet released, the version number will come back as "Dev Version", for example:
24. [system.util.invokeAsynchronous](#systemutilinvokeasynchronous) - This function is used inPython Scripting. Invokes (calls) the given Python function on a different thread. This means that calls to invokeAsynchronous will return immediately, and then the given function will start executing asynchronously on a different thread. This is useful for long-running data intensive functions, where running them synchronously (in the GUI thread) would make the GUI non-responsive for an unacceptable amount of time. This function should not be used to asynchronously inter
25. [system.util.invokeLater](#systemutilinvokelater) - This function is used inPython Scripting. Invokes (calls) the given Python function object after all of the currently processing and pending events are done being processed, or after a specified delay. The function will be executed on the GUI, or event dispatch, thread. This is useful for events like propertyChange events, where the script is called before any bindings are evaluated. If you specify an optional time argument (number of milliseconds), the function will be invoked after all current
26. [system.util.jsonDecode](#systemutiljsondecode) - This function is used inPython Scripting. Takes a JSON string and converts it into a Python object such as a list or a dictionary. If the input is not valid JSON, a string is returned. This scripting function has noClient Permissionrestrictions.
27. [system.util.jsonEncode](#systemutiljsonencode) - This function is used inPython Scripting. Takes a Python object such as a list or dictionary and converts into a JSON string. This scripting function has noClient Permissionrestrictions.
28. [system.util.modifyTranslation](#systemutilmodifytranslation) - This function is used inPython Scripting. This function allows you to add or modify a global translation. Permission Type: Translation Management
29. [system.util.playSoundClip](#systemutilplaysoundclip) - This function is used inPython Scripting. Plays a sound clip from a  wav  file to the system's default audio device. The  wav  file can be specified as a filepath, a URL, or directly as a raw List[Byte]. While this function is technically scoped for Gateway and Perspective Sessions, it's intended for use in Vision Clients.
30. [system.util.queryAuditLog](#systemutilqueryauditlog) - This function is used inPython Scripting. Queries an audit profile for audit history. Returns the results as a dataset. A description of the returned dataset can be found on theIgnition Database Table Referencepage.
31. [system.util.retarget](#systemutilretarget) - This function is used inPython Scripting. This function allows you to programmatically 'retarget' a Vision Client to a different project and/or different Gateway. You can have it switch to another project on the same Gateway, or another Gateway entirely, even across a WAN. This feature makes the vision of a seamless, enterprise-wide SCADA application a reality. The retarget feature will attempt to transfer the current user credentials over to the new project / Gateway. If the credentials fail on
32. [system.util.sendMessage](#systemutilsendmessage) - This function is used inPython Scripting. This function sends a message to clients running under the Gateway or to a project within the Gateway itself. To handle received messages, you must set up event script message handlers within a project. These message handlers run Jython code when a message is received. You can add message handlers under theMessagesection of the client/Gateway event script configuration dialogs. Messages cannot be received within a Designer. However, messages can be sent 
33. [system.util.sendRequest](#systemutilsendrequest) - This function is used inPython Scripting. This function sends a message to the Gateway, working in a similar manner to thesendMessagefunction, except sendRequest expects a response to the message. To handle received messages, you must set up Gateway Event Script message handlers within a project. These message handlers run Jython code when a message is received. You can then place a return at the end of the code to return something to where the sendRequest was originally called from. You can add
34. [system.util.sendRequestAsync](#systemutilsendrequestasync) - This function is used inPython Scripting. This function sends a message to the Gateway and expects a response. Works in a similar manner to thesendRequestfunction, except sendRequestAsync will send the request and then immediately return a handle for it. The Request handle has the following methods: This scripting function has noClient Permissionrestrictions.
35. [system.util.setConnectTimeout](#systemutilsetconnecttimeout) - This function is used inPython Scripting. Sets the connect timeout for Client-to-Gateway communication. Specified in milliseconds. This scripting function has noClient Permissionrestrictions.
36. [system.util.setConnectionMode](#systemutilsetconnectionmode) - This function is used inPython Scripting. Sets the connection mode for the client session. Normally a client runs in mode 3, which is read-write. You may wish to change this to mode 2, which is read-only, which will only allow reading and subscribing to tags, and running SELECT queries. Tag writes and INSERT/UPDATE/DELETE queries will not function. You can also set the connection mode to mode 1, which is disconnected, all tag and query features will not work. This scripting function has noClient
37. [system.util.setLocale](#systemutilsetlocale) - This function is used inPython Scripting. Sets the user's current Locale. Any valid Java locale code (case-insensitive) can be used as a parameter, including ones that have not yet been added to the Translation Manager. An invalid locale code will cause an Illegal Argument Exception. This scripting function has noClient Permissionrestrictions.
38. [system.util.setLoggingLevel](#systemutilsetlogginglevel) - This function is used inPython Scripting. Sets the logging level on the given logger. This can be a logger you create, or a logger already defined in the system. This scripting function has noClient Permissionrestrictions.
39. [system.util.setReadTimeout](#systemutilsetreadtimeout) - This function is used inPython Scripting. Sets the read timeout for Client-to-Gateway communication. Specified in milliseconds. This scripting function has noClient Permissionrestrictions.
40. [system.util.threadDump](#systemutilthreaddump) - This function is used inPython Scripting. Creates a thread dump of the current running JVM. This scripting function has noClient Permissionrestrictions.
41. [system.util.translate](#systemutiltranslate) - This function is used inPython Scripting. This function allows you to retrieve the global translation of a term from the translation database using the current locale. This scripting function has noClient Permissionrestrictions.

---

# system.util.audit

**版本：** 8.1
**型別：** Scripting
**分類：** Util

## 詳述

This function is used inPython Scripting. Inserts a record into an audit profile. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.util.audit([action], [actionTarget], [actionValue], [auditProfile], [actor], [actorHost], [originatingSystem], [eventTimestamp], [originatingContext], [statusCode])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| action | String | What happened. Default is null. [optional] |
| actionTarget | String | What the action happened to. Default is null. [optional] |
| actionValue | String | The value of the action. Default is no value. [optional] |
| auditProfile | String | Where the audit record should be stored. Defaults to the project’s audit profile (if specified), or the Gateway audit profile if calling in the Gateway or Perspective Session scope. [optional] |
| actor | String | Who made the change. Will be populated automatically if omitted, assuming there is a known user. [optional] |
| actorHost | String | The hostname of whoever made the change. Will be populated automatically if omitted. [optional] |
| originatingSystem | List[String] | An even-length list providing additional context to the audit event. Will be appended to the automatically generated list.Typically, the automatically generated context looks like this:sys:${gatewayName}:\project:${projectName}If you provided[“component”, “Joe’sButton”, “field”, “value”], you would get a record with:originatingSystem:sys:${gatewayName}:\project:${projectName}:\component:Joe’sButton:\field:value.If a string is provided, this automatic context will not be used and your provided string will be written directly into the originatingSystem column in the audit profile. [optional] |
| eventTimestamp | Date | When the event happened. Will be set to the current time if omitted. [optional] |
| originatingContext | Integer | What scope the event originated from: 1 means Gateway, 2 means Designer, 4 means Client. Will be set automatically if omitted. [optional] |
| statusCode | Integer | A quality code to attach to the object. Defaults to 0, indicating no special meaning. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.util.audit([action], [actionTarget], [actionValue], [auditProfile], [actor], [actorHost], [originatingSystem], [eventTimestamp], [originatingContext], [statusCode])
```

### Example 3

```python
actionTarget
```


---



---

# system.util.beep

**版本：** 8.1
**型別：** Scripting
**分類：** Util

## 詳述

This function is used inPython Scripting. Tells the computer where the script is running to make a "beep" sound. The computer must have a way of producing sound. While this function is technically scoped for Gateway and Perspective Sessions, it's intended for use in Vision Clients.

## 語法

```python
system.util.beep()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.util.beep()
```

### Example 2

```python
# This will simply cause the system where the script is being executed to emit a beep sound.
# That system must have a way to produce sound, such as speakers or headphones.

system.util.beep()
```

### Example 3

```python
# This will simply cause the system where the script is being executed to emit a beep sound.
# That system must have a way to produce sound, such as speakers or headphones.

system.util.beep()
```


---



---

# system.util.execute

**版本：** 8.1
**型別：** Scripting
**分類：** Util

## 詳述

This function is used inPython Scripting. Executes the given commands via the operating system, in a separate process. The commands argument is an array of strings. The first string is the program to execute, with subsequent strings being the arguments to that command. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.util.execute(commands)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| commands | List[String] | A list containing the command (1st entry) and associated arguments (remaining entries) to execute. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.util.execute(commands)
```

### Example 3

```python
# This function flushes the resolver cache.
system.util.execute(["ipconfig", "/flushdns"])
```


---



---

# system.util.exit

**版本：** 8.1
**型別：** Scripting
**分類：** Util

## 詳述

This function is used inPython Scripting. Exits the running client, as long as the shutdown intercept script doesn't cancel the shutdown event. Set force to true to not give the shutdown intercept script a chance to cancel the exit. Note that this will quit the Client completely. you can use system.security.logout() to return to the login screen. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.util.exit([force])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| force | Boolean | If true (1), the shutdown-intercept script will be skipped. Default is false (0). [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.util.exit([force])
```

### Example 3

```python
# This code would exit the client after confirming with the user.
if system.gui.confirm("Are you sure you want to exit?"):
   system.util.exit()
```


---



---

# system.util.getAvailableLocales

**版本：** 8.1
**型別：** Scripting
**分類：** Util

## 詳述

This function is used inPython Scripting. Returns a collection of strings representing the Locales added to the Translation Manager, such as 'en' for English. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.util.getAvailableLocales()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.util.getAvailableLocales()
```

### Example 2

```python
#This code will take all of the available locales, and put them into a text field on the same window.

collection = system.util.getAvailableLocales()
locales = ''
for locale in collection:
    if locales == '':
        locales += locale
    else:
        locales += ", " + locale
event.source.parent.getComponent('Text Field').text = locales
```

### Example 3

```python
#This code will take all of the available locales, and put them into a text field on the same window.

collection = system.util.getAvailableLocales()
locales = ''
for locale in collection:
    if locales == '':
        locales += locale
    else:
        locales += ", " + locale
event.source.parent.getComponent('Text Field').text = locales
```


---



---

# system.util.getAvailableTerms

**版本：** 8.1
**型別：** Scripting
**分類：** Util

## 詳述

This function is used inPython Scripting. Returns a collection of available terms defined in the translation system. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.util.getAvailableTerms()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.util.getAvailableTerms()
```

### Example 2

```python
# This code will print out a list of all of the available terms to the console.

collection = system.util.getAvailableTerms()
for term in collection:
    print term
```

### Example 3

```python
# This code will print out a list of all of the available terms to the console.

collection = system.util.getAvailableTerms()
for term in collection:
    print term
```


---



---

# system.util.getClientId

**版本：** 8.1
**型別：** Scripting
**分類：** Util

## 詳述

This function is used inPython Scripting. Returns a hex-string that represents a number unique to the running client's session. You are guaranteed that this number is unique between all running clients. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.util.getClientId()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.util.getClientId()
```

### Example 2

```python
# This code prints the current client's id to the debug console.
id = system.util.getClientId()
print id
```

### Example 3

```python
# This code prints the current client's id to the debug console.
id = system.util.getClientId()
print id
```


---



---

# system.util.getConnectTimeout

**版本：** 8.1
**型別：** Scripting
**分類：** Util

## 詳述

This function is used inPython Scripting. Returns the connect timeout in milliseconds for all client-to-gateway communication. This is the maximum amount of time that communication operations to the Gateway will be given to connect. The default is 10,000ms (10 seconds). This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.util.getConnectTimeout()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.util.getConnectTimeout()
```

### Example 2

```python
# This code would print out the current connect timeout
print system.util.getConnectTimeout()
```

### Example 3

```python
# This code would print out the current connect timeout
print system.util.getConnectTimeout()
```


---



---

# system.util.getConnectionMode

**版本：** 8.1
**型別：** Scripting
**分類：** Util

## 詳述

This function is used inPython Scripting. Retrieves this client session's current connection mode. 3 is read/write, 2 is read-only, and 1 is disconnected. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.util.getConnectionMode()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.util.getConnectionMode()
```

### Example 2

```python
# This code will set a client to read-only after a timeout of 30 seconds.
# Add this code to a client timer script

mode = system.util.getConnectionMode()
if mode == 3 and system.util.getInactivitySeconds() > 30:
    system.util.setConnectionMode(2)
```

### Example 3

```python
# This code will set a client to read-only after a timeout of 30 seconds.
# Add this code to a client timer script

mode = system.util.getConnectionMode()
if mode == 3 and system.util.getInactivitySeconds() > 30:
    system.util.setConnectionMode(2)
```


---



---

# system.util.getEdition

**版本：** 8.1
**型別：** Scripting
**分類：** Util

## 詳述

This function is used inPython Scripting. Returns the "edition" of the Vision client - "standard", "limited", or "panel". This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.util.getEdition()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.util.getEdition()
```

### Example 2

```python
# This code will write the Vision module edition to a text field on the same page.

event.source.parent.getComponent('Text Field').text = system.util.getEdition()
```

### Example 3

```python
# This code will write the Vision module edition to a text field on the same page.

event.source.parent.getComponent('Text Field').text = system.util.getEdition()
```


---



---

# system.util.getGatewayAddress

**版本：** 8.1
**型別：** Scripting
**分類：** Util

## 詳述

This function is used inPython Scripting. Returns the address of the Gateway with which the Client is currently communicating. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.util.getGatewayAddress()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.util.getGatewayAddress()
```

### Example 2

```python
# This code would open up the gateway config page.
address = system.util.getGatewayAddress()
system.net.openURL("%s/web/config/" % address)
```

### Example 3

```python
# This code would open up the gateway config page.
address = system.util.getGatewayAddress()
system.net.openURL("%s/web/config/" % address)
```


---



---

# system.util.getGatewayStatus

**版本：** 8.1
**型別：** Scripting
**分類：** Util

## 詳述

This function is used inPython Scripting. Returns a string that indicates the status of a Gateway. A status ofRUNNINGmeans the Gateway is fully functional. If an exception occurs, the function returnsERRORwith the associated error message appended. This function can be used to test the availability and operational state of a remote Gateway. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.util.getGatewayStatus(gatewayAddress, [connectTimeoutMillis], [socketTimeoutMillis])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| gatewayAddress | String | The Gateway address to ping, in the form of ADDR:PORT. |
| connectTimeoutMillis | Integer | The maximum time in milliseconds to attempt to initially contact a Gateway. [optional] |
| socketTimeoutMillis | Integer | The maximum time in milliseconds to wait for a response from a Gateway after initial connection has been established. [optional] |
| bypassCertValidation | Boolean | If the target address is an HTTPS address, and this parameter is True, the system will bypass all SSL certificate validation. This is not recommended, though is sometimes necessary for self-signed certificates. |

## 回傳值

**型別：** Object

## 範例

### Example 3

```python
system.util.getGatewayStatus(gatewayAddress, [connectTimeoutMillis], [socketTimeoutMillis])
```


---



---

# system.util.getGlobals

**版本：** 8.1
**型別：** Scripting
**分類：** Util

## 詳述

This function is used inPython Scripting. This method returns a dictionary that provides access to the legacy global namespace. As of version 7.7.0, most new scripts use the modern style of scoping, which makes the 'global' keyword act very differently. Most importantly, the modern scoping rules mean that variables declared as 'global' are only global within that one module. The system.util.getGlobals() method can be used to interact with older scripts that used the old meaning of the 'global' k

## 語法

```python
system.util.getGlobals()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.util.getGlobals()
```

### Example 2

```python
# Read and print out global variable 'foo'
print system.util.getGlobals()['foo']
```

### Example 3

```python
# Read and print out global variable 'foo'
print system.util.getGlobals()['foo']
```


---



---

# system.util.getInactivitySeconds

**版本：** 8.1
**型別：** Scripting
**分類：** Util

## 詳述

This function is used inPython Scripting. Returns the number of seconds since any keyboard or mouse activity. This function will always return zero in the Designer.

## 語法

```python
system.util.getInactivitySeconds()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.util.getInactivitySeconds()
```

### Example 2

```python
# This code could run in a global timer script.
# After a 5-minute timeout, navigate back to the home screen
if system.util.getInactivitySeconds()>300 and system.nav.getCurrentWindow()!="Home":
   system.nav.swapTo("Home")
```

### Example 3

```python
# This code could run in a global timer script.
# After a 5-minute timeout, navigate back to the home screen
if system.util.getInactivitySeconds()>300 and system.nav.getCurrentWindow()!="Home":
   system.nav.swapTo("Home")
```


---



---

# system.util.getLocale

**版本：** 8.1
**型別：** Scripting
**分類：** Util

## 詳述

This function is used inPython Scripting. Returns the current string representing the user's Locale, such as 'en' for English. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.util.getLocale()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.util.getLocale()
```

### Example 2

```python
# print a test if they are using English
locale = system.util.getLocale()
if locale == "en":
    print "Using English"
```

### Example 3

```python
# print a test if they are using English
locale = system.util.getLocale()
if locale == "en":
    print "Using English"
```


---



---

# system.util.getLogger

**版本：** 8.1
**型別：** Scripting
**分類：** Util

## 詳述

This function is used inPython Scripting. Returns a Logger object that can be used to log messages to the console. Each Logger has a name, which is typically structured hierarchically using periods, indicating where in the project the Logger is used. You can use any naming scheme you like, however a well-planned naming scheme makes finding  log entries and setting log levels much easier. Loggers can be shared between scripts simply by giving them the same name. Six levels of logging are availabl

## 語法

```python
system.util.getLogger(name)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| name | String | The name of a logger to create. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.util.getLogger(name)
```

### Example 3

```python
# This code would log a message with level info
logger = system.util.getLogger("myLogger")
logger.info("Hello, world.")
```


---



---

# system.util.getModules

**版本：** 8.1
**型別：** Scripting
**分類：** Util

## 詳述

This function is used inPython Scripting. Returns a dataset of information about each installed module. Each row represents a single module. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.util.getModules()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.util.getModules()
```

### Example 2

```python
#Return the names of all installed modules

results = system.util.getModules()
for row in range(results.rowCount):
    names = results.getValueAt(row, "Name")
    print names
```

### Example 3

```python
#Return the names of all installed modules

results = system.util.getModules()
for row in range(results.rowCount):
    names = results.getValueAt(row, "Name")
    print names
```


---



---

# system.util.getProjectName

**版本：** 8.1
**型別：** Scripting
**分類：** Util

## 詳述

This function is used inPython Scripting. Returns the name of the project that is currently being run. When run from the Gateway scope from a resource that originates from a singular project (reports, SFCs, etc.), will return that resources project. When called from a scope that does not have an associated project (a Tag Event Script), the function will return the name of the Gateway scripting project. If a Gateway scripting project has not been configured, then returns an empty string.

## 語法

```python
system.util.getProjectName()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.util.getProjectName()
```

### Example 2

```python
# This code would display the name of the currently running project
system.gui.messageBox("You are running project: %s" % system.util.getProjectName())
```

### Example 3

```python
# This code would display the name of the currently running project
system.gui.messageBox("You are running project: %s" % system.util.getProjectName())
```


---



---

# system.util.getProperty

**版本：** 8.1
**型別：** Scripting
**分類：** Util

## 詳述

This function is used inPython Scripting. Retrieves the value of a named system property. Some of the available properties are: This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.util.getProperty(propertyName)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| propertyName | String | The name of the system property to get. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.util.getProperty(propertyName)
```

### Example 2

```python
propertyName
```

### Example 3

```python
# This script would store the contents of the Text Area component in the users home directory.
homeDir = system.util.getProperty("user.home")
sep = system.util.getProperty("file.separator")
path = "%s%smyfile.txt" %(homeDir, sep)
system.file.writeFile(path, event.source.parent.getComponent("Text Area").text)
```


---



---

# system.util.getReadTimeout

**版本：** 8.1
**型別：** Scripting
**分類：** Util

## 詳述

This function is used inPython Scripting. Returns the read timeout in milliseconds for all client-to-gateway communication. This is the maximum amount of time allowed for a communication operation to complete. The default is 60,000ms (1 minute). This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.util.getReadTimeout()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.util.getReadTimeout()
```

### Example 2

```python
# This code will find the current read timeout and write it to a numeric text field on the same page.

event.source.parent.getComponent('Numeric Text Field').intValue = system.util.getReadTimeout()
```

### Example 3

```python
# This code will find the current read timeout and write it to a numeric text field on the same page.

event.source.parent.getComponent('Numeric Text Field').intValue = system.util.getReadTimeout()
```


---



---

# system.util.getSessionInfo

**版本：** 8.1
**型別：** Scripting
**分類：** Util

## 詳述

This function is used inPython Scripting. Returns a PyDataSet holding information about all of the open Designer sessions and Vision Clients. Optional regular-expression based filters can be provided to filter the username or the username and the project returned. This function will not return all sessions across a cluster - only the cluster node that is being communicated with by the client who makes the call.

## 語法

```python
system.util.getSessionInfo([usernameFilter], [projectFilter])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| usernameFilter | String | A regular-expression based filter string to restrict the list by username. [optional] |
| projectFilter | String | A regular-expression based filter string to restrict the list by project [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.util.getSessionInfo([usernameFilter], [projectFilter])
```

### Example 2

```python
usernameFilter
```

### Example 3

```python
projectFilter
```


---



---

# system.util.getSystemFlags

**版本：** 8.1
**型別：** Scripting
**分類：** Util

## 詳述

This function is used inPython Scripting. Returns an integer that represents a bit field containing information about the currently running system. Each bit corresponds to a specific flag as defined in the bitmask below. The integer return will be a total of all of the bits that are currently active. See the example for tips on how to extract the information in this bit field. Note that the tag[System]Client/System/SystemFlagscontains the same value. This scripting function has noClient Permissi

## 語法

```python
system.util.getSystemFlags()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
[System]Client/System/SystemFlags
```

### Example 2

```python
system.util.getSystemFlags()
```

### Example 3

```python
# The first part of the script will take the integer representing the system flags, convert it to bits, and place it in a list and then print it out.
# The second part of the script will take the list of bits, and place it in a table showing what each of the bits represent.

myList = []
flags = system.util.getSystemFlags()
for i in range(8,-1,-1):
    myList.insert(0, flags >> i & 1)
print myList

headers = ["Designer Flag", "Preview Flag", "Client Flag", "Webstart Flag", "Applet Flag", "Fullscreen Flag", "SSL Flag", "Mobile Flag", "Staging Flag"]
data = system.dataset.toDataSet(headers, [myList])
table = event.source.parent.getComponent("Table")
table.data = data
```


---



---

# system.util.getVersion

**版本：** 8.1
**型別：** Scripting
**分類：** Util

## 詳述

This function is used inPython Scripting. Returns the Ignition version number that is currently being run. If the version is from a nightly build or developer version that is not yet released, the version number will come back as "Dev Version", for example:

## 語法

```python
system.util.getVersion()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.util.getVersion()
```

### Example 2

```python
# This code displays the name of the currently running Ignition version number.
system.gui.messageBox("You are running project: %s" % system.util.getVersion())
```

### Example 3

```python
# This code displays the name of the currently running Ignition version number.
system.gui.messageBox("You are running project: %s" % system.util.getVersion())
```


---



---

# system.util.invokeAsynchronous

**版本：** 8.1
**型別：** Scripting
**分類：** Util

## 詳述

This function is used inPython Scripting. Invokes (calls) the given Python function on a different thread. This means that calls to invokeAsynchronous will return immediately, and then the given function will start executing asynchronously on a different thread. This is useful for long-running data intensive functions, where running them synchronously (in the GUI thread) would make the GUI non-responsive for an unacceptable amount of time. This function should not be used to asynchronously inter

## 語法

```python
system.util.invokeAsynchronous(function, [args], [kwargs], [description])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| function | Callable | A Python function object that will be invoked in a newly created thread. |
| args | List [Any] | A list or tuple of Python objects that will be provided to the called function as arguments. Equivalent to the *operator. [optional] |
| kwargs | Dictionary[String, Any] | A dictionary of keyword argument names to Python object values that will be provided to the called function as keyword arguments. Equivalent to the **operator.  [optional] |
| description | String | A description to use for the asynchronous thread. Will be displayed on the current scope's diagnostic view for scripts. For Vision and the Designer, this would be the "Scripts" tab of the Diagnostics popup. For Perspective and the Gateway scope, this would be the Gateway'sRunning Scriptsstatus page. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.util.invokeAsynchronous(function, [args], [kwargs], [description])
```


---



---

# system.util.invokeLater

**版本：** 8.1
**型別：** Scripting
**分類：** Util

## 詳述

This function is used inPython Scripting. Invokes (calls) the given Python function object after all of the currently processing and pending events are done being processed, or after a specified delay. The function will be executed on the GUI, or event dispatch, thread. This is useful for events like propertyChange events, where the script is called before any bindings are evaluated. If you specify an optional time argument (number of milliseconds), the function will be invoked after all current

## 語法

```python
system.util.invokeLater(function, [delay])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| function | Callable | A Python function object that will be invoked later, on the GUI, or event-dispatch, thread with no arguments. |
| delay | Integer | A delay, in milliseconds, to wait before the function is invoked. The default is 0, which means it will be invoked after all currently pending events are processed. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.util.invokeLater(function, [delay])
```


---



---

# system.util.jsonDecode

**版本：** 8.1
**型別：** Scripting
**分類：** Util

## 詳述

This function is used inPython Scripting. Takes a JSON string and converts it into a Python object such as a list or a dictionary. If the input is not valid JSON, a string is returned. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.util.jsonDecode(jsonString)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| jsonString | String | The JSON string to decode into a Python object. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.util.jsonDecode(jsonString)
```

### Example 3

```python
# The following example reads in a JSON string, and converts the string to a Python object.
# The example attempts to read the JSON string from a text file, but this could easily be modified to read data from a web server.

# Read the JSON string
jsonString = system.file.readFileAsString("C:\tmp\\json.txt")

# Decode the JSON string and store the results into a variable
obj = system.util.jsonDecode(jsonString)

# Do something with the results. The code below prints the datatype of the results to the console.
print type(obj)
```


---



---

# system.util.jsonEncode

**版本：** 8.1
**型別：** Scripting
**分類：** Util

## 詳述

This function is used inPython Scripting. Takes a Python object such as a list or dictionary and converts into a JSON string. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.util.jsonEncode(pyObj, [indentFactor])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| pyObj | Any | The Python object to encode into JSON such as a Python list or dictionary. |
| indentFactor | Integer | The number of spaces to add to each level of indentation for prettyprinting. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.util.jsonEncode(pyObj, [indentFactor])
```

### Example 3

```python
indentFactor
```


---



---

# system.util.modifyTranslation

**版本：** 8.1
**型別：** Scripting
**分類：** Util

## 詳述

This function is used inPython Scripting. This function allows you to add or modify a global translation. Permission Type: Translation Management

## 語法

```python
system.util.modifyTranslation(term, translation, [locale])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| term | String | The key term to translate. |
| translation | String | The translated value to store. |
| locale | String | If specified, the locale code (such as "es") identifying the language of the translation. Otherwise, the currently set language is used.[optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.util.modifyTranslation(term, translation, [locale])
```

### Example 3

```python
translation
```


---



---

# system.util.playSoundClip

**版本：** 8.1
**型別：** Scripting
**分類：** Util

## 詳述

This function is used inPython Scripting. Plays a sound clip from a  wav  file to the system's default audio device. The  wav  file can be specified as a filepath, a URL, or directly as a raw List[Byte]. While this function is technically scoped for Gateway and Perspective Sessions, it's intended for use in Vision Clients.

## 語法

```python
system.util.playSoundClip(wavBytes, [volume], [wait])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| wavBytes | List[Byte] | A byte list of a wav file. |
| volume | Float | The clip's volume, represented as a floating point number between 0.0 and 1.0. [optional] |
| wait | Boolean | A boolean flag indicating whether or not the call to playSoundClip should block further script execution within the triggering event until the clip finishes. Useful in cases where code on lines after the playSoundClip call should wait until the sound clip finishes playing. [optional] |
| wavFile | String | A filepath or URL that represents a wav file. |
| volume | Float | The clip's volume, represented as a floating point number between 0.0 and 1.0. [optional] |
| wait | Boolean | A boolean flag indicating whether or not the call to playSoundClip should block further script execution within the triggering event until the clip finishes. Useful in cases where code on lines after the playSoundClip call should wait until the sound clip finishes playing. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.util.playSoundClip(wavBytes, [volume], [wait])
```


---



---

# system.util.queryAuditLog

**版本：** 8.1
**型別：** Scripting
**分類：** Util

## 詳述

This function is used inPython Scripting. Queries an audit profile for audit history. Returns the results as a dataset. A description of the returned dataset can be found on theIgnition Database Table Referencepage.

## 語法

```python
system.util.queryAuditLog(auditProfileName, [startDate], [endDate], [actorFilter], [actionFilter], [targetFilter], [valueFilter], [systemFilter], [contextFilter])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| auditProfileName | String | The name of the audit profile to pull the history from. |
| startDate | Date | The earliest audit event to return. If omitted, the current time - 8 hours will be used. [optional] |
| endDate | Date | The latest audit event to return. If omitted, the current time will be used. [optional] |
| actorFilter | String | A filter string used to restrict the results by actor. [optional] |
| actionFilter | String | A filter string used to restrict the results by action. [optional] |
| targetFilter | String | A filter string used to restrict the results by target. [optional] |
| valueFilter | String | A filter string used to restrict the results by value. [optional] |
| systemFilter | String | A filter string used to restrict the results by system. [optional] |
| contextFilter | Integer | A bitmask used to restrict the results by context. 0x01 = Gateway, 0x02 = Designer, 0x04 = Client. [optional] |
| auditProfileName | String | The name of the audit profile to pull the history from. [optional]Note:The project must have an Audit Profile configured in Project Properties. Otherwise this parameter is mandatory. |
| startDate | Date | The earliest audit event to return. If omitted, the current time - 8 hours will be used. [optional] |
| endDate | Date | The latest audit event to return. If omitted, the current time will be used. [optional] |
| actorFilter | String | A filter string used to restrict the results by actor. [optional] |
| actionFilter | String | A filter string used to restrict the results by action. [optional] |
| targetFilter | String | A filter string used to restrict the results by target. [optional] |
| valueFilter | String | A filter string used to restrict the results by value. [optional] |
| systemFilter | String | A filter string used to restrict the results by system. [optional] |
| contextFilter | Integer | A bitmask used to restrict the results by context. 0x01 = Gateway, 0x02 = Designer, 0x04 = Client. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.util.queryAuditLog(auditProfileName, [startDate], [endDate], [actorFilter], [actionFilter], [targetFilter], [valueFilter], [systemFilter], [contextFilter])
```

### Example 2

```python
auditProfileName
```


---



---

# system.util.retarget

**版本：** 8.1
**型別：** Scripting
**分類：** Util

## 詳述

This function is used inPython Scripting. This function allows you to programmatically 'retarget' a Vision Client to a different project and/or different Gateway. You can have it switch to another project on the same Gateway, or another Gateway entirely, even across a WAN. This feature makes the vision of a seamless, enterprise-wide SCADA application a reality. The retarget feature will attempt to transfer the current user credentials over to the new project / Gateway. If the credentials fail on

## 語法

```python
system.util.retarget(project, [addresses], [params], [windows])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| project | String | The name of the project to retarget to. |
| addresses | String or List | The address of the Gateway that the project resides on. If omitted, the current Gateway will be used. Format ishost:portwhen not using SSL/TLS, orhttps://host:portwhen SSL/TLS is enabled on the target gateway. This can be a list of strings. When using a list, the function will try each address in order, waiting for the timeout period between each address attempt. [optional] |
| params | Dictionary[String, Any] | A dictionary of parameters that will be passed to the new project. They will be set as global variables in the new project's Python scripting environment. [optional] |
| windows | List[String] | A list of window paths to use as the startup windows. If omitted, the project's normal startup windows will be opened. If specified, the project's normal startup windows will be ignored, and this list will be used instead. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.util.retarget(project, [addresses], [params], [windows])
```


---



---

# system.util.sendMessage

**版本：** 8.1
**型別：** Scripting
**分類：** Util

## 詳述

This function is used inPython Scripting. This function sends a message to clients running under the Gateway or to a project within the Gateway itself. To handle received messages, you must set up event script message handlers within a project. These message handlers run Jython code when a message is received. You can add message handlers under theMessagesection of the client/Gateway event script configuration dialogs. Messages cannot be received within a Designer. However, messages can be sent 

## 語法

```python
system.util.sendMessage(project, messageHandler, [payload], [scope], [clientSessionId], [user], [hasRole], [hostName], [remoteServers])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| project | String | The name of the project containing the message handler. |
| messageHandler | String | The name of the message handler that will fire upon receiving a message. |
| payload | Dictionary[String, Any] | A dictionary which will get passed to the message handler. Use "payload" in the message handler to access dictionary variables. [optional] |
| scope | String | Limits the scope of the message delivery to "C" (clients), "G" (Gateway), "CG" for clients and the Gateway, or "S" Session. Any combination of C, G, and S are available. Defaults to "CS" if the user name, role, or host name parameters are set, and to "CGS" if none of these parameters are set. [optional] |
| clientSessionId | String | Limits the message delivery to a client with the specified session ID. [optional] |
| user | String | Limits the message delivery to clients where the specified user has logged in. [optional] |
| hasRole | String | Limits the message delivery to any client where the logged in user has the specified user role. [optional] |
| hostName | String | Limits the message delivery to the client that has the specified network host name. [optional] |
| remoteServers | List | A list of Strings representing Gateway Server names. The message will be delivered to each server in the list. Upon delivery, the message is distributed to the local Gateway and clients as per the other parameters. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.util.sendMessage(project, messageHandler, [payload], [scope], [clientSessionId], [user], [hasRole], [hostName], [remoteServers])
```

### Example 3

```python
messageHandler
```


---



---

# system.util.sendRequest

**版本：** 8.1
**型別：** Scripting
**分類：** Util

## 詳述

This function is used inPython Scripting. This function sends a message to the Gateway, working in a similar manner to thesendMessagefunction, except sendRequest expects a response to the message. To handle received messages, you must set up Gateway Event Script message handlers within a project. These message handlers run Jython code when a message is received. You can then place a return at the end of the code to return something to where the sendRequest was originally called from. You can add

## 語法

```python
system.util.sendRequest(project, messageHandler, [payload], [remoteServer], [timeoutSec])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| project | String | The name of the project containing the message handler. |
| messageHandler | String | The name of the message handler that will fire upon receiving a message. |
| payload | Dictionary[String, Any] | A dictionary which will get passed to the message handler. Use "payload" in the message handler to access dictionary variables. [optional] |
| hostName | String | Limits the message delivery to the client that has the specified network host name. [optional] |
| remoteServer | String | A string representing a target Gateway Server name. The message will be delivered to the remote Gateway over the Gateway Network. Upon delivery, the message is distributed to the local Gateway and clients as per the other parameters. [optional] |
| timeoutSec | String | The number of seconds before the sendRequest call times out. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.util.sendRequest(project, messageHandler, [payload], [remoteServer], [timeoutSec])
```

### Example 3

```python
messageHandler
```


---



---

# system.util.sendRequestAsync

**版本：** 8.1
**型別：** Scripting
**分類：** Util

## 詳述

This function is used inPython Scripting. This function sends a message to the Gateway and expects a response. Works in a similar manner to thesendRequestfunction, except sendRequestAsync will send the request and then immediately return a handle for it. The Request handle has the following methods: This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.util.sendRequestAsync(project, messageHandler, [payload], [remoteServer], [timeoutSec], [onSuccess], [onError])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| project | String | The name of the project containing the message handler. |
| messageHandler | String | The name of the message handler that will fire upon receiving a message. |
| payload | Dictionary[String, Any] | A dictionary which will get passed to the message handler. Use "payload" in the message handler to access dictionary variables. [optional] |
| hostName | String | Limits the message delivery to the client that has the specified network host name. [optional] |
| remoteServer | String | A string representing the target Gateway server name. The message will be delivered to the remote Gateway over the Gateway Network. Upon delivery, the message is distributed to the local Gateway and clients as per the other parameters. [optional] |
| timeoutSec | String | The number of seconds before the sendRequest call times out. [optional] |
| onSuccess | Callable | Should take one argument, which will be the result from the message handler. Callback functions will be executed on the GUI thread, similar tosystem.util.invokeLater. [optional] |
| onError | Callable | Should take one argument, which will be the exception encountered. Callback functions will be executed on the GUI thread, similar tosystem.util.invokeLater. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.util.sendRequestAsync(project, messageHandler, [payload], [remoteServer], [timeoutSec], [onSuccess], [onError])
```

### Example 3

```python
messageHandler
```


---



---

# system.util.setConnectTimeout

**版本：** 8.1
**型別：** Scripting
**分類：** Util

## 詳述

This function is used inPython Scripting. Sets the connect timeout for Client-to-Gateway communication. Specified in milliseconds. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.util.setConnectTimeout(connectTimeout)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| connectTimeout | Integer | The new connect timeout, specified in milliseconds. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.util.setConnectTimeout(connectTimeout)
```

### Example 2

```python
connectTimeout
```

### Example 3

```python
# This code would set the current connect timeout to 30 seconds
system.util.setConnectTimeout(30000)
```


---



---

# system.util.setConnectionMode

**版本：** 8.1
**型別：** Scripting
**分類：** Util

## 詳述

This function is used inPython Scripting. Sets the connection mode for the client session. Normally a client runs in mode 3, which is read-write. You may wish to change this to mode 2, which is read-only, which will only allow reading and subscribing to tags, and running SELECT queries. Tag writes and INSERT/UPDATE/DELETE queries will not function. You can also set the connection mode to mode 1, which is disconnected, all tag and query features will not work. This scripting function has noClient

## 語法

```python
system.util.setConnectionMode(mode)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| mode | Integer | The new connection mode. 1 = Disconnected, 2 = Read-only, 3 = Read/Write. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.util.setConnectionMode(mode)
```

### Example 3

```python
# This example, which could go in a project's startup script, would check the current username
# and set the connection mode to read-only if it is the "guest" user.

username = system.security.getUsername()
if "guest" == username.lower():
   # Set "guest" user to read-only mode
   system.util.setConnectionMode(2)
else:
   system.util.setConnectionMode(3)
```


---



---

# system.util.setLocale

**版本：** 8.1
**型別：** Scripting
**分類：** Util

## 詳述

This function is used inPython Scripting. Sets the user's current Locale. Any valid Java locale code (case-insensitive) can be used as a parameter, including ones that have not yet been added to the Translation Manager. An invalid locale code will cause an Illegal Argument Exception. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.util.setLocale(locale)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| locale | Object | Changed in8.1.22A locale code, such as "en_US" for US English, or a java.util.Locale object. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.util.setLocale(locale)
```

### Example 3

```python
# This script will set the client locale to Arabic.

system.util.setLocale('ar')
```


---



---

# system.util.setLoggingLevel

**版本：** 8.1
**型別：** Scripting
**分類：** Util

## 詳述

This function is used inPython Scripting. Sets the logging level on the given logger. This can be a logger you create, or a logger already defined in the system. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.util.setLoggingLevel(loggerName, loggerLevel)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| loggerName | String | The unique name of the logger to change the logging level on, for example "Tags.Client". |
| loggerLevel | String | The level you want to change to logger to: "trace", "debug", "info", "warn" or "error". |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.util.setLoggingLevel(loggerName, loggerLevel)
```

### Example 3

```python
loggerLevel
```


---



---

# system.util.setReadTimeout

**版本：** 8.1
**型別：** Scripting
**分類：** Util

## 詳述

This function is used inPython Scripting. Sets the read timeout for Client-to-Gateway communication. Specified in milliseconds. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.util.setReadTimeout(readTimeout)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| readTimeout | Integer | The new read timeout, specified in milliseconds. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.util.setReadTimeout(readTimeout)
```

### Example 2

```python
readTimeout
```

### Example 3

```python
# This script will set the read timeout to 20 seconds.

system.util.setReadTimeout(20000)
```


---



---

# system.util.threadDump

**版本：** 8.1
**型別：** Scripting
**分類：** Util

## 詳述

This function is used inPython Scripting. Creates a thread dump of the current running JVM. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.util.threadDump()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.util.threadDump()
```

### Example 2

```python
# This script will take a thread dump of the current JVM, and write it to a Text Area component.

event.source.parent.getComponent('Text Area').text = system.util.threadDump()
```

### Example 3

```python
# This script will take a thread dump of the current JVM, and write it to a Text Area component.

event.source.parent.getComponent('Text Area').text = system.util.threadDump()
```


---



---

# system.util.translate

**版本：** 8.1
**型別：** Scripting
**分類：** Util

## 詳述

This function is used inPython Scripting. This function allows you to retrieve the global translation of a term from the translation database using the current locale. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.util.translate(term, [locale], [strict])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| term | String | The term to look up. |
| locale | String | Which locale to translate against. Useful when there are multiple locales defined for a single term. If omitted, the function attempts to use the current locale (as defined by the client, session, or Designer). [optional] |
| strict | Boolean | If false, the function will return the passed term (param 1) if it could not find a defined translation for the locale: meaning, if you pass a term that hasn't been configured, the function will just send the term back to you. If true, then the function will return a None when it fails to find a defined translation. Default is false. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.util.translate(term, [locale], [strict])
```


---

