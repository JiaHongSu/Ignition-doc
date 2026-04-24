# Ignition 8.1 - system.file 函數文檔


## 📑 目錄

---

1. [system.file.fileExists](#systemfilefileexists) - This function is used inPython Scripting. Checks to see if a file or folder at a given path exists. This function is scoped for Perspective Sessions, but since all scripts in Perspective run on the Gateway, the file must be located on the Gateway's file system.
2. [system.file.getTempFile](#systemfilegettempfile) - This function is used inPython Scripting. Creates a new temp file on the host machine with a certain extension, returning the path to the file. The file is marked to be removed when the Java VM exits. This function is scoped for Perspective Sessions, but since all scripts in Perspective run on the Gateway, the file must be located on the Gateway's file system.
3. [system.file.openFile](#systemfileopenfile) - This function is used inPython Scripting. Shows an "Open File" dialog box, prompting the user to choose a file to open. Returns the path to the file that the user chose, or None if the user canceled the dialog box. An extension can optionally be passed in that sets the filetype filter to that extension. This scripting function has noClient Permissionrestrictions.
4. [system.file.openFiles](#systemfileopenfiles) - This function is used inPython Scripting. Shows an "Open File" dialog box, prompting the user to choose a file or files to open. Returns the paths to the files that the user chooses, or None if the user canceled the dialog box. An extension can optionally be passed in that sets the filetype filter to that extension. This scripting function has noClient Permissionrestrictions.
5. [system.file.readFileAsBytes](#systemfilereadfileasbytes) - This function is used inPython Scripting. Opens the file found at path filename, and reads the entire file. Returns the file as an array of bytes. Commonly this array of bytes is uploaded to a database table with a column of type BLOB (Binary Large OBject). This upload would be done through an INSERT or UPDATE SQL statement run through the system.db.runPrepUpdate function. You could also write the bytes to another file using the system.file.writeFile function, or send the bytes as an email attac
6. [system.file.readFileAsString](#systemfilereadfileasstring) - This function is used inPython Scripting. Opens the file found at path filename, and reads the entire file. Returns the file as a string. Common things to do with this string would be to load it into the text property of a component, upload it to a database table, or save it to another file using system.file.writeFile function. This function is scoped for Perspective Sessions, but since all scripts in Perspective run on the Gateway, the file must be located on the Gateway's file system.
7. [system.file.saveFile](#systemfilesavefile) - This function is used inPython Scripting. Prompts the user to save a new file named filename. The optional extension and typeDesc arguments will be used for a file type filter, if any. If the user accepts the save, the path to that file will be returned. If the user cancels the save, None will be returned. This scripting function has noClient Permissionrestrictions.
8. [system.file.writeFile](#systemfilewritefile) - This function is used inPython Scripting. Writes the given data to the file at file path filename. If the file exists, the append argument determines whether or not it is overwritten (the default) or appended to. The data argument can be either a string or an array of bytes (commonly retrieved from a BLOB in a database or read from another file using system.file.readFileAsBytes). This function is scoped for Perspective Sessions, but since all scripts in Perspective run on the Gateway, the file m

---

# system.file.fileExists

**版本：** 8.1
**型別：** Scripting
**分類：** File

## 詳述

This function is used inPython Scripting. Checks to see if a file or folder at a given path exists. This function is scoped for Perspective Sessions, but since all scripts in Perspective run on the Gateway, the file must be located on the Gateway's file system.

## 語法

```python
system.file.fileExists(filepath)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| filepath | String | The path of the file or folder to check. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.file.fileExists(filepath)
```

### Example 3

```python
# This basic example shows how the fileExists function is used in its simplest form:
if system.file.fileExists("C:\\temp_file.txt"):
   system.gui.messageBox("Yes, the file exists")
else:
   system.gui.messageBox("No, it doesn't exist")
```


---



---

# system.file.getTempFile

**版本：** 8.1
**型別：** Scripting
**分類：** File

## 詳述

This function is used inPython Scripting. Creates a new temp file on the host machine with a certain extension, returning the path to the file. The file is marked to be removed when the Java VM exits. This function is scoped for Perspective Sessions, but since all scripts in Perspective run on the Gateway, the file must be located on the Gateway's file system.

## 語法

```python
system.file.getTempFile(extension)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| extension | String | An extension, like ".txt", to append to the end of the temporary file. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.file.getTempFile(extension)
```

### Example 3

```python
# This code writes some data to a temporary file, and then opens that file.
# Assume that the data variable holds the contents of an Excel (xls) file.

filename = system.file.getTempFile("xls")
system.file.writeFile(filename, data)
system.net.openURL("file://" + filename)
```


---



---

# system.file.openFile

**版本：** 8.1
**型別：** Scripting
**分類：** File

## 詳述

This function is used inPython Scripting. Shows an "Open File" dialog box, prompting the user to choose a file to open. Returns the path to the file that the user chose, or None if the user canceled the dialog box. An extension can optionally be passed in that sets the filetype filter to that extension. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.file.openFile([extension], [defaultLocation])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| extension | String | A file extension, such as "pdf", to try to open. [optional] |
| defaultLocation | String | A folder location, such as "C:\MyFiles", to use as the default folder to store in. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.file.openFile([extension], [defaultLocation])
```

### Example 3

```python
defaultLocation
```


---



---

# system.file.openFiles

**版本：** 8.1
**型別：** Scripting
**分類：** File

## 詳述

This function is used inPython Scripting. Shows an "Open File" dialog box, prompting the user to choose a file or files to open. Returns the paths to the files that the user chooses, or None if the user canceled the dialog box. An extension can optionally be passed in that sets the filetype filter to that extension. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.file.openFiles([extension], [defaultLocation])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| extension | String | A file extension, such as "pdf", to try to open. [optional] |
| defaultLocation | String | A folder location, such as "C:\MyFiles", to use as the default folder to store in. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.file.openFiles([extension], [defaultLocation])
```

### Example 3

```python
defaultLocation
```


---



---

# system.file.readFileAsBytes

**版本：** 8.1
**型別：** Scripting
**分類：** File

## 詳述

This function is used inPython Scripting. Opens the file found at path filename, and reads the entire file. Returns the file as an array of bytes. Commonly this array of bytes is uploaded to a database table with a column of type BLOB (Binary Large OBject). This upload would be done through an INSERT or UPDATE SQL statement run through the system.db.runPrepUpdate function. You could also write the bytes to another file using the system.file.writeFile function, or send the bytes as an email attac

## 語法

```python
system.file.readFileAsBytes(filepath)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| filepath | String | The path of the file to read. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.file.readFileAsBytes(filepath)
```

### Example 3

```python
# This code would prompt the user to choose a file. If the user chooses a file, it would then read that file and upload it to a database table called Files into a BLOB column called file_data.

path = system.file.openFile()
if path != None:
   bytes = system.file.readFileAsBytes(path)
   system.db.runPrepUpdate("INSERT INTO Files (file_data) VALUES (?)", [bytes])
```


---



---

# system.file.readFileAsString

**版本：** 8.1
**型別：** Scripting
**分類：** File

## 詳述

This function is used inPython Scripting. Opens the file found at path filename, and reads the entire file. Returns the file as a string. Common things to do with this string would be to load it into the text property of a component, upload it to a database table, or save it to another file using system.file.writeFile function. This function is scoped for Perspective Sessions, but since all scripts in Perspective run on the Gateway, the file must be located on the Gateway's file system.

## 語法

```python
system.file.readFileAsString(filepath, [encoding])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| filepath | String | The path of the file to read. |
| encoding | String | The character encoding of the file to be read. Will throw an exception if the string does not represent a supported encoding. Common encodings are "UTF-8", "ISO-8859-1" and "US-ASCII". Default is your system's default. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.file.readFileAsString(filepath, [encoding])
```


---



---

# system.file.saveFile

**版本：** 8.1
**型別：** Scripting
**分類：** File

## 詳述

This function is used inPython Scripting. Prompts the user to save a new file named filename. The optional extension and typeDesc arguments will be used for a file type filter, if any. If the user accepts the save, the path to that file will be returned. If the user cancels the save, None will be returned. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.file.saveFile(filename)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| filename | String | A file name to suggest to the user. |
| filename | String | A file name to suggest to the user. |
| extension | String | The appropriate file extension, like "jpeg", for the file. [optional] |
| typeDesc | String | A description of the extension, like "JPEG Image". [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.file.saveFile(filename)
```

### Example 3

```python
system.file.saveFile(filename, [extension], [typeDesc])
```


---



---

# system.file.writeFile

**版本：** 8.1
**型別：** Scripting
**分類：** File

## 詳述

This function is used inPython Scripting. Writes the given data to the file at file path filename. If the file exists, the append argument determines whether or not it is overwritten (the default) or appended to. The data argument can be either a string or an array of bytes (commonly retrieved from a BLOB in a database or read from another file using system.file.readFileAsBytes). This function is scoped for Perspective Sessions, but since all scripts in Perspective run on the Gateway, the file m

## 語法

```python
system.file.writeFile(filepath, charData, [append], [encoding])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| filepath | String | The path of the file to write to. |
| charData | String | The character content to write to the file. |
| append | Boolean | If true, the file will be appended to if it already exists. If false, the file will be overwritten if it exists. The default is false. [optional] |
| encoding | String | The character encoding of the file to write. Will throw an exception if the string does not represent a supported encoding. Common encodings are "UTF-8", "ISO-8859-1" and "US-ASCII". Default is "UTF-8". [optional] |
| filepath | String | The path of the file to write to. |
| data | Byte[] | The binary content to write to the file. |
| append | Boolean | If true, the file will be appended to if it already exists. If false, the file will be overwritten if it exists. The default is false. [optional] |
| encoding | String | The character encoding of the file to write. Will throw an exception if the string does not represent a supported encoding. Common encodings are "UTF-8", "ISO-8859-1" and "US-ASCII". Default is "UTF-8". [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.file.writeFile(filepath, charData, [append], [encoding])
```


---

