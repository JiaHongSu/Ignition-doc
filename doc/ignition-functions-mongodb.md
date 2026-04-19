# Ignition 8.1 - system.mongodb 函數文檔

﻿# Ignition 8.1 - 函數文檔（PATTERN 規範）

> 根據 FUNCTION_PATTERN 爬蟲生成
> 生成時間: 2026年04月19日 00:56:44
> 總計函式數: 434

## 📑 目錄

---

1. [system.mongodb.aggregate](#systemmongodbaggregate) - This function is used inPython Scripting. Project Library scripts will not provide hints for MongoDB system functions unless the Script Hint Scope is set toGateway. See theScripting in Ignitionpage for more details on scripting hints.
2. [system.mongodb.deleteMany](#systemmongodbdeletemany) - This function is used inPython Scripting. Project Library scripts will not provide hints for MongoDB system functions unless the Script Hint Scope is set toGateway. See theScripting in Ignitionpage for more details on scripting hints.
3. [system.mongodb.deleteOne](#systemmongodbdeleteone) - This function is used inPython Scripting. Project Library scripts will not provide hints for MongoDB system functions unless the Script Hint Scope is set toGateway. See theScripting in Ignitionpage for more details on scripting hints.
4. [system.mongodb.find](#systemmongodbfind) - This function is used inPython Scripting. Project Library scripts will not provide hints for MongoDB system functions unless the Script Hint Scope is set toGateway. See theScripting in Ignitionpage for more details on scripting hints.
5. [system.mongodb.findOne](#systemmongodbfindone) - This function is used inPython Scripting. Project Library scripts will not provide hints for MongoDB system functions unless the Script Hint Scope is set toGateway. See theScripting in Ignitionpage for more details on scripting hints.
6. [system.mongodb.insertMany](#systemmongodbinsertmany) - This function is used inPython Scripting. Project Library scripts will not provide hints for MongoDB system functions unless the Script Hint Scope is set toGateway. See theScripting in Ignitionpage for more details on scripting hints.
7. [system.mongodb.insertOne](#systemmongodbinsertone) - This function is used inPython Scripting. Project Library scripts will not provide hints for MongoDB system functions unless the Script Hint Scope is set toGateway. See theScripting in Ignitionpage for more details on scripting hints.
8. [system.mongodb.listCollectionNames](#systemmongodblistcollectionnames) - This function is used inPython Scripting. Project Library scripts will not provide hints for MongoDB system functions unless the Script Hint Scope is set toGateway. See theScripting in Ignitionpage for more details on scripting hints.
9. [system.mongodb.listConnectorInfo](#systemmongodblistconnectorinfo) - This function is used inPython Scripting. Project Library scripts will not provide hints for MongoDB system functions unless the Script Hint Scope is set toGateway. See theScripting in Ignitionpage for more details on scripting hints.
10. [system.mongodb.replaceOne](#systemmongodbreplaceone) - This function is used inPython Scripting. Project Library scripts will not provide hints for MongoDB system functions unless the Script Hint Scope is set toGateway. See theScripting in Ignitionpage for more details on scripting hints.
11. [system.mongodb.updateMany](#systemmongodbupdatemany) - This function is used inPython Scripting. Project Library scripts will not provide hints for MongoDB system functions unless the Script Hint Scope is set toGateway. See theScripting in Ignitionpage for more details on scripting hints.
12. [system.mongodb.updateOne](#systemmongodbupdateone) - This function is used inPython Scripting. Project Library scripts will not provide hints for MongoDB system functions unless the Script Hint Scope is set toGateway. See theScripting in Ignitionpage for more details on scripting hints.

---

# system.mongodb.aggregate

**版本：** 8.1
**型別：** Scripting
**分類：** Mongodb

## 詳述

This function is used inPython Scripting. Project Library scripts will not provide hints for MongoDB system functions unless the Script Hint Scope is set toGateway. See theScripting in Ignitionpage for more details on scripting hints.

## 語法

```python
system.mongodb.aggregate(connector, collection, aggregate, [collation])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| connector | String | The name of connector (case-insensitive). |
| collection | String | The name of collection (case-sensitive). |
| aggregate | List[PyDictionary] | A list of PyDictionaries to specify an aggregate pipeline.See MongoDB documentationfor all valid aggregate options. |
| collation | PyDictionary | A PyDictionary of items to specify language-specific rules.See MongoDB documentationfor all valid collation values. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.mongodb.aggregate(connector, collection, aggregate, [collation])
```


---



---

# system.mongodb.deleteMany

**版本：** 8.1
**型別：** Scripting
**分類：** Mongodb

## 詳述

This function is used inPython Scripting. Project Library scripts will not provide hints for MongoDB system functions unless the Script Hint Scope is set toGateway. See theScripting in Ignitionpage for more details on scripting hints.

## 語法

```python
system.mongodb.deleteMany(connector, collection, filter, [options])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| connector | String | The name of connector (case-insensitive). |
| collection | String | The name of collection (case-sensitive). |
| filter | PyDictionary | A PyDictionary for specifying matching key value pair criteria when querying a collection. |
| options | PyDictionary | A PyDictionary for including additional delete configurations. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.mongodb.deleteMany(connector, collection, filter, [options])
```


---



---

# system.mongodb.deleteOne

**版本：** 8.1
**型別：** Scripting
**分類：** Mongodb

## 詳述

This function is used inPython Scripting. Project Library scripts will not provide hints for MongoDB system functions unless the Script Hint Scope is set toGateway. See theScripting in Ignitionpage for more details on scripting hints.

## 語法

```python
system.mongodb.deleteOne(connector, collection, filter, [options])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| connector | String | The name of connector (case-insensitive). |
| collection | String | The name of collection (case-sensitive). |
| filter | PyDictionary | A PyDictionary for specifying matching key value pair criteria when querying a collection. |
| options | PyDictionary | A PyDictionary for including additional delete configurations. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.mongodb.deleteOne(connector, collection, filter, [options])
```


---



---

# system.mongodb.find

**版本：** 8.1
**型別：** Scripting
**分類：** Mongodb

## 詳述

This function is used inPython Scripting. Project Library scripts will not provide hints for MongoDB system functions unless the Script Hint Scope is set toGateway. See theScripting in Ignitionpage for more details on scripting hints.

## 語法

```python
system.mongodb.find(connector, collection, filter, [projection], [sort], [collation], [limit], [skip])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| connector | String | The name of connector (case-insensitive). |
| collection | String | The name of collection (case-sensitive). |
| filter | PyDictionary | A PyDictionary for specifying matching key value pair criteria when querying a collection. |
| projection | PyDictionary | A PyDictionary for including or omitting specific key value pairs in the query result.See MongoDB documentationfor all valid project values. [optional] |
| sort | PyDictionary | A PyDictionary of specified items to sort returned results.See MongoDB documentationfor all valid sort values. [optional] |
| collation | PyDictionary | A PyDictionary of items to specify language-specific rules.See MongoDB documentationfor all valid collation values. [optional] |
| limit | Int | The maximum number of PyDictionaries that will be returned. [optional] |
| skip | Int | The number of PyDictionaries to skip before returning results. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.mongodb.find(connector, collection, filter, [projection], [sort], [collation], [limit], [skip])
```


---



---

# system.mongodb.findOne

**版本：** 8.1
**型別：** Scripting
**分類：** Mongodb

## 詳述

This function is used inPython Scripting. Project Library scripts will not provide hints for MongoDB system functions unless the Script Hint Scope is set toGateway. See theScripting in Ignitionpage for more details on scripting hints.

## 語法

```python
system.mongodb.findOne(connector, collection, filter, [projection])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| connector | String | The name of connector (case-insensitive). |
| collection | String | The name of collection (case-sensitive). |
| filter | PyDictionary | A PyDictionary for specifying matching key value pair criteria when querying a collection. |
| projection | PyDictionary | A PyDictionary for including or omitting specific key value pairs in the query result.See MongoDB documentationfor all valid project values. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.mongodb.findOne(connector, collection, filter, [projection])
```


---



---

# system.mongodb.insertMany

**版本：** 8.1
**型別：** Scripting
**分類：** Mongodb

## 詳述

This function is used inPython Scripting. Project Library scripts will not provide hints for MongoDB system functions unless the Script Hint Scope is set toGateway. See theScripting in Ignitionpage for more details on scripting hints.

## 語法

```python
system.mongodb.insertMany(connector, collection, document, [options])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| connector | String | The name of connector (case-insensitive). |
| collection | String | The name of collection (case-sensitive). |
| document | List[PyDictionary] | A list of PyDictionaries that will represent new records being added to the collection.See MongoDB documentationfor more details about documents. |
| options | PyDictionary | A PyDictionary for including additional insert configurations. [optional]. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.mongodb.insertMany(connector, collection, document, [options])
```


---



---

# system.mongodb.insertOne

**版本：** 8.1
**型別：** Scripting
**分類：** Mongodb

## 詳述

This function is used inPython Scripting. Project Library scripts will not provide hints for MongoDB system functions unless the Script Hint Scope is set toGateway. See theScripting in Ignitionpage for more details on scripting hints.

## 語法

```python
system.mongodb.insertOne(connector, collection, document, [options])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| connector | String | The name of connector (case-insensitive). |
| collection | String | The name of collection (case-sensitive). |
| document | PyDictionary | A PyDictionary of specified fields that will represent a record being added to the collection.See MongoDB documentationfor more details about documents. |
| options | PyDictionary | A PyDictionary for including additional insert configurations. [optional]. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.mongodb.insertOne(connector, collection, document, [options])
```


---



---

# system.mongodb.listCollectionNames

**版本：** 8.1
**型別：** Scripting
**分類：** Mongodb

## 詳述

This function is used inPython Scripting. Project Library scripts will not provide hints for MongoDB system functions unless the Script Hint Scope is set toGateway. See theScripting in Ignitionpage for more details on scripting hints.

## 語法

```python
system.mongodb.listCollectionNames(connector)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| connector | String | Name of connector (case-insensitive). |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.mongodb.listCollectionNames(connector)
```

### Example 3

```python
collectionNames
```


---



---

# system.mongodb.listConnectorInfo

**版本：** 8.1
**型別：** Scripting
**分類：** Mongodb

## 詳述

This function is used inPython Scripting. Project Library scripts will not provide hints for MongoDB system functions unless the Script Hint Scope is set toGateway. See theScripting in Ignitionpage for more details on scripting hints.

## 語法

```python
system.mongodb.listConnectorInfo()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.mongodb.listConnectorInfo()
```

### Example 3

```python
# Retrieve and print the returned list of connectors found.
connectors = system.mongodb.listConnectorInfo()

print connectors[0]['name']
print connectors[0]['status']
print connectors[0]['description']
print connectors[0]['error']
```


---



---

# system.mongodb.replaceOne

**版本：** 8.1
**型別：** Scripting
**分類：** Mongodb

## 詳述

This function is used inPython Scripting. Project Library scripts will not provide hints for MongoDB system functions unless the Script Hint Scope is set toGateway. See theScripting in Ignitionpage for more details on scripting hints.

## 語法

```python
system.mongodb.replaceOne(connector, collection, filter, replacement, [options])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| connector | String | The name of connector (case-insensitive). |
| collection | String | The name of collection (case-sensitive). |
| filter | PyDictionary | A PyDictionary for specifying matching key value pair criteria when querying a collection. |
| replacement | PyDictionary | New values to apply for all non-immutable document fields. |
| options | PyDictionary | A PyDictionary for including additional replace configurations. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.mongodb.replaceOne(connector, collection, filter, replacement, [options])
```


---



---

# system.mongodb.updateMany

**版本：** 8.1
**型別：** Scripting
**分類：** Mongodb

## 詳述

This function is used inPython Scripting. Project Library scripts will not provide hints for MongoDB system functions unless the Script Hint Scope is set toGateway. See theScripting in Ignitionpage for more details on scripting hints.

## 語法

```python
system.mongodb.updateMany(connector, collection, filter, updates, [options])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| connector | String | The name of connector (case-insensitive). |
| collection | String | The name of collection (case-sensitive). |
| filter | PyDictionary | A PyDictionary for specifying matching key value pair criteria when querying a collection. |
| List[PyDictionary] | PyDictionary | updates |
| options | PyDictionary | A PyDictionary for including additional update configurations. [optional]. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.mongodb.updateMany(connector, collection, filter, updates, [options])
```


---



---

# system.mongodb.updateOne

**版本：** 8.1
**型別：** Scripting
**分類：** Mongodb

## 詳述

This function is used inPython Scripting. Project Library scripts will not provide hints for MongoDB system functions unless the Script Hint Scope is set toGateway. See theScripting in Ignitionpage for more details on scripting hints.

## 語法

```python
system.mongodb.updateOne(connector, collection, filter, updates, [options])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| connector | String | The name of connector (case-insensitive). |
| collection | String | The name of collection (case-sensitive). |
| filter | PyDictionary | A PyDictionary for specifying matching key value pair criteria when querying a collection. |
| updates | PyDictionary / List[PyDictionary] | Changes to apply to specific document fields. Also supports aggregation pipeline for update operations SeeMongoDB documentationfor all valid update operators. |
| options | PyDictionary | A PyDictionary for including additional update configurations. [optional]. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.mongodb.updateOne(connector, collection, filter, updates, [options])
```


---

