# Ignition 8.1 - system.tag 函數文檔


## 📑 目錄

---

1. [system.tag.browse](#systemtagbrowse) - This function is used inPython Scripting. Returns a list ofnodesfound at the specified path. The list objects are returned as dictionaries with some basic information about each node. This scripting function has noClient Permissionrestrictions.
2. [system.tag.browseHistoricalTags](#systemtagbrowsehistoricaltags) - This function is used inPython Scripting. Will browse for any historical tags at the provided historical path. It will only browse for tags at the path, and will not go down through any children. Will return with a BrowseResults object, which can be accessed using the methods below: The result set returned from .getResults() is a list of Results objects. This list can be iterated through with a standard for loop, and each object in the list can be accessed with the following methods:
3. [system.tag.configure](#systemtagconfigure) - This function is used inPython Scripting. Creates tags from a given list of Python dictionaries or from a JSON source string. Can be used to overwrite a current tag's configuration. When utilizing this function, the tag definitions must specify the names of properties with their scripting/JSON name. A reference of these properties can be found on theTag PropertiesandTag Alarm Propertiespages.
4. [system.tag.copy](#systemtagcopy) - This function is used inPython Scripting. Copies tags from one folder to another. Multiple Tag and folder paths may be passed to a single call of this function. The new destination can be a separate tag provider. When copying UDTs to a different provider, the destination provider must have a matching UDT definition. The function copies Tags sequentially, so definitions can be placed earlier in the list, with instances following after:
5. [system.tag.deleteAnnotations](#systemtagdeleteannotations) - This function is used inPython Scripting. Removes stored annotations from the sqlth_annotations table.  Requires the full Tag path (including history provider) for each annotation, as well as each annotation's storage ID.
6. [system.tag.deleteTags](#systemtagdeletetags) - This function is used inPython Scripting. Deletes multiple tags or tag folders. When deleting a tag folder, all tags under the folder are also deleted. Permission Type: Tag Editing
7. [system.tag.exists](#systemtagexists) - This function is used inPython Scripting. Checks whether or not a tag with a given path exists. This scripting function has noClient Permissionrestrictions.
8. [system.tag.exportTags](#systemtagexporttags) - This function is used inPython Scripting. Exports tags to a file on a local file system. The term "local file system" refers to the scope in which the script was running; for example, running this script in a Gateway Timer script will export the file to the Gateway file system.
9. [system.tag.getConfiguration](#systemtaggetconfiguration) - This function is used inPython Scripting. Retrieves tags from the Gateway as Python dictionaries. These can be edited and then saved back usingsystem.tag.configure. The configurations returned by this function can only contain properties that arenotusing their default values. Thus, if a property on a tag has not been modified from its default value, then it willnotbe included in the returned list.
10. [system.tag.importTags](#systemtagimporttags) - This function is used inPython Scripting. Imports a JSON tag file at the provided path. Also supports XML and CSV Tag file exports from legacy systems. Permission Type: Tag Editing
11. [system.tag.isOverlaysEnabled](#systemtagisoverlaysenabled) - This function is used inPython Scripting. Returns whether or not the current client's quality overlay system is currently enabled. This scripting function has noClient Permissionrestrictions.
12. [system.tag.move](#systemtagmove) - This function is used inPython Scripting. Moves tags or folders to a new destination. The new destination can be a separate tag provider. If interested in copying the tags to a new destination, instead of moving them, please see thesystem.tag.copypage. When moving UDTs to a different provider, the destination provider must have a matching UDT definition. This function moves folders/tags sequentially, so definitions can be placed earlier in the list, with instances following after.
13. [system.tag.query](#systemtagquery) - This function is used inPython Scripting. Queries a Tag Provider to produce a list of tags that meet the specified criteria. Provides the same functionality as theTag Report Tool.
14. [system.tag.queryAnnotations](#systemtagqueryannotations) - This function is used inPython Scripting. Queries annotations stored in the Tag History system for a set of paths for a given time range.
15. [system.tag.queryTagCalculations](#systemtagquerytagcalculations) - This function is used inPython Scripting. Queries various calculations (aggregations) for a set of tags over a specified range. Returns a dataset with a row per tag, and a column per calculation. This is useful when you wish to aggregate tag history collected over a period of time into a single value per aggregate. If you want multiple values aggregated to a single time slice (i.e., hourly aggregates for the same tag over an 8 hour period) consider usingsystem.tag.queryTagHistory.
16. [system.tag.queryTagDensity](#systemtagquerytagdensity) - This function is used inPython Scripting. Queries the Tag history system for information about the density of data. In other words, how much data is available for a given time span. This function is called with a list of Tag paths, and a start and end date. The result set is a two column dataset specifying the timestamp, and a relative weight. Each row is valid from the given time until the next row. Tags are assigned a 1 or a 0 if they are present or not. All values are then multiplied together
17. [system.tag.queryTagHistory](#systemtagquerytaghistory) - This function is used inPython Scripting. Issues a query to the Tag Historian. Querying tag history involves specifying the tags and the date range, as well as a few optional parameters. The Tag Historian will find the relevant history and then interpolate and aggregate it together into a coherent, tabular result set. This function takes a list of strings, where each string is a tag path, likeTanks/Tank5or[OracleProvider]Sump/Out2. This function also supports historical tag paths, seeTag Pathsfo
18. [system.tag.readAsync](#systemtagreadasync) - This function is used inPython Scripting. Asynchronously reads the value of the tags at the given paths. Meaning, execution of the calling script will continue without waiting for this function to finish. This is useful in cases where the rest of the script should continue without waiting for the results from system.tag.readAsync. Instead of returning the tag read results to the calling script, the results are processed by a Python callback function.
19. [system.tag.readBlocking](#systemtagreadblocking) - This function is used inPython Scripting. Reads the value of the tags at the given paths. Will "block" until the read operation is complete or times out. Meaning, execution of the calling script will pause until this function finishes. This is useful in cases where the tag read must complete before further lines in the same script should execute. This scripting function has noClient Permissionrestrictions.
20. [system.tag.rename](#systemtagrename) - This function is used inPython Scripting. Renames a single tag or folder. Permission Type: Tag Editing
21. [system.tag.requestGroupExecution](#systemtagrequestgroupexecution) - This function is used inPython Scripting. Sends a request to the specified tag group to execute now. This scripting function has noClient Permissionrestrictions.
22. [system.tag.setOverlaysEnabled](#systemtagsetoverlaysenabled) - This function is used inPython Scripting. Enables or disables the component quality overlay system. This scripting function has noClient Permissionrestrictions.
23. [system.tag.storeAnnotations](#systemtagstoreannotations) - This function is used inPython Scripting. Stores annotations into the tag history system. Annotations are stored by the underlying historian implementations, so different providers may store in different ways, and some providers may not support annotation storage. All parameters are 1-to-1, so all provided lists should be of the same length. If a particular annotation doesn't need a parameter, that element can be None in the list.
24. [system.tag.storeTagHistory](#systemtagstoretaghistory) - This function was originally deprecated in 8.0.0. It was reintroduced in version 8.1.8. This function is used inPython Scripting. Inserts data into the tag history system, allowing Tag history to be recorded via scripting.
25. [system.tag.writeAsync](#systemtagwriteasync) - This function is used inPython Scripting. Asynchronously writes values to tags at specified paths. The script will not wait for the write operation to complete before moving on, but you can provide a callback function to run further code after the write has finished. For a blocking tag write operation, seesystem.tag.writeBlocking.
26. [system.tag.writeBlocking](#systemtagwriteblocking) - This function is used inPython Scripting. Writes values to tags at the given paths. This function will "block" until the write operation is complete or times out. Meaning, execution of the calling script will pause until this function finishes. This is useful in cases where the tag write must complete before further lines in the same script should execute. Permission Type: Tag Editing

---

# system.tag.browse

**版本：** 8.1
**型別：** Scripting
**分類：** Tag

## 詳述

This function is used inPython Scripting. Returns a list ofnodesfound at the specified path. The list objects are returned as dictionaries with some basic information about each node. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.tag.browse(path, filter)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| path | String | The path that will be browsed, typically to a folder or UDT instance. |
| filter | Dictionary[String, Any] | A dictionary of browse filter keys. Keys are listed below. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.tag.browse(path, filter)
```


---



---

# system.tag.browseHistoricalTags

**版本：** 8.1
**型別：** Scripting
**分類：** Tag

## 詳述

This function is used inPython Scripting. Will browse for any historical tags at the provided historical path. It will only browse for tags at the path, and will not go down through any children. Will return with a BrowseResults object, which can be accessed using the methods below: The result set returned from .getResults() is a list of Results objects. This list can be iterated through with a standard for loop, and each object in the list can be accessed with the following methods:

## 語法

```python
system.tag.browseHistoricalTags(path, [nameFilters], [maxSize], [continuationPoint])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| path | String | The Historical Tag Path to browse. See the Tag Export page for adescription of how to construct a historical Tag. |
| nameFilters | List[String] | A list of name filters to be applied to the result set. [optional] |
| maxSize | Integer | The maximum size of the result set. [optional] |
| continuationPoint | Any | Sets the continuation point in order to continue a browse that was previously started and then limited. Use getContinuationPoint() on the Results object (seeReturnsbelow) to get the continuation point. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.tag.browseHistoricalTags(path, [nameFilters], [maxSize], [continuationPoint])
```

### Example 3

```python
nameFilters
```


---



---

# system.tag.configure

**版本：** 8.1
**型別：** Scripting
**分類：** Tag

## 詳述

This function is used inPython Scripting. Creates tags from a given list of Python dictionaries or from a JSON source string. Can be used to overwrite a current tag's configuration. When utilizing this function, the tag definitions must specify the names of properties with their scripting/JSON name. A reference of these properties can be found on theTag PropertiesandTag Alarm Propertiespages.

## 語法

```python
system.tag.configure(basePath, tags, [collisionPolicy])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| basePath | String | The starting point where the new tags will be created. When making changes to existing tags with this function, you want to set the path to the parent folder of the existing tag(s), not the tag(s) themselves. |
| tags | Any | A list of tag definitions, where each tag definition is a Python dictionary. Alternatively, a JSON source string may be passed to this parameter. When editing existing tags, it is generally easier to retrieve the tag configurations withsystem.tag.getConfiguration, modify the results of the getConfiguration call, and then write the new configuration to the parent folder of the existing tag(s). |
| collisionPolicy | String | The action to take when a tag or folder with the same path and name is encountered. Defaults to Overwrite. [optional]. Possible values include:a - Abort and throw an exception.o - Overwrite and replace existing tag's configuration.i - Ignore that item in the list.m - MergeOverwrite, modifying values that are specified in the definition, without impacting values that aren't defined in the definition. Use this when you want to apply a slight change to tags, without having to build a complete configuration object. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.tag.configure(basePath, tags, [collisionPolicy])
```


---



---

# system.tag.copy

**版本：** 8.1
**型別：** Scripting
**分類：** Tag

## 詳述

This function is used inPython Scripting. Copies tags from one folder to another. Multiple Tag and folder paths may be passed to a single call of this function. The new destination can be a separate tag provider. When copying UDTs to a different provider, the destination provider must have a matching UDT definition. The function copies Tags sequentially, so definitions can be placed earlier in the list, with instances following after:

## 語法

```python
system.tag.copy(tags, destination, [collisionPolicy])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| tags | List | A List of tag paths to move. |
| destination | String | The destination to copy the tags to. All specified tags will be copied to the same destination. The destination tag provider must be specified. |
| collisionPolicy | String | The action to take when a tag or folder with the same path and name is encountered. Defaults to Abort. [optional]. Possible values include:a - Abort and throw an exceptiono - Overwrite and replace existing tag's configurationi - Ignore that item in the list. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
# The '_types_' part of the path denotes the Data Types folder. You can retrieve the path to your UDT definition with right-click on
# on the Tag in the Tag Browser > Copy Tag Path.
udtDef = '[default]_types_/Motor'
udtInstances = '[default]UDT_Instances_Folder'

# When building the Tag list, place the definitions in list before the instances.
tags = [udtDef, udtInstances]
```

### Example 2

```python
# The '_types_' part of the path denotes the Data Types folder. You can retrieve the path to your UDT definition with right-click on
# on the Tag in the Tag Browser > Copy Tag Path.
udtDef = '[default]_types_/Motor'
udtInstances = '[default]UDT_Instances_Folder'

# When building the Tag list, place the definitions in list before the instances.
tags = [udtDef, udtInstances]
```

### Example 3

```python
system.tag.copy(tags, destination, [collisionPolicy])
```


---



---

# system.tag.deleteAnnotations

**版本：** 8.1
**型別：** Scripting
**分類：** Tag

## 詳述

This function is used inPython Scripting. Removes stored annotations from the sqlth_annotations table.  Requires the full Tag path (including history provider) for each annotation, as well as each annotation's storage ID.

## 語法

```python
system.tag.deleteAnnotations(paths, storageIds)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| paths | List[String] | A list of Tag paths with existing annotations. The paths are equivalent to what would be used for a Tag history query, and should specify the source provider as well. For example,HistoryProvider/Gateway:[Provider]Path/To/Tag. |
| storageIds | List[String] | A sequence of storage identifiers that will be deleted. Storage ID values can be retrieved withsystem.tag.queryAnnotations. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.tag.deleteAnnotations(paths, storageIds)
```

### Example 3

```python
HistoryProvider/Gateway:[Provider]Path/To/Tag
```


---



---

# system.tag.deleteTags

**版本：** 8.1
**型別：** Scripting
**分類：** Tag

## 詳述

This function is used inPython Scripting. Deletes multiple tags or tag folders. When deleting a tag folder, all tags under the folder are also deleted. Permission Type: Tag Editing

## 語法

```python
system.tag.deleteTags(tagPaths)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| tagPaths | List | A List of the paths to the tags or tag folders that are to be removed. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.tag.deleteTags(tagPaths)
```

### Example 3

```python
# This example will delete several Tags. Modify the paths argument to change which Tags will be deleted.
# Note that a confirmation isn't automatically included, so be cautious when calling this on a production server.

paths = [
    '[default]A_Tag',
    '[default]Folder/Some_Other_Tag'
]

# Delete the Tags.
results = system.tag.deleteTags(paths)

# We could expand this example further by examining the list of quality codes...
for index in range(len(results)):

    # ...check if a returned anything except Good.
    if results[index].isNotGood():

        # ...and do something if we failed, such as retrieve the Tag path from earlier, and pair it with a quality code.
        print 'Could not delete tag at path: %s \n Reason: %s' % (paths[index], results[index])
```


---



---

# system.tag.exists

**版本：** 8.1
**型別：** Scripting
**分類：** Tag

## 詳述

This function is used inPython Scripting. Checks whether or not a tag with a given path exists. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.tag.exists(tagPath)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| tagPath | String | The path of the tag to look up. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.tag.exists(tagPath)
```

### Example 3

```python
# This code would write a 1 to the Tag "Compressors/C28/ClearFault" if that Tag exists.

if system.tag.exists("Compressors/C28/ClearFault"):
   system.tag.write("Compressors/C28/ClearFault", 1)
```


---



---

# system.tag.exportTags

**版本：** 8.1
**型別：** Scripting
**分類：** Tag

## 詳述

This function is used inPython Scripting. Exports tags to a file on a local file system. The term "local file system" refers to the scope in which the script was running; for example, running this script in a Gateway Timer script will export the file to the Gateway file system.

## 語法

```python
system.tag.exportTags([filePath], tagPaths, [recursive], [exportType])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| filePath | String or Nothing | The file path that the tags will be exported to. If the file does not already exist, this function will attempt to create it.Changed in8.1.8Previously, the filePath parameter was required. If omitted, causes the function to return the tag export as a string. |
| tagPaths | List | A List of tag paths to export. All tag paths in the list must be from the same parent folder. |
| recursive | Boolean | Set to true to export all tags under each tag path, including tags in child folders. Defaults to true. [optional] |
| exportType | String | The type of file that will be exported. Set to "json" or "xml". Defaults to "json". |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.tag.exportTags([filePath], tagPaths, [recursive], [exportType])
```


---



---

# system.tag.getConfiguration

**版本：** 8.1
**型別：** Scripting
**分類：** Tag

## 詳述

This function is used inPython Scripting. Retrieves tags from the Gateway as Python dictionaries. These can be edited and then saved back usingsystem.tag.configure. The configurations returned by this function can only contain properties that arenotusing their default values. Thus, if a property on a tag has not been modified from its default value, then it willnotbe included in the returned list.

## 語法

```python
system.tag.readBlocking(["[default]path/to/tag.engUnit"])

```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| basePath | String | The starting point where the tags will be retrieved. This can be a folder containing, and ifrecursiveis true, then the function will retrieve all of the tags in the folder. |
| recursive | Boolean | If true, the entire tag tree under the specified path will be retrieved. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.tag.readBlocking(["[default]path/to/tag.engUnit"])
```

### Example 2

```python
system.tag.readBlocking(["[default]path/to/tag.engUnit"])
```

### Example 3

```python
system.tag.getConfiguration(basePath, recursive)
```


---



---

# system.tag.importTags

**版本：** 8.1
**型別：** Scripting
**分類：** Tag

## 詳述

This function is used inPython Scripting. Imports a JSON tag file at the provided path. Also supports XML and CSV Tag file exports from legacy systems. Permission Type: Tag Editing

## 語法

```python
system.tag.importTags(filePath, basePath, [collisionPolicy])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| filePath | String | The file path of the tag export to import. |
| basePath | String | The Tag path that will serve as the root node for the imported tags. |
| collisionPolicy | String | The action to take when a tag or folder with the same path and name is encountered. Defaults to Overwrite. [optional]. Possible values include:a - Abort and throw an exceptiono - Overwrite and replace existing tag's configurationi - Ignore that item in the list. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.tag.importTags(filePath, basePath, [collisionPolicy])
```


---



---

# system.tag.isOverlaysEnabled

**版本：** 8.1
**型別：** Scripting
**分類：** Tag

## 詳述

This function is used inPython Scripting. Returns whether or not the current client's quality overlay system is currently enabled. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.tag.isOverlaysEnabled()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.tag.isOverlaysEnabled()
```

### Example 2

```python
# This code will return whether or not overlays are currently enabled.
print system.tag.isOverlaysEnabled()
```

### Example 3

```python
# This code will return whether or not overlays are currently enabled.
print system.tag.isOverlaysEnabled()
```


---



---

# system.tag.move

**版本：** 8.1
**型別：** Scripting
**分類：** Tag

## 詳述

This function is used inPython Scripting. Moves tags or folders to a new destination. The new destination can be a separate tag provider. If interested in copying the tags to a new destination, instead of moving them, please see thesystem.tag.copypage. When moving UDTs to a different provider, the destination provider must have a matching UDT definition. This function moves folders/tags sequentially, so definitions can be placed earlier in the list, with instances following after.

## 語法

```python
system.tag.move(tags, destination, [collisionPolicy])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| tags | List | A List of tag paths to move. |
| destination | String | The destination to move the tags to. The destination tag provider must be specified: i.e.,[default]Folder/myTag. |
| collisionPolicy | String | The action to take when a tag or folder with the same path and name is encountered. Defaults to Overwrite. [optional]. Possible values include:a - Abort and throw an exceptiono - Overwrite and replace existing tag's configurationi - Ignore that item in the list. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.tag.move(tags, destination, [collisionPolicy])
```

### Example 3

```python
destination
```


---



---

# system.tag.query

**版本：** 8.1
**型別：** Scripting
**分類：** Tag

## 詳述

This function is used inPython Scripting. Queries a Tag Provider to produce a list of tags that meet the specified criteria. Provides the same functionality as theTag Report Tool.

## 語法

```python
system.tag.query([provider], [query], [limit], [continuation])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| provider | String | The Tag Provider to query.Note:Technically, this parameter is optional, but omitting it will result in an empty Results object. [optional] |
| query | PyObject | An object that specifies the query conditions. Can be configured in theTag Report Toolusing theCopy as Scriptfunction. See example below. [optional] |
| limit | Integer | Maximum results to return. If more results are possible, the result will have a continuation point set. [optional] |
| continuation | String | The tag ID of a previously returned continuation point, to continue the associated query from that point [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.tag.query([provider], [query], [limit], [continuation])
```


---



---

# system.tag.queryAnnotations

**版本：** 8.1
**型別：** Scripting
**分類：** Tag

## 詳述

This function is used inPython Scripting. Queries annotations stored in the Tag History system for a set of paths for a given time range.

## 語法

```python
system.tag.queryAnnotations(paths, [startTime], [endTime], [types])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| paths | List[String] | A list of tag paths to query. The paths are equivalent to what would be used for a Tag History Query, and should specify the Source Providers as well. For example,[HistoryProvider/Gateway:Provider]Path/To/Tag. |
| startTime | Date | The start of the time range. If not defined, defaults to 12 hours ago. [optional] |
| endTime | Date | The end of the time range. If not defined, defaults to "now". [optional] |
| types | List[String] | A list of string "types" to filter on. Types are defined by the annotations and various subsystems, and may vary with different providers. Possible annotation types are listed on thesystem.tag.storeAnnotationspage. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.tag.queryAnnotations(paths, [startTime], [endTime], [types])
```

### Example 3

```python
[HistoryProvider/Gateway:Provider]Path/To/Tag
```


---



---

# system.tag.queryTagCalculations

**版本：** 8.1
**型別：** Scripting
**分類：** Tag

## 詳述

This function is used inPython Scripting. Queries various calculations (aggregations) for a set of tags over a specified range. Returns a dataset with a row per tag, and a column per calculation. This is useful when you wish to aggregate tag history collected over a period of time into a single value per aggregate. If you want multiple values aggregated to a single time slice (i.e., hourly aggregates for the same tag over an 8 hour period) consider usingsystem.tag.queryTagHistory.

## 語法

```python
system.tag.queryTagCalculations(paths=['Historical Tag'], calculations=['Average'], noInterpolation=False)

```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| paths | List[String] | An array of tag paths (strings) to query calculations for. The resulting dataset will have a row for each tag, and a column for each calculation. |
| calculations | List[String] | An array of calculations (aggregation functions) to execute for each tag. Valid values are: "Average" (time-weighted), "MinMax", "LastValue", "SimpleAverage", "Sum", "Minimum", "Maximum", "DurationOn", "DurationOff", "CountOn", "CountOff", "Count", "Range", "Variance", "StdDev", "PctGood", and "PctBad". |
| startDate | Date | The starting point for the calculation window. If omitted, and range is not used, 8 hours before the current time is used. [optional] |
| endDate | Date | The end of the calculation window. If omitted, and range is not used, uses the current time. [optional] |
| rangeHours | Integer | Allows you to specify the query range in hours, instead of using start and end date. Can be positive or negative, and can be used in conjunction with startDate or endDate. [optional] |
| rangeMinutes | Integer | Same as rangeHours, but in minutes. [optional] |
| aliases | List[String] | Aliases that will be used to override the tag path names in the result dataset. Must be 1-to-1 with the tag paths. If not specified, the tag paths themselves will be used. [optional] |
| includeBoundingValues | Boolean | A boolean flag indicating that the system should attempt to load values before and after the query bounds for the purpose of interpolation. The effect depends on the aggregates used. The default is true. For more information seeSeeded Values. [optional] |
| validatesSCExec | Boolean | A boolean flag indicating whether or not data should be validated against the scan class execution records. If false, calculations may include data that is assumed to be good, even though the system may not have been running. Default is true. [optional] |
| noInterpolation | Boolean | A boolean flag indicating that the system should not attempt to interpolate values in situations where it normally would, such as for analog Tags. Default is false. [optional] |
| ignoreBadQuality | Boolean | A boolean flag indicating that bad quality values should not be used in the query process. If set, any value with a "bad" quality will be completely ignored in calculations. Default is false. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.tag.queryTagCalculations(paths, calculations, [startDate], [endDate], [rangeHours], [rangeMinutes], [aliases], [includeBoundingValues], [validatesSCExec], [noInterpolation], [ignoreBadQuality])
```

### Example 3

```python
calculations
```


---



---

# system.tag.queryTagDensity

**版本：** 8.1
**型別：** Scripting
**分類：** Tag

## 詳述

This function is used inPython Scripting. Queries the Tag history system for information about the density of data. In other words, how much data is available for a given time span. This function is called with a list of Tag paths, and a start and end date. The result set is a two column dataset specifying the timestamp, and a relative weight. Each row is valid from the given time until the next row. Tags are assigned a 1 or a 0 if they are present or not. All values are then multiplied together

## 語法

```python
system.tag.queryTagDensity(paths, startDate, endDate)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| paths | PySequence | An array of tag paths (strings) to query. |
| startDate | Date | The start of the range to query. |
| endDate | Date | The end of the range to query. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.tag.queryTagDensity(paths, startDate, endDate)
```


---



---

# system.tag.queryTagHistory

**版本：** 8.1
**型別：** Scripting
**分類：** Tag

## 詳述

This function is used inPython Scripting. Issues a query to the Tag Historian. Querying tag history involves specifying the tags and the date range, as well as a few optional parameters. The Tag Historian will find the relevant history and then interpolate and aggregate it together into a coherent, tabular result set. This function takes a list of strings, where each string is a tag path, likeTanks/Tank5or[OracleProvider]Sump/Out2. This function also supports historical tag paths, seeTag Pathsfo

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| paths | List[String] | An array of tag paths (strings) to query. Each tag path specified will be a column in the result dataset. |
| startDate | Date | The earliest value to retrieve. If omitted, 8 hours before current time is used. [optional] |
| endDate | Date | The latest value to retrieve. If omitted, current time is used. [optional] |
| returnSize | Integer | The number of samples to return. -1 will return values as they changed, and 0 will return the "natural" number of values based on the logging rates of the scan class(es) involved. -1 is the default. [optional] |
| aggregationMode | String | The mode to use when aggregating multiple samples into one time slice. Valid values are: "Average" (time-weighted), "MinMax", "LastValue", "SimpleAverage", "Sum", "Minimum", "Maximum", "DurationOn", "DurationOff", "CountOn", "CountOff", "Count", "Range", "Variance", "StdDev", "PctGood", and "PctBad". Default is "Average" (time-weighted). [optional] |
| returnFormat | String | Use "Wide" to have a column per tag queried, or "Tall" to have a fixed-column format. Default is "Wide". [optional] |
| columnNames | List[String] | Aliases that will be used to override the column names in the result dataset. Must be 1-to-1 with the tag paths. If not specified, the Tag paths themselves will be used as column titles. [optional] |
| intervalHours | Integer | Allows you to specify the window interval in terms of hours, as opposed to using a specific returnSize. The Historian will use the intervalHours value to determine the return size automatically based on the start and end date. For example, if your start and end date are 12 hours apart, and you pass an interval of 2 hours, the Historian will calculate your return size as 6. If you specify a returnSize, all interval parameters are ignored. [optional] |
| intervalMinutes | Integer | Same as intervalHours, but in minutes. Can be used on its own, or in conjunction with intervalHours. [optional] |
| rangeHours | Integer | Allows you to specify the query range in hours, instead of using start and end date. Can be positive or negative, and can be used in conjunction with startDate or endDate. [optional] |
| rangeMinutes | Integer | Same as rangeHours, but in minutes. [optional] |
| aggregationModes | List[String] | A one-to-one list with paths specifying an aggregation mode per column. [optional] |
| includeBoundingValues | Boolean | A boolean flag indicating that the system should attempt to include values for the query bound times if possible. The default for this property depends on the query mode. For more information seeSeeded Values. [optional] |
| validateSCExec | Boolean | A boolean flag indicating whether or not data should be validated against the scan class execution records. If false, data will appear flat (but good quality) for periods of time in which the system wasn't running. If true, the same data would be bad quality during downtime periods. [optional] |
| noInterpolation | Boolean | A boolean flag indicating that the system should not attempt to interpolate values in situations where it normally would. This will also prevent the return of rows that are purely interpolated. [optional] |
| ignoreBadQuality | Boolean | A boolean flag indicating that bad quality values should not be used in the query process. If set, any value with a "bad" quality will be completely ignored in calculations and in the result set. [optional] |
| timeout | Integer | Timeout in milliseconds for Client Scope. This property is ignored in the Gateway Scope. [optional] |
| intervalSeconds | Integer | New in8.1.0Same as intervalHours and interval Minutes, but in seconds. Can be used on its own, or in conjunction with intervalHours and intervalMinutes. [optional] |
| rangeSeconds | Integer | New in8.1.0Allows you to specify the query range in seconds, instead of using start and end date. Can be positive or negative, and can be used in conjunction with startDate or endDate. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
Tanks/Tank5
```

### Example 2

```python
[OracleProvider]Sump/Out2
```

### Example 3

```python
system.tag.queryTagHistory(paths, [startDate], [endDate], [returnSize], [aggregationMode], [returnFormat], [columnNames], [intervalHours], [intervalMinutes], [rangeHours], [rangeMinutes], [aggregationModes], [includeBoundingValues], [validateSCExec], [noInterpolation], [ignoreBadQuality], [timeout], [intervalSeconds], [rangeSeconds])
```


---



---

# system.tag.readAsync

**版本：** 8.1
**型別：** Scripting
**分類：** Tag

## 詳述

This function is used inPython Scripting. Asynchronously reads the value of the tags at the given paths. Meaning, execution of the calling script will continue without waiting for this function to finish. This is useful in cases where the rest of the script should continue without waiting for the results from system.tag.readAsync. Instead of returning the tag read results to the calling script, the results are processed by a Python callback function.

## 語法

```python
system.tag.readAsync(tagPaths, callback)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| tagPaths | List | A List of Tag paths to read from. If no property is specified in the path, the Value property is assumed. |
| callback | Callable | A Python callback function to process the read results. The function definition must provide a single argument, which will hold a List of qualified values when the callback function is invoked. The qualified values will have three sub-members: value, quality, and timestamp. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.tag.readAsync(tagPaths, callback)
```


---



---

# system.tag.readBlocking

**版本：** 8.1
**型別：** Scripting
**分類：** Tag

## 詳述

This function is used inPython Scripting. Reads the value of the tags at the given paths. Will "block" until the read operation is complete or times out. Meaning, execution of the calling script will pause until this function finishes. This is useful in cases where the tag read must complete before further lines in the same script should execute. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.tag.readBlocking(tagPaths, [timeout])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| tagPaths | String or List[String] | Either a string of a single tag path, or a list of strings tag paths to read from. If no property is specified in a path, the Value property is assumed. |
| timeout | Integer | How long to wait in milliseconds before the read operation times out. This parameter is optional, and defaults to 45000 milliseconds if not specified. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.tag.readBlocking(tagPaths, [timeout])
```


---



---

# system.tag.rename

**版本：** 8.1
**型別：** Scripting
**分類：** Tag

## 詳述

This function is used inPython Scripting. Renames a single tag or folder. Permission Type: Tag Editing

## 語法

```python
system.tag.rename(tag, newName, [collisionPolicy])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| tag | String | A path to the tag or folder to rename. |
| newName | String | The new name for the tag or folder. |
| collisionPolicy | String | The action to take when a tag or folder with the same path and name is encountered. Defaults to Abort. [optional]. Possible values include:a - Abort and throw an exceptiono - Overwrite and replace existing tag's configurationi - Ignore that item in the list. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.tag.rename(tag, newName, [collisionPolicy])
```


---



---

# system.tag.requestGroupExecution

**版本：** 8.1
**型別：** Scripting
**分類：** Tag

## 詳述

This function is used inPython Scripting. Sends a request to the specified tag group to execute now. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.tag.requestGroupExecution(provider, tagGroup)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| provider | String | Name of the Tag Provider that the tag group is in. |
| tagGroup | String | The name of the tag group to execute. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.tag.requestGroupExecution(provider, tagGroup)
```


---



---

# system.tag.setOverlaysEnabled

**版本：** 8.1
**型別：** Scripting
**分類：** Tag

## 詳述

This function is used inPython Scripting. Enables or disables the component quality overlay system. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.tag.setOverlaysEnabled(enabled)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| enabled | Boolean | True to turn on Tag overlays; false to turn them off. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.tag.setOverlaysEnabled(enabled)
```

### Example 3

```python
# This example will turn Tag overlays on.
system.tag.setOverlaysEnabled(True)
```


---



---

# system.tag.storeAnnotations

**版本：** 8.1
**型別：** Scripting
**分類：** Tag

## 詳述

This function is used inPython Scripting. Stores annotations into the tag history system. Annotations are stored by the underlying historian implementations, so different providers may store in different ways, and some providers may not support annotation storage. All parameters are 1-to-1, so all provided lists should be of the same length. If a particular annotation doesn't need a parameter, that element can be None in the list.

## 語法

```python
system.tag.storeAnnotations(paths, startTimes, [endTimes], [types], [data], [storageIds], [deleted])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| paths | List[String] | A list of tag paths to store for. The paths are equivalent to what would be used for a tag history query, and should specify the source provider as well. For example,[HistoryProvider/Gateway:Provider]Path/To/Tag. This parameter is required, even if storage ids are included, because it is used to identify the underlying storage provider. |
| startTimes | List[Date] | The start times of the events. If omitted, defaults to the current time. |
| endTimes | List[Date] | The end times of the event, if applicable. If omitted, does not store an end time for the annotation. [optional] |
| types | List[Annotation] | The type id for the annotation. If not defined, "marker" will be used. See theAnnotation Typesfor more details. [optional] |
| data | List[String] | Data for the annotation, such as text describing the meaning of the annotation. [optional] |
| storageIds | List[String] | If defined, the function will instead update the existing annotation instead of adding new ones, overriding existing values for the annotation with those provided by this function (if the corresponding delete parameter is True). Storage id is available on the Annotation object, and is returned as the result value from the storeAnnotations call. [optional] |
| deleted | List[Boolean] | A list of booleans indicating that the individual annotation should be deleted. Requires storage id to be set as well. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.tag.storeAnnotations(paths, startTimes, [endTimes], [types], [data], [storageIds], [deleted])
```

### Example 3

```python
[HistoryProvider/Gateway:Provider]Path/To/Tag
```


---



---

# system.tag.storeTagHistory

**版本：** 8.1
**型別：** Scripting
**分類：** Tag

## 詳述

This function was originally deprecated in 8.0.0. It was reintroduced in version 8.1.8. This function is used inPython Scripting. Inserts data into the tag history system, allowing Tag history to be recorded via scripting.

## 語法

```python
system.tag.storeTagHistory(historyprovider, tagprovider, paths, values, [qualities], [timestamps])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| historyprovider | String | The historical provider to store to. |
| tagprovider | String | The name of the realtime Tag Provider to associate these tags with. The Tag Provider does not need to exist, and the Tag paths do not need to exist in it. |
| paths | List | A list of paths to store. The values, qualities, and timestamps are one-to-one with the paths. A single path may be present multiple times in order to store multiple values. |
| values | List | A list of values to store. |
| qualities | List | A list of integer quality codes corresponding to the values. Quality codes can be found on theQuality Codes and Overlayspage. If omitted, GOOD quality will be used. [optional] |
| timestamps | List | A list of Date timestamps corresponding to the values. If omitted, the current time will be used. A java.util.date object may be passed, so thesystem.datefunctions can be used to return a timestamp. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.tag.storeTagHistory(historyprovider, tagprovider, paths, values, [qualities], [timestamps])
```

### Example 2

```python
historyprovider
```

### Example 3

```python
tagprovider
```


---



---

# system.tag.writeAsync

**版本：** 8.1
**型別：** Scripting
**分類：** Tag

## 詳述

This function is used inPython Scripting. Asynchronously writes values to tags at specified paths. The script will not wait for the write operation to complete before moving on, but you can provide a callback function to run further code after the write has finished. For a blocking tag write operation, seesystem.tag.writeBlocking.

## 語法

```python
system.tag.writeAsync(tagPaths, values, [callback])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| tagPaths | List | A List of tag paths to write to. A tag property can be included in the path. If no property is specified in a tag path, the Value property is assumed. |
| values | List | The values to write to the specified paths. |
| callback | Callable | A function that will be invoked after the write operation is complete. The function must take a single argument: a List ofQualityCodeobjects corresponding to the results of the write operation. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.tag.writeAsync(tagPaths, values, [callback])
```


---



---

# system.tag.writeBlocking

**版本：** 8.1
**型別：** Scripting
**分類：** Tag

## 詳述

This function is used inPython Scripting. Writes values to tags at the given paths. This function will "block" until the write operation is complete or times out. Meaning, execution of the calling script will pause until this function finishes. This is useful in cases where the tag write must complete before further lines in the same script should execute. Permission Type: Tag Editing

## 語法

```python
system.tag.writeBlocking(tagPaths, values, [timeout])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| tagPaths | List | A List of tag paths to write to. If no property is specified in a tag path, the Value property is assumed. |
| values | List | A list of values to write to the specified tag paths. |
| timeout | Integer | How long to wait in milliseconds before the write operation times out. This parameter is optional and defaults to 45000 milliseconds if not specified. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.tag.writeBlocking(tagPaths, values, [timeout])
```


---

