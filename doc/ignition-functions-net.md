# Ignition 8.1 - system.net 函數文檔

﻿# Ignition 8.1 - 函數文檔（PATTERN 規範）

> 根據 FUNCTION_PATTERN 爬蟲生成
> 生成時間: 2026年04月19日 00:56:44
> 總計函式數: 434

## 📑 目錄

---

1. [system.net.getExternalIpAddress](#systemnetgetexternalipaddress) - This function is used inPython Scripting. Returns the Client's IP address, as it is detected by the Gateway. This means that this call will communicate with the Gateway, and the Gateway will tell the Client what IP address its incoming traffic is coming from. If you have a client behind a Network Address Translation (NAT) router, then this address will be the Wide Area Network (WAN) address of the router instead of the Local Area Network (LAN) address of the Client, which is what you'd get withs
2. [system.net.getHostName](#systemnetgethostname) - This function is used inPython Scripting. Returns the host name of the computer that the script was ran on. When run in the Gateway scope, returns the Gateway hostname. When run in the Client scope, returns the Client hostname. On Windows, this is typically the "computer name." For example, might return EAST_WING_WORKSTATION or bobs-laptop. This scripting function has noClient Permissionrestrictions.
3. [system.net.getIpAddress](#systemnetgetipaddress) - This function is used inPython Scripting. Returns the IP address of the computer that the script was ran on. When run in the Gateway scope, returns the Gateway IP address. When run in the Client scope, returns the Client IP address. This scripting function has noClient Permissionrestrictions.
4. [system.net.getRemoteServers](#systemnetgetremoteservers) - This function is used inPython Scripting. This function returns a list of Gateway Network servers that are visible from the local Gateway. This scripting function has noClient Permissionrestrictions.
5. [system.net.httpClient](#systemnethttpclient) - This function is used inPython Scripting. Provides a general use object that can be used to send and receive HTTP requests. The object created by this function is a wrapper around Java's HttpClient class. Usage requires creating aJythonHttpClientobject with a call tosystem.net.httpClient, then calling a method (such asget(),post()) on theJythonHttpClientto actually issue a request. To learn more about Java's HttpClient class, click the link corresponding to your version of Ignition:
6. [system.net.httpDelete](#systemnethttpdelete) - This function is used inPython Scripting. Performs an HTTP DELETE to the given URL. Keep in mind thatJRE proxy settingswill influence how these functions conduct their network activities.
7. [system.net.httpGet](#systemnethttpget) - This function is used inPython Scripting. Retrieves the document at the given URL using the HTTP GET protocol. The document is returned as a string. For example, if you use the URL of a website, you'll get the same thing you'd get by going to that website in a browser and using the browser's "View Source" function. Keep in mind thatJRE proxy settingswill influence how these functions conduct their network activities.
8. [system.net.httpPost](#systemnethttppost) - This function is used inPython Scripting. Retrieves the document at the given URL using the HTTP POST protocol. If a parameter dictionary argument is specified, the entries in the dictionary will encoded in "application/x-www-form-urlencoded" format, and then posted. You can post arbitrary data as well, but you'll need to specify the MIME type. The document is then returned as a string. Keep in mind thatJRE proxy settingswill influence how these functions conduct their network activities.
9. [system.net.httpPut](#systemnethttpput) - This function is used inPython Scripting. Performs an HTTP PUT to the given URL. Encodes the given dictionary of parameters using "applications/x-www-form-urlencoded" format. Keep in mind thatJRE proxy settingswill influence how these functions conduct their network activities.
10. [system.net.openURL](#systemnetopenurl) - This function is used inPython Scripting. Opens the given URL or URI scheme outside of the currently running Client in whatever application the host operating system deems appropriate. For example, the URL: will open in the default web browser, whereas this one:
11. [system.net.sendEmail](#systemnetsendemail) - This function is used inPython Scripting. Sends an email through the given SMTP server. Note that this email is relayed first through the Gateway; the Client host machine doesn't need network access to the SMTP server. Note that you can use this function to send emails as text messages. Most phone service providers offer a domain that can be used to convert emails into text messages. For example:1234567890@phone.domain.com. Contact your cell carrier for details.

---

# system.net.getExternalIpAddress

**版本：** 8.1
**型別：** Scripting
**分類：** Net

## 詳述

This function is used inPython Scripting. Returns the Client's IP address, as it is detected by the Gateway. This means that this call will communicate with the Gateway, and the Gateway will tell the Client what IP address its incoming traffic is coming from. If you have a client behind a Network Address Translation (NAT) router, then this address will be the Wide Area Network (WAN) address of the router instead of the Local Area Network (LAN) address of the Client, which is what you'd get withs

## 語法

```python
system.net.getExternalIpAddress()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.net.getExternalIpAddress()
```

### Example 2

```python
# Put this script on a navigation button to restrict users from opening a specific page.

ip = system.net.getExternalIpAddress()
# check if this matches the CEO's IP address
if ip == "66.102.7.104":
   system.nav.swapTo("CEO Dashboard")
else:
   system.nav.swapTo("Manager Dashboard")
```

### Example 3

```python
# Put this script on a navigation button to restrict users from opening a specific page.

ip = system.net.getExternalIpAddress()
# check if this matches the CEO's IP address
if ip == "66.102.7.104":
   system.nav.swapTo("CEO Dashboard")
else:
   system.nav.swapTo("Manager Dashboard")
```


---



---

# system.net.getHostName

**版本：** 8.1
**型別：** Scripting
**分類：** Net

## 詳述

This function is used inPython Scripting. Returns the host name of the computer that the script was ran on. When run in the Gateway scope, returns the Gateway hostname. When run in the Client scope, returns the Client hostname. On Windows, this is typically the "computer name." For example, might return EAST_WING_WORKSTATION or bobs-laptop. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.net.getHostName()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.net.getHostName()
```

### Example 2

```python
# Put this script on a navigation button to link dedicated machines to specific screens.
comp = system.net.getHostName()
# check which line this client is tied to
if comp == "Line1Computer":
   system.nav.swapTo("Line Detail", {"line":1})
elif comp == "Line2Computer":
   system.nav.swapTo("Line Detail", {"line":2})
else:
   system.nav.swapTo("Line Overview")
```

### Example 3

```python
# Put this script on a navigation button to link dedicated machines to specific screens.
comp = system.net.getHostName()
# check which line this client is tied to
if comp == "Line1Computer":
   system.nav.swapTo("Line Detail", {"line":1})
elif comp == "Line2Computer":
   system.nav.swapTo("Line Detail", {"line":2})
else:
   system.nav.swapTo("Line Overview")
```


---



---

# system.net.getIpAddress

**版本：** 8.1
**型別：** Scripting
**分類：** Net

## 詳述

This function is used inPython Scripting. Returns the IP address of the computer that the script was ran on. When run in the Gateway scope, returns the Gateway IP address. When run in the Client scope, returns the Client IP address. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.net.getIpAddress()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.net.getIpAddress()
```

### Example 2

```python
# Put this script on a navigation button to link dedicated machines to specific screens.
ip = system.net.getIpAddress()
# check which line this client is tied to
if ip == "10.1.10.5":
   system.nav.swapTo("Line Detail", {"line":1})
elif ip == "10.1.10.6":
   system.nav.swapTo("Line Detail", {"line":2})
else:
   system.nav.swapTo("Line Overview")
```

### Example 3

```python
# Put this script on a navigation button to link dedicated machines to specific screens.
ip = system.net.getIpAddress()
# check which line this client is tied to
if ip == "10.1.10.5":
   system.nav.swapTo("Line Detail", {"line":1})
elif ip == "10.1.10.6":
   system.nav.swapTo("Line Detail", {"line":2})
else:
   system.nav.swapTo("Line Overview")
```


---



---

# system.net.getRemoteServers

**版本：** 8.1
**型別：** Scripting
**分類：** Net

## 詳述

This function is used inPython Scripting. This function returns a list of Gateway Network servers that are visible from the local Gateway. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.net.getRemoteServers([runningOnly])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| runningOnly | Boolean | If set to true, only servers on the Gateway Network that are running will be returned. Servers that have lost contact with the Gateway Network will be filtered out. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.net.getRemoteServers([runningOnly])
```

### Example 2

```python
runningOnly
```

### Example 3

```python
# The following will create a list of running servers on the Gateway Network, and show the list in a message box.

# Collect the list of running servers
runningServers = system.net.getRemoteServers(True)

# Initialize the start of the message
serverStatusText = "The following servers are running:\n "
# Add each running server to the message
for server in runningServers:
    serverStatusText += "%s \n" % server

# Show the message
system.gui.messageBox(serverStatusText)
```


---



---

# system.net.httpClient

**版本：** 8.1
**型別：** Scripting
**分類：** Net

## 詳述

This function is used inPython Scripting. Provides a general use object that can be used to send and receive HTTP requests. The object created by this function is a wrapper around Java's HttpClient class. Usage requires creating aJythonHttpClientobject with a call tosystem.net.httpClient, then calling a method (such asget(),post()) on theJythonHttpClientto actually issue a request. To learn more about Java's HttpClient class, click the link corresponding to your version of Ignition:

## 語法

```python
get()
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| timeout | Integer | A value, in milliseconds, to set the client’s connect timeout setting to. Defaults to 60000. [optional] |
| bypass_cert_validation | Boolean | A boolean indicating whether the client should attempt to validate the certificates of remote servers, if connecting via HTTPS/SSL. Defaults to False. [optional] |
| username | String | A string indicating the username to use for authentication if the remote server requests authentication; specifically, by responding with aWWW-AuthenticateorProxy-Authenticateheader. Only supportsBasic authentication. Ifusernameis specified but not password, an empty string will be used for the password in the Basic Authentication response. Defaults to None. [optional] |
| password | String | A string indicating the password to use for authentication. Defaults to None. [optional] |
| proxy | String | The address of a proxy server, which will be used for HTTP and HTTPS traffic. If a port is not specified as part of that address, it will be assumed from the protocol in the URL, i.e. 80/443. Defaults to None. [optional] |
| cookie_policy | String | A string representing this client’s cookie policy. Accepts values "ACCEPT_ALL", "ACCEPT_NONE", and "ACCEPT_ORIGINAL_SERVER" . [Defaults to "ACCEPT_ORIGINAL_SERVER"] |
| redirect_policy | String | A string representing this client’s redirect policy. Acceptable values are listed below. Defaults to "Never". [optional]"NEVER" - never allow redirects"ALWAYS" - allow redirects"NORMAL" - allows redirects, except those that would downgrade to insecure addresses (i.e., HTTPS redirecting to HTTP) |
| version | String | New in8.1.16A string specifying eitherHTTP_2orHTTP_1_1for the HTTP protocol. When omitted, the previous default ofHTTP_2is implied. [optional] |
| customizer | Callable | A reference to a function. This function will be called with one argument (an instance of HttpClient.Builder). The function should operate on that builder instance, which allows for customization of the created HTTP client. Defaults to None. [optional] |
| url | String | The URL to connect to. [required] |
| method | String | The method to use in the request. [Required. Used by .request() and .requestAsync() only.] |
| params | String or Dictionary | URL parameters to send with the request. Defaults to None. [optional]If supplied as a string, will be directly appended to the URL.If supplied as a dictionary, key/value pairs will be automatically URL encoded. |
| data | String or Dictionary or byte[] | Data to send in the request. Defaults to None. [optional]String data will be sent with a Content-Type oftext/plain; charset=UTF-8, unless a different Content-Type header was specified.Dictionaries will be automatically encoded into JSON to send to the target server, with a Content-Type header set toapplication/json;charset=UTF-8unless a different Content-Type header was specified.Byte arrays will be streamed directly to the target server, with a Content-Type header ofapplication/octet-streamunless a different Content-Type header was specified. |
| file | String | The path to a file, relative to the HTTP client instance. If specified, and the path is valid, the data in the file will be sent to the remote server. The file attribute overrides any value set in data; only the file’s data will be sent.  Defaults to None. [optional] |
| headers | Dictionary | A dictionary of HTTP headers to send with the request.  Defaults to None. [optional] |
| username | String | Username to add to a Basic Authorization header in the outgoing request. Ifusernameis specified, but notpassword, the password is encoded as an empty string.  Defaults to None. [optional] |
| password | String | Password to add to a Basic Authorization header in the outgoing request.  Defaults to None. [optional] |
| timeout | Integer | The read timeout for this request, in milliseconds.  Defaults to 60000. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
JythonHttpClient
```

### Example 2

```python
system.net.httpClient
```


---



---

# system.net.httpDelete

**版本：** 8.1
**型別：** Scripting
**分類：** Net

## 詳述

This function is used inPython Scripting. Performs an HTTP DELETE to the given URL. Keep in mind thatJRE proxy settingswill influence how these functions conduct their network activities.

## 語法

```python
system.net.httpDelete(url, [contentType], [connectTimeout], [readTimeout], [username], [password], [headerValues], [bypassCertValidation])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| url | String | The URL to send the request to. |
| contentType | String | [Optional] The MIME type used in the HTTP 'Content-type' header. |
| connectTimeout | Int | [Optional] The timeout for connecting to the URL in milliseconds. Default is 10,000 |
| readTimeout | Int | [Optional] The read timeout for the operation in milliseconds. Default is 60,000. |
| username | String | [Optional] If specified, the call will attempt to authenticate with basic HTTP authentication. |
| password | String | [Optional] The password used for basic HTTP authentication, if the username parameter is also present. |
| headerValues | PyDictionary | [Optional] A dictionary of name/value pairs that will be set in the HTTP header. |
| bypassCertValidation | Boolean | [Optional] If the target address in an HTTPS address, and this parameter is TRUE, the system will bypass all SSL certificate validation. This is not recommended, though is sometimes necessary for self-signed certificates. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.net.httpDelete(url, [contentType], [connectTimeout], [readTimeout], [username], [password], [headerValues], [bypassCertValidation])
```

### Example 3

```python
contentType
```


---



---

# system.net.httpGet

**版本：** 8.1
**型別：** Scripting
**分類：** Net

## 詳述

This function is used inPython Scripting. Retrieves the document at the given URL using the HTTP GET protocol. The document is returned as a string. For example, if you use the URL of a website, you'll get the same thing you'd get by going to that website in a browser and using the browser's "View Source" function. Keep in mind thatJRE proxy settingswill influence how these functions conduct their network activities.

## 語法

```python
system.net.httpGet(url, connectTimeout, readTimeout, username, password, headerValues, bypassCertValidation, useCaches, throwOnError)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| url | String | The URL to retrieve. |
| connectTimeout | Integer | The timeout for connecting to the URL. In milliseconds. Default is 10,000.  [optional] |
| readTimeout | Integer | The read timeout for the get operation. In milliseconds. Default is 60,000. [optional] |
| username | String | If specified, the call will attempt to authenticate with basic HTTP authentication. [optional] |
| password | String | The password used for basic HTTP authentication, if the username parameter is also present. [optional] |
| headerValues | Dictionary[String, String] | A dictionary of name/value pairs that will be set in the HTTP header. [optional] |
| bypassCertValidation | Boolean | If the target address is an HTTPS address, and this parameter is true, the system will bypass all SSL certificate validation. This is not recommended, though is sometimes necessary for self-signed certificates. [optional] |
| useCaches | Boolean | Will cache the information returned by the httpGet call. If using this for something that constantly updates like an RSS feed, it would be better to set this to False. Default is True. [optional] |
| throwOnError | Boolean | Set to False if you wish to get the error body rather than a Python exception if the GET request returns an error code (non-200 responsive). Default is True. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.net.httpGet(url, connectTimeout, readTimeout, username, password, headerValues, bypassCertValidation, useCaches, throwOnError)
```

### Example 3

```python
connectTimeout
```


---



---

# system.net.httpPost

**版本：** 8.1
**型別：** Scripting
**分類：** Net

## 詳述

This function is used inPython Scripting. Retrieves the document at the given URL using the HTTP POST protocol. If a parameter dictionary argument is specified, the entries in the dictionary will encoded in "application/x-www-form-urlencoded" format, and then posted. You can post arbitrary data as well, but you'll need to specify the MIME type. The document is then returned as a string. Keep in mind thatJRE proxy settingswill influence how these functions conduct their network activities.

## 語法

```python
system.net.httpPost(url, postParams)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| url | String | The URL to post to. |
| postParams | Dictionary[String, String] | A dictionary of name/value key pairs to use as the post data. |
| url | String | The URL to post to. |
| contentType | String | The MIME type to use in the HTTP "Content-type" header. [optional] |
| postData | String | The raw data to post via HTTP.  [optional] |
| connectTimeout | Integer | The timeout for connecting to the url. In milliseconds. Default is 10,000. [optional] |
| readTimeout | Integer | The read timeout for the get operation. In milliseconds. Default is 60,000. [optional] |
| username | String | If specified, the call will attempt to authenticate with basic HTTP authentication. [optional] |
| password | String | The password used for basic http authentication, if the username parameter is also present. [optional] |
| headerValues | Dictionary[String, Integer] | A dictionary of name/value pairs that will be set in the http header. [optional] |
| bypassCertValidation | Boolean | If the target address is an HTTPS address, and this parameter is True, the system will bypass all SSL certificate validation. This is not recommended, though is sometimes necessary for self-signed certificates. [optional] |
| throwOnError | Boolean | Set to false if you wish to get the error body rather than a Python exception if the POST request returns an error code (non-200 responsive). Default is True. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.net.httpPost(url, postParams)
```


---



---

# system.net.httpPut

**版本：** 8.1
**型別：** Scripting
**分類：** Net

## 詳述

This function is used inPython Scripting. Performs an HTTP PUT to the given URL. Encodes the given dictionary of parameters using "applications/x-www-form-urlencoded" format. Keep in mind thatJRE proxy settingswill influence how these functions conduct their network activities.

## 語法

```python
system.net.httpPut(url, [contentType], putData, [connectTimeout], [readTimeout], [username], [password], [headerValues], [bypassCertValidation])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| url | String | The URL to put to. |
| contentType | String | The MIME type used in the HTTP 'Content-type' header. [optional] |
| putData | String | The raw data to put via HTTP. |
| connectTimeout | Int | The timeout for connecting to the URL in milliseconds. Default is 10,000. [optional] |
| readTimeout | Int | The read timeout for the operation in milliseconds. Default is 60,000. [optional] |
| username | String | If specified, the call will attempt to authenticate with basic HTTP authentication. [optional] |
| password | String | The password used for basic HTTP authentication, if the username parameter is also present. [optional] |
| headerValues | Dictionary[String, String] | A dictionary of name/value pairs that will be set in the HTTP header. [optional] |
| bypassCertValidation | Boolean | If the target address in an HTTPS address, and this parameter is true, the system will bypass all SSL certificate validation. This is not recommended, though is sometimes necessary for self-signed certificates. [optional] |
| url | String | The URL to send the request to. |
| putParams | Dictionary[String, Integer] | A dictionary of name/value key pairs to use as the put data. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.net.httpPut(url, [contentType], putData, [connectTimeout], [readTimeout], [username], [password], [headerValues], [bypassCertValidation])
```

### Example 3

```python
contentType
```


---



---

# system.net.openURL

**版本：** 8.1
**型別：** Scripting
**分類：** Net

## 詳述

This function is used inPython Scripting. Opens the given URL or URI scheme outside of the currently running Client in whatever application the host operating system deems appropriate. For example, the URL: will open in the default web browser, whereas this one:

## 語法

```python
system.net.openURL(url [, useApplet])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| url | String | The URL to open in a web browser. |
| useApplet | Boolean | If set to true (1), and the client is running as an Applet, then the browser instance that launched the applet will be used to open the URL. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
"http://www.google.com"
```

### Example 2

```python
"http://www.google.com"
```

### Example 3

```python
"file://C:/Report.pdf"
```


---



---

# system.net.sendEmail

**版本：** 8.1
**型別：** Scripting
**分類：** Net

## 詳述

This function is used inPython Scripting. Sends an email through the given SMTP server. Note that this email is relayed first through the Gateway; the Client host machine doesn't need network access to the SMTP server. Note that you can use this function to send emails as text messages. Most phone service providers offer a domain that can be used to convert emails into text messages. For example:1234567890@phone.domain.com. Contact your cell carrier for details.

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| smtp | String | The address of an SMTP server to send the email through, likemail.example.com. A port can be specified, likemail.example.com:25. STARTTLS can also be forced, likemail.example.com:587:tls. |
| fromAddr | String | An email address to have the email come from. |
| subject | String | The subject line for the email. [optional] |
| body | String | The body text of the email. [optional] |
| html | Boolean | A flag indicating whether or not to send the email as an HTML email. Will auto-detect if omitted. [optional] |
| to | List[String] | A list of email addresses to send to.New in8.1.48This parameter becomes optional if either theccorbccparameter is specified. |
| attachmentNames | List[String] | A list of attachment names. Attachment names must have the correct extension for the file type or an error will occur. [optional] |
| attachmentData | List[Byte] | A list of attachment data, in binary format. [optional] |
| timeout | Integer | A timeout for the email, specified in milliseconds. Defaults to 300,000 milliseconds (5 minutes). [optional] |
| username | String | If specified, will be used to authenticate with the SMTP host. [optional] |
| password | String | If specified, will be used to authenticate with the SMTP host. [optional] |
| priority | String | Priority for the message, from "1" to "5", with "1" being highest priority. Defaults to "3" (normal) priority. [optional] |
| smtpProfile | String | If specified, the named SMTP profile defined in the Gateway will be used. If this keyword is present, thesmtp,username, andpasswordkeywords will be ignored. [optional] |
| cc | List[String] | A list of email addresses to carbon copy. Only available if ansmtpProfileis used. [optional] |
| bcc | List[String] | A list of email addresses to blind carbon copy. Only available if ansmtpProfileis used. [optional] |
| retries | Integer | The number of additional times to retry sending on failure. Defaults to 0. Only available if ansmtpProfileis used. [optional] |
| replyTo | List[String] | An optional list of addresses to have the recipients reply to. If omitted, this defaults to the from address. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
1234567890@phone.domain.com
```


---

