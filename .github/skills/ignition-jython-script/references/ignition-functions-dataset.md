# Ignition 8.1 - system.dataset 函數文檔


## 📑 目錄

---

1. [system.dataset.addColumn](#systemdatasetaddcolumn) - This function is used inPython Scripting. Takes adatasetand returns a new dataset with a new column added or inserted into it. If the columnIndex argument is omitted, the column will be appended to the end of the dataset. Datasets are immutable, which means they cannot be directly modified once created. Instead, this scripting function returns a new dataset with some modification applied, which must be assigned to a variable to be used. SeeAltering a Dataset.
2. [system.dataset.addRow](#systemdatasetaddrow) - This function is used inPython Scripting. Takes adatasetand returns a new dataset with a new row added or inserted into it. If the rowIndex argument is omitted, the row will be appended to the end of the dataset. Datasets are immutable, which means they cannot be directly modified once created. Instead, this scripting function returns a new dataset with some modification applied, which must be assigned to a variable to be used. SeeAltering a Dataset.
3. [system.dataset.addRows](#systemdatasetaddrows) - This function is used inPython Scripting. Takes adatasetand returns a new dataset with new rows added or inserted into it. If the rowIndex argument is omitted, the rows will be appended to the end of the dataset. Datasets are immutable, which means they cannot be directly modified once created. Instead, this scripting function returns a new dataset with some modification applied, which must be assigned to a variable to be used. SeeAltering a Dataset.
4. [system.dataset.appendDataset](#systemdatasetappenddataset) - This function is used inPython Scripting. Takes two different datasets and returns a newdatasetwith the second dataset appended to the first. Will throw an error if the number and types of columns do not match. This scripting function has noClient Permissionrestrictions.
5. [system.dataset.clearDataset](#systemdatasetcleardataset) - This function is used inPython Scripting. Takes adatasetand returns a new dataset with all of the same column names and types, but no rows. Datasets are immutable, which means they cannot be directly modified once created. Instead, this scripting function returns a new dataset with some modification applied, which must be assigned to a variable to be used. SeeAltering a Dataset.
6. [system.dataset.dataSetToHTML](#systemdatasetdatasettohtml) - This function is used inPython Scripting. Formats the contents of adatasetas an HTML page, returning the results as a string. Uses the<table>element to create a data table page. This scripting function has noClient Permissionrestrictions.
7. [system.dataset.deleteRow](#systemdatasetdeleterow) - This function is used inPython Scripting. Takes adatasetand returns a new dataset with the specified rowIndex removed. Datasets are immutable, which means they cannot be directly modified once created. Instead, this scripting function returns a new dataset with some modification applied, which must be assigned to a variable to be used. SeeAltering a Dataset.
8. [system.dataset.deleteRows](#systemdatasetdeleterows) - This function is used inPython Scripting. Takes adatasetand returns a new dataset with one or more rows removed. Datasets are immutable, which means they cannot be directly modified once created. Instead, this scripting function returns a new dataset with some modification applied, which must be assigned to a variable to be used. SeeAltering a Dataset.
9. [system.dataset.exportCSV](#systemdatasetexportcsv) - This function is used inPython Scripting. Exports the contents of adatasetas a CSV file, prompting the user to save the file to disk. To write silently to a file, you cannot use the dataset.export* functions. Instead, use thetoCSV()function. This scripting function has noClient Permissionrestrictions.
10. [system.dataset.exportExcel](#systemdatasetexportexcel) - This function is used inPython Scripting. Exports the contents of adatasetas an Excel spreadsheet, prompting the user to save the file to disk. Uses the same format as thesystem.dataset.toExcelfunction. To write silently to a file, you cannot use the dataset.export* functions. Instead, use the toExcel() function. This scripting function has noClient Permissionrestrictions.
11. [system.dataset.exportHTML](#systemdatasetexporthtml) - This function is used inPython Scripting. Exports the contents of adatasetto an HTML page. Prompts the user to save the file to disk. This scripting function has noClient Permissionrestrictions.
12. [system.dataset.filterColumns](#systemdatasetfiltercolumns) - This function is used inPython Scripting. Takes adatasetand returns a view of the dataset containing only the columns found within the given list of columns. Datasets are immutable, which means they cannot be directly modified once created. Instead, this scripting function returns a new dataset with some modification applied, which must be assigned to a variable to be used. SeeAltering a Dataset.
13. [system.dataset.formatDates](#systemdatasetformatdates) - This function is used inPython Scripting. Returns a newdatasetreplacing date typed columns with string typed columns. The new columns will match the formatting specified by the dateFormat parameter. This scripting function has noClient Permissionrestrictions.
14. [system.dataset.fromCSV](#systemdatasetfromcsv) - This function is used inPython Scripting. Converts adatasetstored in a CSV formatted string to a dataset that can be immediately assignable to a dataset property in your project.  Usually this is used in conjunction withsystem.file.readFileAsStringwhen reading in a CSV file that was exported usingsystem.dataset.toCSV.  The CSV string must be formatted in a specific way: The second line must list the names of the columns of the dataset separated by commas
15. [system.dataset.getColumnHeaders](#systemdatasetgetcolumnheaders) - This function is used inPython Scripting. Takes in adatasetand returns the headers as a Python list. This scripting function has noClient Permissionrestrictions.
16. [system.dataset.setValue](#systemdatasetsetvalue) - This function is used inPython Scripting. Takes adatasetand returns a new dataset with one value altered. Datasets are immutable, which means they cannot be directly modified once created. Instead, this scripting function returns a new dataset with some modification applied, which must be assigned to a variable to be used. SeeAltering a Dataset.
17. [system.dataset.sort](#systemdatasetsort) - This function is used inPython Scripting. Takes adatasetand returns a sorted version of the dataset. The sort order is determined by a single column. This works on numeric, as well as alphanumeric columns. When sorting alphanumerically, contiguous numbers are treated as a single number: you may recognize this as a "natural sort". Datasets are immutable, which means they cannot be directly modified once created. Instead, this scripting function returns a new dataset with some modification applied
18. [system.dataset.toCSV](#systemdatasettocsv) - This function is used inPython Scripting. Formats the contents of adatasetas CSV (comma separated values), returning the resulting CSV as a string. If the "forExport" flag is set, then the format will be appropriate for parsing using thesystem.dataset.fromCSVfunction. This scripting function has noClient Permissionrestrictions.
19. [system.dataset.toDataSet](#systemdatasettodataset) - This function is used inPython Scripting. This function is used to convert a PyDataset to a dataset. In addition it can also create new datasets from a raw Python list. When creating a new dataset, headers should have unique names. For more information on datasets and PyDatasets, see theDatasetspage. This scripting function has noClient Permissionrestrictions.
20. [system.dataset.toExcel](#systemdatasettoexcel) - This function is used inPython Scripting. Formats the contents of one or moredatasetsas an Excel spreadsheet, returning the results as a byte array. Each dataset specified will be added as a worksheet in the Excel workbook. This function replaces the deprecatedsystem.dataset.dataSetToExcelfunction.
21. [system.dataset.toPyDataSet](#systemdatasettopydataset) - This function is used inPython Scripting. This function converts from a normaldatasetto a PyDataset, which is a wrapper class which makes working with datasets more Python-esque. For more information on datasets and PyDatasets, see theDatasetspage. This scripting function has noClient Permissionrestrictions.
22. [system.dataset.updateRow](#systemdatasetupdaterow) - This function is used inPython Scripting. Takes adatasetand returns a new dataset with a one row altered. To alter the row, this function takes a Python dictionary to represent the changes to make to the specified row. The keys in the dictionary are used to find the columns to alter. Datasets are immutable, which means they cannot be directly modified once created. Instead, this scripting function returns a new dataset with some modification applied, which must be assigned to a variable to be us

---

# system.dataset.addColumn

**版本：** 8.1
**型別：** Scripting
**分類：** Dataset

## 詳述

This function is used inPython Scripting. Takes adatasetand returns a new dataset with a new column added or inserted into it. If the columnIndex argument is omitted, the column will be appended to the end of the dataset. Datasets are immutable, which means they cannot be directly modified once created. Instead, this scripting function returns a new dataset with some modification applied, which must be assigned to a variable to be used. SeeAltering a Dataset.

## 語法

```python
system.dataset.addColumn(dataset, [colIndex], col, colName, colType)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| dataset | Dataset | The starting dataset. Please be aware that this dataset will not actually be modified (datasets are immutable), but rather will be the starting point for creating a new dataset. |
| colIndex | Integer | The index (starting at 0) at which to insert the new column. Will throw an IndexError if less than zero or greater than the length of the dataset. If omitted, the new column will be appended to the end. [optional] |
| col | List[Any] | A Python sequence representing the data for the new column. Its length must equal the number of rows in the dataset. |
| colName | String | The name of the column. |
| colType | Type | The type of the of the column. The type can be a Python builtin type, such as str , int, float, or a Java class, such as java.util.Date. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dataset.addColumn(dataset, [colIndex], col, colName, colType)
```


---



---

# system.dataset.addRow

**版本：** 8.1
**型別：** Scripting
**分類：** Dataset

## 詳述

This function is used inPython Scripting. Takes adatasetand returns a new dataset with a new row added or inserted into it. If the rowIndex argument is omitted, the row will be appended to the end of the dataset. Datasets are immutable, which means they cannot be directly modified once created. Instead, this scripting function returns a new dataset with some modification applied, which must be assigned to a variable to be used. SeeAltering a Dataset.

## 語法

```python
system.dataset.addRow(dataset, [rowIndex], row)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| dataset | Dataset | The starting dataset. Please be aware that this dataset will not actually be modified (datasets are immutable), but rather will be the starting point for creating a new dataset. |
| rowIndex | Integer | The index (starting at 0) at which to insert the new row. Will throw an IndexError if less than zero or greater than the length of the dataset. If omitted, the new row will be appended to the end. [optional] |
| row | List[Any] | A Python list representing the data for the new row. Its length must equal the number of columns in the dataset. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dataset.addRow(dataset, [rowIndex], row)
```


---



---

# system.dataset.addRows

**版本：** 8.1
**型別：** Scripting
**分類：** Dataset

## 詳述

This function is used inPython Scripting. Takes adatasetand returns a new dataset with new rows added or inserted into it. If the rowIndex argument is omitted, the rows will be appended to the end of the dataset. Datasets are immutable, which means they cannot be directly modified once created. Instead, this scripting function returns a new dataset with some modification applied, which must be assigned to a variable to be used. SeeAltering a Dataset.

## 語法

```python
system.dataset.addRows(dataset, [rowIndex], rows)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| dataset | Dataset | The starting dataset. Please be aware that this dataset will not actually be modified (datasets are immutable), but rather will be the starting point for creating a new dataset. |
| rowIndex | Integer | The index (starting at 0) at which to insert the new row. Will throw an IndexError if less than zero or greater than the length of the dataset. If omitted, the new row will be appended to the end. [optional] |
| rows | List[Any] | A Python sequence of sequences representing the data for the new rows. The length of each sequence must equal the number of columns in the dataset. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dataset.addRows(dataset, [rowIndex], rows)
```


---



---

# system.dataset.appendDataset

**版本：** 8.1
**型別：** Scripting
**分類：** Dataset

## 詳述

This function is used inPython Scripting. Takes two different datasets and returns a newdatasetwith the second dataset appended to the first. Will throw an error if the number and types of columns do not match. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.dataset.appendDataset(dataset1, dataset2)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| dataset1 | Dataset | The dataset that will come first in the returned dataset. |
| dataset2 | Dataset | The second dataset that will be appended to the end in the returned dataset. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dataset.appendDataset(dataset1, dataset2)
```


---



---

# system.dataset.clearDataset

**版本：** 8.1
**型別：** Scripting
**分類：** Dataset

## 詳述

This function is used inPython Scripting. Takes adatasetand returns a new dataset with all of the same column names and types, but no rows. Datasets are immutable, which means they cannot be directly modified once created. Instead, this scripting function returns a new dataset with some modification applied, which must be assigned to a variable to be used. SeeAltering a Dataset.

## 語法

```python
system.dataset.clearDataset(dataset)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| dataset | Dataset | The starting dataset. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dataset.clearDataset(dataset)
```

### Example 3

```python
# This example pulls in the dataset from a Vision Table component, clears it, then writes the empty dataset back to the table.

data = event.source.parent.getComponent('Table').data
event.source.parent.getComponent('Table').data = system.dataset.clearDataset(data)
```


---



---

# system.dataset.dataSetToHTML

**版本：** 8.1
**型別：** Scripting
**分類：** Dataset

## 詳述

This function is used inPython Scripting. Formats the contents of adatasetas an HTML page, returning the results as a string. Uses the<table>element to create a data table page. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.dataset.dataSetToHTML(showHeaders, dataset, title)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| showHeaders | Boolean | If true, the HTML table will include a header row. |
| dataset | Dataset | The dataset to export. |
| title | String | The title for the HTML page. |

## 回傳值

**型別：** Object

## 範例

### Example 2

```python
system.dataset.dataSetToHTML(showHeaders, dataset, title)
```

### Example 3

```python
showHeaders
```


---



---

# system.dataset.deleteRow

**版本：** 8.1
**型別：** Scripting
**分類：** Dataset

## 詳述

This function is used inPython Scripting. Takes adatasetand returns a new dataset with the specified rowIndex removed. Datasets are immutable, which means they cannot be directly modified once created. Instead, this scripting function returns a new dataset with some modification applied, which must be assigned to a variable to be used. SeeAltering a Dataset.

## 語法

```python
system.dataset.deleteRow(dataset, rowIndex)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| dataset | Dataset | The starting dataset. Please be aware that this dataset will not actually be modified (datasets are immutable), but rather will be the starting point for creating a new dataset. |
| rowIndex | Integer | The index (starting at 0) of the row to delete. Will throw an IndexError if out of bounds. The maximum bounds is defined by subtracting one from the number of rows in the dataset. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dataset.deleteRow(dataset, rowIndex)
```


---



---

# system.dataset.deleteRows

**版本：** 8.1
**型別：** Scripting
**分類：** Dataset

## 詳述

This function is used inPython Scripting. Takes adatasetand returns a new dataset with one or more rows removed. Datasets are immutable, which means they cannot be directly modified once created. Instead, this scripting function returns a new dataset with some modification applied, which must be assigned to a variable to be used. SeeAltering a Dataset.

## 語法

```python
system.dataset.deleteRows(dataset, rowIndices)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| dataset | Dataset | The starting dataset. Please be aware that this dataset will not actually be modified (datasets are immutable), but rather will be the starting point for creating a new dataset. |
| rowIndices | List[Integer] | The indices (starting at 0) of the rows to delete. Will throw an IndexError if any element is less than zero or greater than the number of rows in the dataset - 1. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dataset.deleteRows(dataset, rowIndices)
```


---



---

# system.dataset.exportCSV

**版本：** 8.1
**型別：** Scripting
**分類：** Dataset

## 詳述

This function is used inPython Scripting. Exports the contents of adatasetas a CSV file, prompting the user to save the file to disk. To write silently to a file, you cannot use the dataset.export* functions. Instead, use thetoCSV()function. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.dataset.exportCSV(filename, showHeaders, dataset)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| filename | String | A suggested filename to save as. |
| showHeaders | Boolean | If true, the CSV file will include a header row. |
| dataset | Dataset | The dataset to export. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dataset.exportCSV(filename, showHeaders, dataset)
```

### Example 3

```python
showHeaders
```


---



---

# system.dataset.exportExcel

**版本：** 8.1
**型別：** Scripting
**分類：** Dataset

## 詳述

This function is used inPython Scripting. Exports the contents of adatasetas an Excel spreadsheet, prompting the user to save the file to disk. Uses the same format as thesystem.dataset.toExcelfunction. To write silently to a file, you cannot use the dataset.export* functions. Instead, use the toExcel() function. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.dataset.exportExcel(filename, showHeaders, dataset, [nullsEmpty])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| filename | String | A suggested filename to save as. |
| showHeaders | Boolean | If true, the spreadsheet will include a header row. |
| dataset | Dataset / List[Dataset] | Either a single dataset, or a list of datasets. When passing a list, each element represents a single sheet in the resulting workbook. |
| nullsEmpty | Boolean | If True, the spreadsheet will leave cells with NULL values empty, instead of allowing Excel to provide a default value like 0. Defaults to False. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dataset.exportExcel(filename, showHeaders, dataset, [nullsEmpty])
```

### Example 3

```python
showHeaders
```


---



---

# system.dataset.exportHTML

**版本：** 8.1
**型別：** Scripting
**分類：** Dataset

## 詳述

This function is used inPython Scripting. Exports the contents of adatasetto an HTML page. Prompts the user to save the file to disk. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.dataset.exportHTML(filename, showHeaders, dataset, title)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| filename | String | A suggested filename to save as. |
| showHeaders | Boolean | If true, the HTML table will include a header row. |
| dataset | Dataset / PyDataset | The dataset to export. |
| title | String | The title for the HTML page. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dataset.exportHTML(filename, showHeaders, dataset, title)
```

### Example 3

```python
showHeaders
```


---



---

# system.dataset.filterColumns

**版本：** 8.1
**型別：** Scripting
**分類：** Dataset

## 詳述

This function is used inPython Scripting. Takes adatasetand returns a view of the dataset containing only the columns found within the given list of columns. Datasets are immutable, which means they cannot be directly modified once created. Instead, this scripting function returns a new dataset with some modification applied, which must be assigned to a variable to be used. SeeAltering a Dataset.

## 語法

```python
system.dataset.filterColumns(dataset, columns)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| dataset | Dataset / PyDataset | The starting dataset. |
| columns | List[Integer] / List[String] | A list of columns to keep in the returned dataset. The columns may be in integer index form (starting at 0), or the name of the columns as strings. If a value passed to this parameter is not in a list, then an empty dataset will be returned. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dataset.filterColumns(dataset, columns)
```


---



---

# system.dataset.formatDates

**版本：** 8.1
**型別：** Scripting
**分類：** Dataset

## 詳述

This function is used inPython Scripting. Returns a newdatasetreplacing date typed columns with string typed columns. The new columns will match the formatting specified by the dateFormat parameter. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.dataset.formatDates( dataset, dateFormat, [locale] )
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| dataset | Dataset / PyDataset | The starting dataset to format. |
| dateFormat | String | A valid Java DateFormat string, representing how the date should be formatted. For example: "yyyy-MM-dd HH:mm:ss". Refer toData Type Formatting Referencefor more information on the valid characters. |
| locale | Locale | The Locale to use for formatting. The Locale parameter accepts any valid Java Locale object, which can be foundhere. The Java Locale class must be imported, and the Locale must be defined in all caps. See the second example below for an idea of how that works. If no locale is provided, the system’s locale will be used. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dataset.formatDates( dataset, dateFormat, [locale] )
```


---



---

# system.dataset.fromCSV

**版本：** 8.1
**型別：** Scripting
**分類：** Dataset

## 詳述

This function is used inPython Scripting. Converts adatasetstored in a CSV formatted string to a dataset that can be immediately assignable to a dataset property in your project.  Usually this is used in conjunction withsystem.file.readFileAsStringwhen reading in a CSV file that was exported usingsystem.dataset.toCSV.  The CSV string must be formatted in a specific way: The second line must list the names of the columns of the dataset separated by commas

## 語法

```python
system.dataset.fromCSV( csv )
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| csv | String | A string holding a CSV dataset in the format outlined above. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
#NAMES
Col 1,Col 2,Col 3
#TYPES
I,str,D
#ROWS,6
44,Test Row 2,1.8713151369491254
86,Test Row 3,97.4913421614675
0,Test Row 8,20.39722542161364
78,Test Row 9,34.57127071614745
20,Test Row 10,76.41114659745085
21,Test Row 13,13.880548366871926
The first line must be #NAMES
```

### Example 2

```python
#NAMES
Col 1,Col 2,Col 3
#TYPES
I,str,D
#ROWS,6
44,Test Row 2,1.8713151369491254
86,Test Row 3,97.4913421614675
0,Test Row 8,20.39722542161364
78,Test Row 9,34.57127071614745
20,Test Row 10,76.41114659745085
21,Test Row 13,13.880548366871926
The first line must be #NAMES
```


---



---

# system.dataset.getColumnHeaders

**版本：** 8.1
**型別：** Scripting
**分類：** Dataset

## 詳述

This function is used inPython Scripting. Takes in adatasetand returns the headers as a Python list. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.dataset.getColumnHeaders(dataset)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| dataset | Dataset | The input dataset. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dataset.getColumnHeaders(dataset)
```

### Example 3

```python
# This example fetches the dataset from a Vision table, and prints the table headers as a list.
# Fetch data from table component.
data = event.source.parent.getComponent('Table').data
# Print dataset headers.
print system.dataset.getColumnHeaders(data)
```


---



---

# system.dataset.setValue

**版本：** 8.1
**型別：** Scripting
**分類：** Dataset

## 詳述

This function is used inPython Scripting. Takes adatasetand returns a new dataset with one value altered. Datasets are immutable, which means they cannot be directly modified once created. Instead, this scripting function returns a new dataset with some modification applied, which must be assigned to a variable to be used. SeeAltering a Dataset.

## 語法

```python
system.dataset.setValue(dataset, rowIndex, columnName, value)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| dataset | Dataset | The starting dataset. Will not be modified (datasets are immutable), but acts as the basis for the returned dataset. |
| rowIndex | Integer | The index of the row to set the value at (starting at 0). |
| columnName | String | The name of the column to set the value at. Case insensitive. |
| value | Any | The new value for the specified row/column. |
| dataset | Dataset | The starting dataset. Will not be modified (datasets are immutable), but acts as the basis for the returned dataset. |
| rowIndex | Integer | The index of the row to set the value at (starting at 0). |
| columnIndex | Integer | The index of the column to set the value at (starting at 0) |
| value | Any | The new value for the specified row/column. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dataset.setValue(dataset, rowIndex, columnName, value)
```


---



---

# system.dataset.sort

**版本：** 8.1
**型別：** Scripting
**分類：** Dataset

## 詳述

This function is used inPython Scripting. Takes adatasetand returns a sorted version of the dataset. The sort order is determined by a single column. This works on numeric, as well as alphanumeric columns. When sorting alphanumerically, contiguous numbers are treated as a single number: you may recognize this as a "natural sort". Datasets are immutable, which means they cannot be directly modified once created. Instead, this scripting function returns a new dataset with some modification applied

## 語法

```python
system.dataset.sort(dataset, keyColumn [, ascending, naturalOrdering])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| dataset | Dataset | The dataset to sort. |
| keyColumn | Integer / String | The index of the column to sort on. |
| ascending | Boolean | True for ascending order, False for descending order. If omitted, ascending order will be used. [optional] |
| naturalOrdering | Boolean | True for natural ordering, False for alphabetical ordering. Ignored if the sort column is a directly sortable data type. If omitted, defaults to True (natural ordering). [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dataset.sort(dataset, keyColumn [, ascending, naturalOrdering])
```


---



---

# system.dataset.toCSV

**版本：** 8.1
**型別：** Scripting
**分類：** Dataset

## 詳述

This function is used inPython Scripting. Formats the contents of adatasetas CSV (comma separated values), returning the resulting CSV as a string. If the "forExport" flag is set, then the format will be appropriate for parsing using thesystem.dataset.fromCSVfunction. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.dataset.toCSV(dataset, showHeaders, forExport, localized)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| dataset | Dataset | The dataset to export to CSV. |
| showHeaders | Boolean | If set to true, a header row will be present in the CSV. Default is true. |
| forExport | Boolean | If set to true, extra header information will be present in the CSV data which is necessary for the CSV to be compatible with the fromCSV method. Overrides showHeaders. Default is false. |
| localized | Boolean | If set to true, the string representations of the values in the CSV data will be localized. Default is false. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dataset.toCSV(dataset, showHeaders, forExport, localized)
```

### Example 3

```python
showHeaders
```


---



---

# system.dataset.toDataSet

**版本：** 8.1
**型別：** Scripting
**分類：** Dataset

## 詳述

This function is used inPython Scripting. This function is used to convert a PyDataset to a dataset. In addition it can also create new datasets from a raw Python list. When creating a new dataset, headers should have unique names. For more information on datasets and PyDatasets, see theDatasetspage. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.dataset.toDataSet(dataset)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| dataset | PyDataset | A PyDataset object to convert. |
| headers | List[String] | The column names for the dataset to create. |
| data | List[Any] | A list of rows for the new dataset. Each row must have the same length as the headers list, and each value in a column must be the same type. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dataset.toDataSet(dataset)
```

### Example 3

```python
system.dataset.toDataSet(headers, data)
```


---



---

# system.dataset.toExcel

**版本：** 8.1
**型別：** Scripting
**分類：** Dataset

## 詳述

This function is used inPython Scripting. Formats the contents of one or moredatasetsas an Excel spreadsheet, returning the results as a byte array. Each dataset specified will be added as a worksheet in the Excel workbook. This function replaces the deprecatedsystem.dataset.dataSetToExcelfunction.

## 語法

```python
system.dataset.toExcel(showHeaders, dataset, [nullsEmpty], [sheetNames])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| showHeaders | Boolean | If True, the spreadsheet will include a header row. If False, the header row will be omitted. |
| dataset | List[Dataset] | A sequence of one or more datasets, one for each sheet in the resulting workbook. |
| nullsEmpty | Boolean | If True, the spreadsheet will leave cells with NULL values empty, instead of allowing Excel to provide a default value like 0. Defaults to False. [optional] |
| sheetNames | List[String] | Expects a list of strings, where each string is a name for one of the datasets. When used, there must be an equal number of string names in sheetName as there are datasets in the dataset parameter. Names provided in this parameter may be sanitized into acceptable Excel sheet names. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dataset.toExcel(showHeaders, dataset, [nullsEmpty], [sheetNames])
```

### Example 2

```python
showHeaders
```


---



---

# system.dataset.toPyDataSet

**版本：** 8.1
**型別：** Scripting
**分類：** Dataset

## 詳述

This function is used inPython Scripting. This function converts from a normaldatasetto a PyDataset, which is a wrapper class which makes working with datasets more Python-esque. For more information on datasets and PyDatasets, see theDatasetspage. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.dataset.toPyDataSet(dataset)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| dataset | Dataset | A dataset object to convert into a PyDataset. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dataset.toPyDataSet(dataset)
```

### Example 3

```python
# This example script would be added to a button that is in the same container as the table you are working with.
# It grabs the data of the Table component, and adds up the values in the first column, displaying the result to the user.

# Get a Table component's data.
table = event.source.parent.getComponent("Table")
data = system.dataset.toPyDataSet(table.data)

# Loop through the data, summing the Value column.
value = 0.0
for row in data:
   value += row[0]

# Show the user the sum of the Value column.
system.gui.messageBox("The value is: %f" % value)
```


---



---

# system.dataset.updateRow

**版本：** 8.1
**型別：** Scripting
**分類：** Dataset

## 詳述

This function is used inPython Scripting. Takes adatasetand returns a new dataset with a one row altered. To alter the row, this function takes a Python dictionary to represent the changes to make to the specified row. The keys in the dictionary are used to find the columns to alter. Datasets are immutable, which means they cannot be directly modified once created. Instead, this scripting function returns a new dataset with some modification applied, which must be assigned to a variable to be us

## 語法

```python
system.dataset.updateRow(dataset, rowIndex, changes)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| dataset | Dataset | The starting dataset. Will not be modified (datasets are immutable), but acts as the basis for the returned dataset. |
| rowIndex | Integer | The index of the row to update (starting at 0). |
| changes | Dictionary[String, Any] | A dictionary of changes to make. The keys in the dictionary should match column names in the dataset, and their values will be used to update the row. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dataset.updateRow(dataset, rowIndex, changes)
```


---

