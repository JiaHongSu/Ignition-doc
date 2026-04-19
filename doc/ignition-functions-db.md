# Ignition 8.1 - system.db 函數文檔

﻿# Ignition 8.1 - 函數文檔（PATTERN 規範）

> 根據 FUNCTION_PATTERN 爬蟲生成
> 生成時間: 2026年04月19日 00:56:44
> 總計函式數: 434

## 📑 目錄

---

1. [system.db.addDatasource](#systemdbadddatasource) - This function is used inPython Scripting. Adds a new database connection in Ignition. Permission Type: Datasource Management
2. [system.db.beginNamedQueryTransaction](#systemdbbeginnamedquerytransaction) - This function is used inPython Scripting. Begins a new database transaction usingNamed Queries. Database transactions are used to execute multiple queries in an atomic fashion. After executing queries, you must either commit the transaction to have your changes take effect or rollback the transaction, which will make all operations since the last commit not take place. The transaction is given a new unique string code, which is then returned. You can then use this code as the tx argument for oth
3. [system.db.beginTransaction](#systemdbbegintransaction) - This function is used inPython Scripting. Begins a new database transaction for using run* and runPrep* queries. Database transactions are used to execute multiple queries in an atomic fashion. After executing queries, you must either commit the transaction to have your changes take effect, or rollback the transaction which will make all operations since the last commit not take place. The transaction is given a new unique string code, which is then returned. You can then use this code  as the t
4. [system.db.clearAllNamedQueryCaches](#systemdbclearallnamedquerycaches) - This function is used inPython Scripting. This clears the caches of all Named Queries in a project. If called from the shared scope (i.e., Tag Event Scripts, Alarm Pipelines, etc.), then the name of the project must be passed as a parameter. This scripting function has noClient Permissionrestrictions.
5. [system.db.clearNamedQueryCache](#systemdbclearnamedquerycache) - This function is used inPython Scripting. This clears the cache of a Named Query. If called from the shared scope (i.e., Tag Event Scripts, Alarm Pipelines, etc.) then the name of the project must be passed as a parameter. This scripting function has noClient Permissionrestrictions.
6. [system.db.closeTransaction](#systemdbclosetransaction) - This function is used inPython Scripting. Closes the transaction with the given ID. You must commit or rollback the transaction before you close it. Closing the transaction will return its database connection to the pool. The transaction ID will no longer be valid. This scripting function hasClient Permissionrestrictions.
7. [system.db.commitTransaction](#systemdbcommittransaction) - This function is used inPython Scripting. Performs a commit for the given transaction. This will make all statements executed against the transaction since its beginning or since the last commit or rollback take effect in the database. Until you commit a transaction, any changes that the transaction makes will not be visible to other connections. If you are done with the transaction, you must close it after you commit it.
8. [system.db.createSProcCall](#systemdbcreatesproccall) - This function is used inPython Scripting. Creates an SProcCall object, which is a stored procedure call context. This is an object that is used to configure a call to a stored procedure. Once configured, you'd use system.db.execSProcCall to call the stored procedure. The call context object then holds any results from the stored procedure. The SProcCall object has the following functions used for registering parameters: These functions are used to register any in/out parameters for the stored pr
9. [system.db.dateFormat](#systemdbdateformat) - This function is used inPython Scripting. This function is used to format dates nicely as strings. It uses a format string to guide its formatting behavior. Learn more about date formatting inDates. This scripting function has noClient Permissionrestrictions.
10. [system.db.execSProcCall](#systemdbexecsproccall) - This function is used inPython Scripting. Executes a stored procedure call. The one parameter to this function is an SProcCall - a stored procedure call context. See the description ofsystem.db.createSProcCallfor more information and examples.
11. [system.db.getConnectionInfo](#systemdbgetconnectioninfo) - This function is used inPython Scripting. Returns a dataset of information about a single database connection, as specified by the name argument. This scripting function has noClient Permissionrestrictions.
12. [system.db.getConnections](#systemdbgetconnections) - This function is used inPython Scripting. Returns a dataset of information about each configured database connection. Each row represents a single connection. This scripting function has noClient Permissionrestrictions.
13. [system.db.refresh](#systemdbrefresh) - This function is used inPython Scripting. This function will cause a Vision component binding to execute immediately. This is most often used for bindings that are set to  Polling - Off.  In this way, you cause a binding to execute on demand, when you know that the results of its query will return a new result. To use it, you simply specify the component and name of the property on whose binding you'd like to refresh. Even though the function includes "db" in the name, the function can update al
14. [system.db.removeDatasource](#systemdbremovedatasource) - This function is used inPython Scripting. Removes a database connection from Ignition. Permission Type: Datasource Management
15. [system.db.rollbackTransaction](#systemdbrollbacktransaction) - This function is used inPython Scripting. Performs a rollback on the given connection. This will make all statements executed against this transaction since its beginning or since the last commit or rollback undone. If you are done with the transaction, you must also close it after you do a rollback on it.
16. [system.db.runNamedQuery](#systemdbrunnamedquery) - This function is used inPython Scripting. Runs a Named Query and returns the results. Note that the number of parameters in the function is determined by scope. Both versions of the function are listed below. This function acceptskeyword arguments.
17. [system.db.runPrepQuery](#systemdbrunprepquery) - This function is used inPython Scripting. Runs a  prepared statement  against the database, returning the results in a PyDataSet. Prepared statements differ from regular queries in that they can use a special placeholder, the question-mark character (?), in the query where any dynamic arguments would go, and then use an array of values to provide real information for those arguments. Make sure that the length of your argument array matches the number of question-mark placeholders in your query. 
18. [system.db.runPrepUpdate](#systemdbrunprepupdate) - This function is used inPython Scripting. Runs a prepared statement against the database, returning the number of rows that were affected. Prepared statements differ from regular queries in that they can use a special placeholder, the question-mark character (?), in the query where any dynamic arguments would go, and then use an array of values to provide real information for those arguments. Make sure that the length of your argument array matches the number of question-mark placeholders in you
19. [system.db.runQuery](#systemdbrunquery) - This function is used inPython Scripting. Runs a SQL query, usually a SELECT query, against a database, returning the results as a dataset. If no database is specified, or the database is the empty-string "", then the current project's default database connection will be used. The results are returned as a PyDataSet, which is a wrapper around the standard dataset that is convenient for scripting. Permission Type: Legacy Database Access
20. [system.db.runSFPrepUpdate](#systemdbrunsfprepupdate) - This function is used inPython Scripting. Runs a prepared statement query through theStore and Forwardsystem and to multiple datasources at the same time. Prepared statements differ from regular queries in that they can use a special placeholder, the question-mark character (?) in the query where any dynamic arguments would go, and then use an array of values to provide real information for those arguments. Make sure that the length of your argument array matches the number of question-mark plac
21. [system.db.runSFUpdateQuery](#systemdbrunsfupdatequery) - This function is used inPython Scripting. Runs a query through theStore and Forwardsystem and to multiple datasources at the same time. Permission Type: Legacy Database Access
22. [system.db.runScalarPrepQuery](#systemdbrunscalarprepquery) - This function is used inPython Scripting. Runs a prepared statement against a database connection just like the runPrepQuery function, but only returns the value from the first row and column. If no results are returned from the query, the special value None is returned. Permission Type: Legacy Database Access
23. [system.db.runScalarQuery](#systemdbrunscalarquery) - This function is used inPython Scripting. Runs a query against a database connection just like the runQuery function, but only returns the value from the first row and column.  If no results are returned from the query, the special value None is returned. Permission Type: Legacy Database Access
24. [system.db.runUpdateQuery](#systemdbrunupdatequery) - This function is used inPython Scripting. Runs a query against a database connection, returning the number of rows affected. Typically this is an UPDATE, INSERT, or DELETE query. If no database is specified, or the database is the empty-string "", then the current project's default database connection will be used. You may want to use the runPrepUpdate query if your query is constructed with user input (to avoid the user's input from breaking your syntax) or if you need to insert binary or BLOB 
25. [system.db.setDatasourceConnectURL](#systemdbsetdatasourceconnecturl) - This function is used inPython Scripting. Changes the connect URL for a given database connection. Permission Type: Datasource Management
26. [system.db.setDatasourceEnabled](#systemdbsetdatasourceenabled) - This function is used inPython Scripting. Enables/disables a given database connection. Permission Type: Datasource Management
27. [system.db.setDatasourceMaxConnections](#systemdbsetdatasourcemaxconnections) - This function is used inPython Scripting. Sets theMax ActiveandMax Idleparameters of a given database connection. Permission Type: Datasource Management

---

# system.db.addDatasource

**版本：** 8.1
**型別：** Scripting
**分類：** Db

## 詳述

This function is used inPython Scripting. Adds a new database connection in Ignition. Permission Type: Datasource Management

## 語法

```python
system.db.addDatasource(jdbcDriver, name, description, [connectUrl], [username], [password], [props], [validationQuery], [maxConnections])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| jdbcDriver | String | The name of the JDBC driver configuration to use. Available options are based off the JDBC driver configurations on the the Gateway. |
| name | String | The datasource name. |
| description | String | Description of the datasource. [optional] |
| connectUrl | String | Default is the connect URL for JDBC driver. [optional] |
| username | String | Username to login to the datasource with. [optional] |
| password | String | Password for the login. [optional] |
| props | String | The extra connection parameters. [optional] |
| validationQuery | String | Default is the validation query for the JDBC driver. [optional] |
| maxConnections | Integer | Default is 8. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.db.addDatasource(jdbcDriver, name, description, [connectUrl], [username], [password], [props], [validationQuery], [maxConnections])
```


---



---

# system.db.beginNamedQueryTransaction

**版本：** 8.1
**型別：** Scripting
**分類：** Db

## 詳述

This function is used inPython Scripting. Begins a new database transaction usingNamed Queries. Database transactions are used to execute multiple queries in an atomic fashion. After executing queries, you must either commit the transaction to have your changes take effect or rollback the transaction, which will make all operations since the last commit not take place. The transaction is given a new unique string code, which is then returned. You can then use this code as the tx argument for oth

## 語法

```python
system.db.beginNamedQueryTransaction([database], [isolationLevel], [timeout])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| database | String | The name of the database connection to create a transaction in. If omitted, uses the project's default connection. |
| isolationLevel | Integer | The transaction isolation level to use. Use one of the four constants:system.db.READ_COMMITTED,system.db.READ_UNCOMMITTED,system.db.REPEATABLE_READ, orsystem.db.SERIALIZABLE. If omitted, usessystem.db.READ_COMMITTED. [optional] |
| timeout | Integer | The amount of time, in milliseconds, that this connection is allowed to remain open without being used. Timeout counter is reset any time a query or call is executed against the transaction, or when committed or rolled-back. If omitted, defaults to 30,000. [optional] |
| project | String | The name of the project that contains the named query. |
| database | String | The name of the database connection to create a transaction in. |
| isolationLevel | Integer | The transaction isolation level to use. Use one of the four constants: system.db.READ_COMMITTED, system.db.READ_UNCOMMITTED, system.db.REPEATABLE_READ, or system.db.SERIALIZABLE. If omitted, uses system.db.READ_COMMITTED. [optional] |
| timeout | Integer | The amount of time, in milliseconds, that this connection is allowed to remain open without being used. Timeout counter is reset any time a query or call is executed against the transaction, or when committed or rolled-back. If omitted, defaults to 30,000. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.db.beginNamedQueryTransaction([database], [isolationLevel], [timeout])
```

### Example 3

```python
isolationLevel
```


---



---

# system.db.beginTransaction

**版本：** 8.1
**型別：** Scripting
**分類：** Db

## 詳述

This function is used inPython Scripting. Begins a new database transaction for using run* and runPrep* queries. Database transactions are used to execute multiple queries in an atomic fashion. After executing queries, you must either commit the transaction to have your changes take effect, or rollback the transaction which will make all operations since the last commit not take place. The transaction is given a new unique string code, which is then returned. You can then use this code  as the t

## 語法

```python
system.db.beginTransaction(database, isolationLevel, timeout)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| database | String | The name of the database connection to create a transaction in. |
| isolationLevel | Integer | The transaction isolation level to use. Use one of the four constants:system.db.READ_COMMITTEDsystem.db.READ_UNCOMMITTEDsystem.db.REPEATABLE_READsystem.db.SERIALIZABLE |
| timeout | Long | The amount of time, in milliseconds, that this connection is allowed to remain open without being used. Timeout counter is reset any time a query or call is executed against the transaction, or when committed or rolled-back. |
| database | String | The name of the database connection to create a transaction in. Use "" for the project's default connection. |
| isolationLevel | Integer/Constant | The transaction isolation level to use. Use one of the four constants:system.db.READ_COMMITTEDsystem.db.READ_UNCOMMITTEDsystem.db.REPEATABLE_READsystem.db.SERIALIZABLE |
| timeout | Long | The amount of time, in milliseconds, that this connection is allowed to remain open without being used. Timeout counter is reset any time a query or call is executed against the transaction, or when committed or rolled-back. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.db.beginTransaction(database, isolationLevel, timeout)
```

### Example 3

```python
isolationLevel
```


---



---

# system.db.clearAllNamedQueryCaches

**版本：** 8.1
**型別：** Scripting
**分類：** Db

## 詳述

This function is used inPython Scripting. This clears the caches of all Named Queries in a project. If called from the shared scope (i.e., Tag Event Scripts, Alarm Pipelines, etc.), then the name of the project must be passed as a parameter. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.db.clearAllNamedQueryCaches()
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| project | String | The Project that contains the named query whose cache needs to be cleared. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.db.clearAllNamedQueryCaches()
```

### Example 2

```python
system.db.clearAllNamedQueryCaches()
```


---



---

# system.db.clearNamedQueryCache

**版本：** 8.1
**型別：** Scripting
**分類：** Db

## 詳述

This function is used inPython Scripting. This clears the cache of a Named Query. If called from the shared scope (i.e., Tag Event Scripts, Alarm Pipelines, etc.) then the name of the project must be passed as a parameter. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.db.clearNamedQueryCache(path)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| path | String | The Path to the named query we want to clear the cache of. |
| project | String | The Project that contains the named query whose cache needs to be cleared. |
| path | String | The Path to the named query we want to clear the cache of. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.db.clearNamedQueryCache(path)
```

### Example 3

```python
system.db.clearNamedQueryCache(project, path)
```


---



---

# system.db.closeTransaction

**版本：** 8.1
**型別：** Scripting
**分類：** Db

## 詳述

This function is used inPython Scripting. Closes the transaction with the given ID. You must commit or rollback the transaction before you close it. Closing the transaction will return its database connection to the pool. The transaction ID will no longer be valid. This scripting function hasClient Permissionrestrictions.

## 語法

```python
system.db.closeTransaction(tx)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| tx | String | The transaction ID. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.db.closeTransaction(tx)
```

### Example 3

```python
# This example starts a transaction with a 5 second timeout against the project's default database, using the default isolation level. Then it executes a series of update calls,
# and commits and closes the transaction.

txId = system.db.beginTransaction(timeout=5000)
status=2

for machineId in range(8):
   system.db.runPrepUpdate("UPDATE MachineStatus SET status=? WHERE ID=?",
      args=[status, machineId], tx=txId)

system.db.commitTransaction(txId)
system.db.closeTransaction(txId)
```


---



---

# system.db.commitTransaction

**版本：** 8.1
**型別：** Scripting
**分類：** Db

## 詳述

This function is used inPython Scripting. Performs a commit for the given transaction. This will make all statements executed against the transaction since its beginning or since the last commit or rollback take effect in the database. Until you commit a transaction, any changes that the transaction makes will not be visible to other connections. If you are done with the transaction, you must close it after you commit it.

## 語法

```python
system.db.commitTransaction(tx)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| tx | String | The transaction ID. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.db.commitTransaction(tx)
```

### Example 3

```python
# This example starts a transaction with a 5 second timeout against the project's default database, using the default isolation level. Then it executes a series of update calls,
# and commits and closes the transaction.

txId = system.db.beginTransaction(timeout=5000)
status=2

for machineId in range(8):
   system.db.runPrepUpdate("UPDATE MachineStatus SET status=? WHERE ID=?",
      args=[status, machineId], tx=txId)

system.db.commitTransaction(txId)
system.db.closeTransaction(txId)
```


---



---

# system.db.createSProcCall

**版本：** 8.1
**型別：** Scripting
**分類：** Db

## 詳述

This function is used inPython Scripting. Creates an SProcCall object, which is a stored procedure call context. This is an object that is used to configure a call to a stored procedure. Once configured, you'd use system.db.execSProcCall to call the stored procedure. The call context object then holds any results from the stored procedure. The SProcCall object has the following functions used for registering parameters: These functions are used to register any in/out parameters for the stored pr

## 語法

```python
SPRocCall.registerInParam(index OR name, typeCode, value)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| procedureName | String | The named of the stored procedure to call. |
| database | String | The name of the database connection to execute against. |
| tx | String | A transaction identifier. If omitted, the call will be executed in its own transaction. |
| skipAudit | Boolean | A flag which, if set to true, will cause the procedure call to skip the audit system. Useful for some queries that have fields which won't fit into the audit log. |
| procedureName | String | The named of the stored procedure to call. |
| database | String | The name of the database connection to execute against. If omitted or "", the project's default database connection will be used. [optional] |
| tx | String | A transaction identifier. If omitted, the call will be executed in its own transaction. [optional] |
| skipAudit | Boolean | A flag which, if set to true, will cause the procedure call to skip the audit system. Useful for some queries that have fields which won't fit into the audit log. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
SPRocCall.registerInParam(index OR name, typeCode, value)
```

### Example 2

```python
SPRocCall.registerOutParam(index OR name, typeCode)
```

### Example 3

```python
SPRocCall.registerReturnParam(typeCode)
```


---



---

# system.db.dateFormat

**版本：** 8.1
**型別：** Scripting
**分類：** Db

## 詳述

This function is used inPython Scripting. This function is used to format dates nicely as strings. It uses a format string to guide its formatting behavior. Learn more about date formatting inDates. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.db.dateFormat(date, formatPattern)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| date | Date | The Date object that you'd like to format |
| formatPattern | String | A format pattern string to apply. Refer toData Type Formatting Referencefor a table of acceptable symbols. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.db.dateFormat(date, formatPattern)
```

### Example 3

```python
formatPattern
```


---



---

# system.db.execSProcCall

**版本：** 8.1
**型別：** Scripting
**分類：** Db

## 詳述

This function is used inPython Scripting. Executes a stored procedure call. The one parameter to this function is an SProcCall - a stored procedure call context. See the description ofsystem.db.createSProcCallfor more information and examples.

## 語法

```python
system.db.execSProcCall(callContext)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| callContext | SProcCall | A stored procedure call context, with any input, output, and/or return value parameters correctly configured. Usesystem.db.createSProcCallto create a call context. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.db.execSProcCall(callContext)
```

### Example 2

```python
callContext
```


---



---

# system.db.getConnectionInfo

**版本：** 8.1
**型別：** Scripting
**分類：** Db

## 詳述

This function is used inPython Scripting. Returns a dataset of information about a single database connection, as specified by the name argument. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.db.getConnectionInfo(name)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| name | String | The name of the database connection to find information about. Will use the current project's default database connection if a name is not specified. |
| Returns the name of this datasource. | Name |  |
| Returns the description for this datasource. | Description |  |
| Returns the database connection type. Example types include PostgreSQL, MSSQL, and Oracle. | DBType |  |
| Returns the status of this datasource based on its last tested condition. Typical values include Valid, Faulted, and Reconnecting. | Status |  |
| Returns a string describing the current problem, if the status is not good. | Problem |  |
| Returns the "best" status of this datasource or of any failover datasources. | ExtStatus |  |
| Returns number of queries per second, including Insert and Select queries. Throughput will be -1 if idle. | Throughput |  |
| Returns the current number of connections in use. | ActiveConnections |  |
| Returns the maximum number of connections the underlying pool is configured to use. | MaxConnections |  |
| Returns a SQL query that will be used to validate the status of this datasource. This query should always return at least 1 row. | ValidationQuery |  |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.db.getConnectionInfo(name)
```

### Example 3

```python
# This example checks the database connection type and selects a query format that matches.

connectionInfo = system.db.getConnectionInfo()
dbType = connectionInfo.getValueAt(0, "DBType")
if dbType == "MYSQL":
    # mysql format for a column with a space in the name
    query = "SELECT `amps value` FROM pumps"
else:
    # mssql format for a column with a space in the name
    query = "SELECT [amps value] FROM pumps"
```


---



---

# system.db.getConnections

**版本：** 8.1
**型別：** Scripting
**分類：** Db

## 詳述

This function is used inPython Scripting. Returns a dataset of information about each configured database connection. Each row represents a single connection. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.db.getConnections()
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| Returns the name of this datasource. | Name |  |
| Returns the description for this datasource. | Description |  |
| Returns the database connection type. Example types include PostgreSQL, MSSQL, and Oracle. | DBType |  |
| Returns the status of this datasource based on its last tested condition. Typical values include Valid, Faulted, and Reconnecting. | Status |  |
| Returns a string describing the current problem, if the status is not good. | Problem |  |
| Returns the "best" status of this datasource or of any failover datasources. | ExtStatus |  |
| Returns number of queries per second, including Insert and Select queries. Throughput will be -1 if idle. | Throughput |  |
| Returns the current number of connections in use. | ActiveConnections |  |
| Returns the maximum number of connections the underlying pool is configured to use. | MaxConnections |  |
| Returns a SQL query that will be used to validate the status of this datasource. This query should always return at least 1 row. | ValidationQuery |  |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.db.getConnections()
```


---



---

# system.db.refresh

**版本：** 8.1
**型別：** Scripting
**分類：** Db

## 詳述

This function is used inPython Scripting. This function will cause a Vision component binding to execute immediately. This is most often used for bindings that are set to  Polling - Off.  In this way, you cause a binding to execute on demand, when you know that the results of its query will return a new result. To use it, you simply specify the component and name of the property on whose binding you'd like to refresh. Even though the function includes "db" in the name, the function can update al

## 語法

```python
system.db.refresh(component, propertyName)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| component | JComponent | The component whose property you want to refresh. |
| propertyName | String | The name of the property that has a SQL Query binding that needs to be refreshed. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.db.refresh(component, propertyName)
```

### Example 3

```python
propertyName
```


---



---

# system.db.removeDatasource

**版本：** 8.1
**型別：** Scripting
**分類：** Db

## 詳述

This function is used inPython Scripting. Removes a database connection from Ignition. Permission Type: Datasource Management

## 語法

```python
system.db.removeDatasource(name)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| name | String | The name of the database connection in Ignition. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.db.removeDatasource(name)
```

### Example 3

```python
# This results in the connection named MySQL being removed.
system.db.removeDatasource("MySQL")
```


---



---

# system.db.rollbackTransaction

**版本：** 8.1
**型別：** Scripting
**分類：** Db

## 詳述

This function is used inPython Scripting. Performs a rollback on the given connection. This will make all statements executed against this transaction since its beginning or since the last commit or rollback undone. If you are done with the transaction, you must also close it after you do a rollback on it.

## 語法

```python
system.db.rollbackTransaction(tx)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| tx | String | The transaction ID. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.db.rollbackTransaction(tx)
```

### Example 3

```python
# This example uses a for-loop to run multiple queries in a single Transaction, and rollback if an error occurs.

# Create some variables for use later.
txId = system.db.beginTransaction(timeout=5000)
status=2
query = "UPDATE MachineStatus SET status=? WHERE ID=?"
errors = False  # A flag to denote if we ran into a problem with a query during the transaction.

for machineId in range(8):
    try:
        system.db.runPrepUpdate(query,  args=[status, machineId], tx=txId)
    except:
        errors = True
        break
# If we encountered an error...
if errors:
    # ...then rollback the transaction
    system.db.rollbackTransaction(txId)
else:
    # Otherwise, commit it.
    system.db.commitTransaction(txId)
# In either case, close the transaction when we're done.
system.db.closeTransaction(txId)
```


---



---

# system.db.runNamedQuery

**版本：** 8.1
**型別：** Scripting
**分類：** Db

## 詳述

This function is used inPython Scripting. Runs a Named Query and returns the results. Note that the number of parameters in the function is determined by scope. Both versions of the function are listed below. This function acceptskeyword arguments.

## 語法

```python
system.db.runNamedQuery(path, [parameters], [tx], [getKey])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| path | String | The path to the named query to run. Note that this is the full path to the query, including any folders. |
| parameters | Dictionary[String, Any] | A Python dictionary of parameters for the Named Query to use. [optional] |
| tx | String | An transaction ID, obtained frombeginNamedQueryTransaction. If blank, will not be part of a transaction. [optional] |
| getKey | Boolean | Only used for Update Query types. A flag indicating whether or not the result should be the number of rows affected (getKey=0) or the newly generated key value that was created as a result of the update (getKey=1). Not all databases support automatic retrieval of generated keys. [optional] |
| project | String | The project name the query exists in. |
| path | String | The path to the Named Query to run. Note that this is the full path to the query, including any folders. |
| parameters | Dictionary[String, Any] | A Python dictionary of parameters for the Named Query to use. [optional] |
| tx | String | An optional transaction ID, obtained frombeginNamedQueryTransaction. If blank, will not be part of a transaction. [optional] |
| getKey | Boolean | Only used for Update Query types. A flag indicating whether or not the result should be the number of rows affected (getKey=0) or the newly generated key value that was created as a result of the update (getKey=1). Not all databases support automatic retrieval of generated keys. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.db.runNamedQuery(path, [parameters], [tx], [getKey])
```


---



---

# system.db.runPrepQuery

**版本：** 8.1
**型別：** Scripting
**分類：** Db

## 詳述

This function is used inPython Scripting. Runs a  prepared statement  against the database, returning the results in a PyDataSet. Prepared statements differ from regular queries in that they can use a special placeholder, the question-mark character (?), in the query where any dynamic arguments would go, and then use an array of values to provide real information for those arguments. Make sure that the length of your argument array matches the number of question-mark placeholders in your query. 

## 語法

```python
system.db.runPrepQuery(query, args, database, [tx])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| query | String | A query (typically a SELECT) to run as a prepared statement with placeholders (?) denoting where the arguments go. |
| args | Object[] | A list of arguments. Will be used in order to match each placeholder (?) found in the query. |
| database | String | The name of the database connection to execute against. |
| tx | String | A transaction identifier. If omitted, the query will be executed in its own transaction. [optional] |
| query | String | A query (typically a SELECT) to run as a prepared statement with placeholders (?) denoting where the arguments go. |
| args | Object[] | A list of arguments. Will be used in order to match each placeholder (?) found in the query. |
| database | String | The name of the database connection to execute against. If omitted or "", the project's default database connection will be used. [optional] |
| tx | String | A transaction identifier. If omitted, the query will be executed in its own transaction. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.db.runPrepQuery(query, args, database, [tx])
```


---



---

# system.db.runPrepUpdate

**版本：** 8.1
**型別：** Scripting
**分類：** Db

## 詳述

This function is used inPython Scripting. Runs a prepared statement against the database, returning the number of rows that were affected. Prepared statements differ from regular queries in that they can use a special placeholder, the question-mark character (?), in the query where any dynamic arguments would go, and then use an array of values to provide real information for those arguments. Make sure that the length of your argument array matches the number of question-mark placeholders in you

## 語法

```python
system.db.runPrepUpdate( query, args, database, [tx], [getKey], [skipAudit])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| query | String | A query (typically an UPDATE, INSERT, or DELETE) to run as a prepared statement with placeholders (?) denoting where the arguments go. |
| args | Object[] | A list of arguments. Will be used in order to match each placeholder (?) found in the query. |
| database | String | The name of the database connection to execute against. |
| tx | String | Optional, A transaction identifier. If omitted, the update will be executed in its own transaction. [optional] |
| getKey | Boolean | Optional, A flag indicating whether or not the result should be the number of rows returned (getKey=0) or the newly generated key value that was created as a result of the update (getKey=1). Not all databases support automatic retrieval of generated keys. [optional] |
| skipAudit | Boolean | Optional, A flag which, if set to true, will cause the prep update to skip the audit system. Useful for some queries that have fields which won't fit into the audit log. [optional] |
| query | String | A query (typically an UPDATE, INSERT, or DELETE) to run as a prepared statement with placeholders (?) denoting where the arguments go. |
| args | Object[] | A list of arguments. Will be used in order to match each placeholder (?) found in the query. |
| database | String | Optional, The name of the database connection to execute against. If omitted or "", the project's default database connection will be used. [optional] |
| tx | String | Optional, A transaction identifier. If omitted, the update will be executed in its own transaction. [optional] |
| getKey | Boolean | Optional, A flag indicating whether or not the result should be the number of rows returned (getKey=0) or the newly generated key value that was created as a result of the update (getKey=1). Not all databases support automatic retrieval of generated keys. [optional] |
| skipAudit | Boolean | Optional, A flag which, if set to true, will cause the prep update to skip the audit system. Useful for some queries that have fields which won't fit into the audit log. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.db.runPrepUpdate( query, args, database, [tx], [getKey], [skipAudit])
```


---



---

# system.db.runQuery

**版本：** 8.1
**型別：** Scripting
**分類：** Db

## 詳述

This function is used inPython Scripting. Runs a SQL query, usually a SELECT query, against a database, returning the results as a dataset. If no database is specified, or the database is the empty-string "", then the current project's default database connection will be used. The results are returned as a PyDataSet, which is a wrapper around the standard dataset that is convenient for scripting. Permission Type: Legacy Database Access

## 語法

```python
system.db.runQuery(query, database, [tx])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| query | String | A SQL query, usually a SELECT query, to run. |
| database | String | The name of the database connection to execute against. |
| tx | String | A transaction identifier. If omitted, the query will be executed in its own transaction. [optional] |
| query | String | A SQL query, usually a SELECT query, to run. |
| database | String | The name of the database connection to execute against. If omitted or "", the project's default database connection will be used. [optional] |
| tx | String | A transaction identifier. If omitted, the query will be executed in its own transaction. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.db.runQuery(query, database, [tx])
```


---



---

# system.db.runSFPrepUpdate

**版本：** 8.1
**型別：** Scripting
**分類：** Db

## 詳述

This function is used inPython Scripting. Runs a prepared statement query through theStore and Forwardsystem and to multiple datasources at the same time. Prepared statements differ from regular queries in that they can use a special placeholder, the question-mark character (?) in the query where any dynamic arguments would go, and then use an array of values to provide real information for those arguments. Make sure that the length of your argument array matches the number of question-mark plac

## 語法

```python
system.db.runSFPrepUpdate(query, args, datasources)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| query | String | A query (typically an UPDATE, INSERT, or DELETE) to run as a prepared statement, with placeholders (?) denoting where the arguments go. |
| args | Object[] | A list of arguments. Will be used in order to match each placeholder (?) found in the query. |
| datasources | String[] | List of datasources to run the query through. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.db.runSFPrepUpdate(query, args, datasources)
```


---



---

# system.db.runSFUpdateQuery

**版本：** 8.1
**型別：** Scripting
**分類：** Db

## 詳述

This function is used inPython Scripting. Runs a query through theStore and Forwardsystem and to multiple datasources at the same time. Permission Type: Legacy Database Access

## 語法

```python
system.db.runSFUpdateQuery(query, datasources)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| query | String | A query (typically an UPDATE, INSERT, or DELETE) to run. |
| datasources | String[] | List of datasources to run the query through. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.db.runSFUpdateQuery(query, datasources)
```

### Example 3

```python
datasources
```


---



---

# system.db.runScalarPrepQuery

**版本：** 8.1
**型別：** Scripting
**分類：** Db

## 詳述

This function is used inPython Scripting. Runs a prepared statement against a database connection just like the runPrepQuery function, but only returns the value from the first row and column. If no results are returned from the query, the special value None is returned. Permission Type: Legacy Database Access

## 語法

```python
system.db.runScalarPrepQuery(query, args, database, [tx])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| query | String | A SQL query (typically a SELECT) to run as a prepared statement with placeholders (?) denoting where the arguments go, that should be designed to return one row and one column. |
| args | List[Any] | A list of arguments. Will be used in order to match each placeholder (?) found in the query. |
| database | String | The name of the database connection to execute against. |
| tx | String | A transaction identifier. If omitted, the query will be executed in its own transaction. [optional] |
| query | String | A SQL query (typically a SELECT) to run as a prepared statement with placeholders (?) denoting where the arguments go, that should be designed to return one row and one column. |
| args | List[Any] | A list of arguments. Will be used in order to match each placeholder (?) found in the query. |
| database | String | The name of the database connection to execute against. If omitted or "", the project's default database connection will be used. [optional] |
| tx | String | A transaction identifier. If omitted, the query will be executed in its own transaction. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.db.runScalarPrepQuery(query, args, database, [tx])
```


---



---

# system.db.runScalarQuery

**版本：** 8.1
**型別：** Scripting
**分類：** Db

## 詳述

This function is used inPython Scripting. Runs a query against a database connection just like the runQuery function, but only returns the value from the first row and column.  If no results are returned from the query, the special value None is returned. Permission Type: Legacy Database Access

## 語法

```python
system.db.runScalarQuery(query, database, [tx])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| query | String | A SQL query that should be designed to return one row and one column. |
| database | String | The name of the database connection to execute against. |
| tx | String | A transaction identifier. If omitted, the query will be executed in its own transaction. [optional] |
| query | String | A SQL query that should be designed to return one row and one column. |
| database | String | The name of the database connection to execute against. If omitted or "", the project's default database connection will be used. [optional] |
| tx | String | A transaction identifier. If omitted, the query will be executed in its own transaction. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.db.runScalarQuery(query, database, [tx])
```


---



---

# system.db.runUpdateQuery

**版本：** 8.1
**型別：** Scripting
**分類：** Db

## 詳述

This function is used inPython Scripting. Runs a query against a database connection, returning the number of rows affected. Typically this is an UPDATE, INSERT, or DELETE query. If no database is specified, or the database is the empty-string "", then the current project's default database connection will be used. You may want to use the runPrepUpdate query if your query is constructed with user input (to avoid the user's input from breaking your syntax) or if you need to insert binary or BLOB 

## 語法

```python
system.db.runUpdateQuery(query, database, [tx], [getKey], [skipAudit])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| query | String | A SQL query, usually an INSERT, UPDATE, or DELETE query, to run. |
| database | String | The name of the database connection to execute against. |
| tx | String | A transaction identifier. If omitted, the update will be executed in its own transaction. [optional] |
| getKey | Boolean | A flag indicating whether or not the result should be the number of rows returned (getKey=0) or the newly generated key value that was created as a result of the update (getKey=1). Not all databases support automatic retrieval of generated keys. [optional] |
| skipAudit | Boolean | A flag which, if set to true, will cause the update query to skip the audit system. Useful for some queries that have fields which won't fit into the audit log. [optional] |
| query | String | A SQL query, usually an INSERT, UPDATE, or DELETE query, to run. |
| database | String | The name of the database connection to execute against. If omitted or "", the project's default database connection will be used. [optional] |
| tx | String | A transaction identifier. If omitted, the update will be executed in its own transaction. [optional] |
| getKey | Boolean | A flag indicating whether or not the result should be the number of rows returned (getKey=0) or the newly generated key value that was created as a result of the update (getKey=1). Not all databases support automatic retrieval of generated keys. [optional] |
| skipAudit | Boolean | A flag which, if set to true, will cause the update query to skip the audit system. Useful for some queries that have fields which won't fit into the audit log. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.db.runUpdateQuery(query, database, [tx], [getKey], [skipAudit])
```


---



---

# system.db.setDatasourceConnectURL

**版本：** 8.1
**型別：** Scripting
**分類：** Db

## 詳述

This function is used inPython Scripting. Changes the connect URL for a given database connection. Permission Type: Datasource Management

## 語法

```python
system.db.setDatasourceConnectURL(name, connectUrl)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| name | String | The name of the database connection in Ignition. |
| connectUrl | String | The new connect URL. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.db.setDatasourceConnectURL(name, connectUrl)
```


---



---

# system.db.setDatasourceEnabled

**版本：** 8.1
**型別：** Scripting
**分類：** Db

## 詳述

This function is used inPython Scripting. Enables/disables a given database connection. Permission Type: Datasource Management

## 語法

```python
system.db.setDatasourceEnabled(name, enabled)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| name | String | The name of the database connection in Ignition. |
| enabled | Boolean | Enables/disables a given database connection. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.db.setDatasourceEnabled(name, enabled)
```


---



---

# system.db.setDatasourceMaxConnections

**版本：** 8.1
**型別：** Scripting
**分類：** Db

## 詳述

This function is used inPython Scripting. Sets theMax ActiveandMax Idleparameters of a given database connection. Permission Type: Datasource Management

## 語法

```python
system.db.setDatasourceMaxConnections(name, maxConnections)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| name | String | The name of the database connection in Ignition. |
| maxConnections | Integer | Sets theMax ActiveandMax Idleparameters of a given database connection. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.db.setDatasourceMaxConnections(name, maxConnections)
```

### Example 3

```python
maxConnections
```


---

