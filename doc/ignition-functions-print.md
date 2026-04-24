# Ignition 8.1 - system.print 函數文檔


## 📑 目錄

---

1. [system.print.createImage](#systemprintcreateimage) - This function is used inPython Scripting. Takes a snapshot of a component and creates a Java BufferedImage out of it. You can usejavax.imageio.ImageIOto turn this into bytes that can be saved to a file or a BLOB field in a database. This scripting function has noClient Permissionrestrictions.
2. [system.print.createPrintJob](#systemprintcreateprintjob) - This function is used inPython Scripting. Provides a general printing facility for printing the contents of a window or component to a printer. The general workflow for this function is that you create the print job, set the options you'd like on it, and then call print()  on the job. For printing reports or tables, use those components' dedicated print() functions. The PrintJob object that this function returns has the following properties:
3. [system.print.getDefaultPrinterName](#systemprintgetdefaultprintername) - This function is used inPython Scripting. Obtains the local default printer.
4. [system.print.getPrinterNames](#systemprintgetprinternames) - This function is used inPython Scripting. Lists the available local printers.
5. [system.print.printToImage](#systemprintprinttoimage) - This function is used inPython Scripting. This function prints the given component (such as a graph, container, entire window, etc) to an image file, and saves the file where ever the operating system deems appropriate. A filename and path may be provided to determine the name and location of the saved file. While not required, it is highly recommended to pass in a filename and path. The script may fail if the function attempts to save to a directory that the client does not have access rights t

---

# system.print.createImage

**版本：** 8.1
**型別：** Scripting
**分類：** Print

## 詳述

This function is used inPython Scripting. Takes a snapshot of a component and creates a Java BufferedImage out of it. You can usejavax.imageio.ImageIOto turn this into bytes that can be saved to a file or a BLOB field in a database. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.print.createImage(component)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| component | Component | The component to render. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
javax.imageio.ImageIO
```

### Example 2

```python
system.print.createImage(component)
```


---



---

# system.print.createPrintJob

**版本：** 8.1
**型別：** Scripting
**分類：** Print

## 詳述

This function is used inPython Scripting. Provides a general printing facility for printing the contents of a window or component to a printer. The general workflow for this function is that you create the print job, set the options you'd like on it, and then call print()  on the job. For printing reports or tables, use those components' dedicated print() functions. The PrintJob object that this function returns has the following properties:

## 語法

```python
system.print.createPrintJob(component)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| component | Component | The component that you'd like to print. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.print.createPrintJob(component)
```

### Example 3

```python
# Put this code on a button to print out an image of the container the button is in.
# A print dialog box will be displayed, allowing the user to specify various aspects of the print job.
job = system.print.createPrintJob(event.source.parent)
job.print()
```


---



---

# system.print.getDefaultPrinterName

**版本：** 8.1
**型別：** Scripting
**分類：** Print

## 詳述

This function is used inPython Scripting. Obtains the local default printer.

## 語法

```python
system.print.getDefaultPrinterName()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.print.getDefaultPrinterName()
```

### Example 2

```python
# This code will return the name of the local default printer.
system.print.getDefaultPrinterName()
```

### Example 3

```python
# This code will return the name of the local default printer.
system.print.getDefaultPrinterName()
```


---



---

# system.print.getPrinterNames

**版本：** 8.1
**型別：** Scripting
**分類：** Print

## 詳述

This function is used inPython Scripting. Lists the available local printers.

## 語法

```python
system.print.getPrinterNames()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.print.getPrinterNames()
```

### Example 2

```python
# This code will return a list of names of the machine's local printers.
system.print.getPrinterNames()
```

### Example 3

```python
# This code will return a list of names of the machine's local printers.
system.print.getPrinterNames()
```


---



---

# system.print.printToImage

**版本：** 8.1
**型別：** Scripting
**分類：** Print

## 詳述

This function is used inPython Scripting. This function prints the given component (such as a graph, container, entire window, etc) to an image file, and saves the file where ever the operating system deems appropriate. A filename and path may be provided to determine the name and location of the saved file. While not required, it is highly recommended to pass in a filename and path. The script may fail if the function attempts to save to a directory that the client does not have access rights t

## 語法

```python
system.print.printToImage(component [, filename])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| component | Component | The component to render. |
| filename | String | A filename to save the image as. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.print.printToImage(component [, filename])
```


---

