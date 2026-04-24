# Ignition 8.1 - 函數文檔


## 📑 目錄

---

1. [system.alarm.acknowledge](#systemalarmacknowledge) - This function is used inPython Scripting. Acknowledges any number of alarms, specified by their event ids. The event id is generated for an alarm when it becomes active, and it is used to identify a particular event from other events for the same source. The alarms will be acknowledged by the logged in user making the call. Additionally, acknowledgement notes may be included and will be stored along with the acknowledgement. This function uses different parameters based on the scope of the scrip
2. [system.alarm.cancel](#systemalarmcancel) - This function is used inPython Scripting. Cancels any number of alarm pipelines, specified by their event ids. Event ids can be obtains from thesystem.alarm.queryStatusfunction. Canceling a pipeline will not impact the alarm that triggered the pipeline. The alarm will still be active, but will drop out of alarm pipelines. Permission Type: Alarm Management
3. [system.alarm.createRoster](#systemalarmcreateroster) - This function is used inPython Scripting. This function creates a new roster. Users may be added to the roster through the Gateway or the Roster Management component Permission Type: Alarm Management
4. [system.alarm.getRosters](#systemalarmgetrosters) - This function is used inPython Scripting. This function returns a mapping of roster names to a list of usernames contained in the roster. This scripting function has noClient Permissionrestrictions.
5. [system.alarm.getShelvedPaths](#systemalarmgetshelvedpaths) - This function is used inPython Scripting. Returns a list of ShelvedPath objects, which each represent a shelved alarm. This scripting function has noClient Permissionrestrictions.
6. [system.alarm.listPipelines](#systemalarmlistpipelines) - This function is used inPython Scripting. Will return a list of the available Alarm Notification Pipelines in a project. The order of the returned list is not guaranteed. The legacy behavior of this function (7.9 and prior) did not have any parameters, and it would always check all projects for pipelines. Upon upgrade to version 8.#+, alarm pipelines were migrated to a project named "alarm-pipelines". See theUpgrade Guidefor more details.
7. [system.alarm.queryJournal](#systemalarmqueryjournal) - This function is used inPython Scripting. Queries the specified journal for historical alarm events. The result is a list of alarm events, which can be parsed for individual properties. Click herefor more information on alarm properties.
8. [system.alarm.queryStatus](#systemalarmquerystatus) - This function is used inPython Scripting. Queries the current state of alarms. The result is a list of alarm events, which can be parsed for individual properties. The results provided by this function represent the current state of alarms, in contrast to the historical alarm events retrieved by thesystem.alarm.queryJournalfunction. Depending on the number of alarm events in the system, this function can be fairly intensive and take a while to finish executing. This can be problematic if the app
9. [system.alarm.shelve](#systemalarmshelve) - This function is used inPython Scripting. This function shelves the specified alarms for the specified amount of time. The time can be specified in minutes (timeoutMinutes) or seconds (timeoutSeconds). If an alarm is already shelved, this will overwrite the remaining time. If no timeout is specified, will default to 15 minutes. Client Permission: Alarm Management
10. [system.alarm.unshelve](#systemalarmunshelve) - This function is used inPython Scripting. Unshelves a list of alarms based on the source paths provided. Client Permission: Alarm Management
11. [system.bacnet.readRaw](#systembacnetreadraw) - This function is used inPython Scripting. Read from any BACnet object not explicitly supported by the BACnet driver. To use this function, theBACnetdriver must be installed.
12. [system.bacnet.readRawMultiple](#systembacnetreadrawmultiple) - This function is used inPython Scripting. This function is the bulk version ofsystem.bacnet.readRawto allow multiple object/property combinations to be read simultaneously from a single request. Returns a list of corresponding Encodable objects provided equal-length lists of object types, object instance numbers, property IDs, and property array indices. To use this function, theBACnetdriver must be installed.
13. [system.bacnet.synchronizeTime](#systembacnetsynchronizetime) - This function is used inPython Scripting. Notifies the remote device of the correct current time, which is the system time (factoring in time zone and DST) of the server Ignition is running on. To use this function, theBACnetdriver must be installed.
14. [system.bacnet.synchronizeTimeUtc](#systembacnetsynchronizetimeutc) - This function is used inPython Scripting. Notifies the remote device of the correct current time in UTC. To use this function, theBACnetdriver must be installed.
15. [system.bacnet.writeRaw](#systembacnetwriteraw) - This function is used inPython Scripting. Write to any BACnet object not explicitly supported by the BACnet driver.
16. [system.bacnet.writeRawMultiple](#systembacnetwriterawmultiple) - This function is used inPython Scripting. This function is the bulk version ofsystem.bacnet.writeRawby writing properties to objects provided equal-length lists of object types, object instance numbers, property IDs, values, priorities, and property array indices. The system.bacnet.writeRawMultiple() function will accept Encodable values on the value parameter.
17. [system.bacnet.writeWithPriority](#systembacnetwritewithpriority) - This function is used inPython Scripting. Write to the Present_Value attribute of an object with a custom priority level. To use this function, theBACnetdriver must be installed.
18. [system.dataset.addColumn](#systemdatasetaddcolumn) - This function is used inPython Scripting. Takes adatasetand returns a new dataset with a new column added or inserted into it. If the columnIndex argument is omitted, the column will be appended to the end of the dataset. Datasets are immutable, which means they cannot be directly modified once created. Instead, this scripting function returns a new dataset with some modification applied, which must be assigned to a variable to be used. SeeAltering a Dataset.
19. [system.dataset.addRow](#systemdatasetaddrow) - This function is used inPython Scripting. Takes adatasetand returns a new dataset with a new row added or inserted into it. If the rowIndex argument is omitted, the row will be appended to the end of the dataset. Datasets are immutable, which means they cannot be directly modified once created. Instead, this scripting function returns a new dataset with some modification applied, which must be assigned to a variable to be used. SeeAltering a Dataset.
20. [system.dataset.addRows](#systemdatasetaddrows) - This function is used inPython Scripting. Takes adatasetand returns a new dataset with new rows added or inserted into it. If the rowIndex argument is omitted, the rows will be appended to the end of the dataset. Datasets are immutable, which means they cannot be directly modified once created. Instead, this scripting function returns a new dataset with some modification applied, which must be assigned to a variable to be used. SeeAltering a Dataset.
21. [system.dataset.appendDataset](#systemdatasetappenddataset) - This function is used inPython Scripting. Takes two different datasets and returns a newdatasetwith the second dataset appended to the first. Will throw an error if the number and types of columns do not match. This scripting function has noClient Permissionrestrictions.
22. [system.dataset.clearDataset](#systemdatasetcleardataset) - This function is used inPython Scripting. Takes adatasetand returns a new dataset with all of the same column names and types, but no rows. Datasets are immutable, which means they cannot be directly modified once created. Instead, this scripting function returns a new dataset with some modification applied, which must be assigned to a variable to be used. SeeAltering a Dataset.
23. [system.dataset.dataSetToHTML](#systemdatasetdatasettohtml) - This function is used inPython Scripting. Formats the contents of adatasetas an HTML page, returning the results as a string. Uses the<table>element to create a data table page. This scripting function has noClient Permissionrestrictions.
24. [system.dataset.deleteRow](#systemdatasetdeleterow) - This function is used inPython Scripting. Takes adatasetand returns a new dataset with the specified rowIndex removed. Datasets are immutable, which means they cannot be directly modified once created. Instead, this scripting function returns a new dataset with some modification applied, which must be assigned to a variable to be used. SeeAltering a Dataset.
25. [system.dataset.deleteRows](#systemdatasetdeleterows) - This function is used inPython Scripting. Takes adatasetand returns a new dataset with one or more rows removed. Datasets are immutable, which means they cannot be directly modified once created. Instead, this scripting function returns a new dataset with some modification applied, which must be assigned to a variable to be used. SeeAltering a Dataset.
26. [system.dataset.exportCSV](#systemdatasetexportcsv) - This function is used inPython Scripting. Exports the contents of adatasetas a CSV file, prompting the user to save the file to disk. To write silently to a file, you cannot use the dataset.export* functions. Instead, use thetoCSV()function. This scripting function has noClient Permissionrestrictions.
27. [system.dataset.exportExcel](#systemdatasetexportexcel) - This function is used inPython Scripting. Exports the contents of adatasetas an Excel spreadsheet, prompting the user to save the file to disk. Uses the same format as thesystem.dataset.toExcelfunction. To write silently to a file, you cannot use the dataset.export* functions. Instead, use the toExcel() function. This scripting function has noClient Permissionrestrictions.
28. [system.dataset.exportHTML](#systemdatasetexporthtml) - This function is used inPython Scripting. Exports the contents of adatasetto an HTML page. Prompts the user to save the file to disk. This scripting function has noClient Permissionrestrictions.
29. [system.dataset.filterColumns](#systemdatasetfiltercolumns) - This function is used inPython Scripting. Takes adatasetand returns a view of the dataset containing only the columns found within the given list of columns. Datasets are immutable, which means they cannot be directly modified once created. Instead, this scripting function returns a new dataset with some modification applied, which must be assigned to a variable to be used. SeeAltering a Dataset.
30. [system.dataset.formatDates](#systemdatasetformatdates) - This function is used inPython Scripting. Returns a newdatasetreplacing date typed columns with string typed columns. The new columns will match the formatting specified by the dateFormat parameter. This scripting function has noClient Permissionrestrictions.
31. [system.dataset.fromCSV](#systemdatasetfromcsv) - This function is used inPython Scripting. Converts adatasetstored in a CSV formatted string to a dataset that can be immediately assignable to a dataset property in your project.  Usually this is used in conjunction withsystem.file.readFileAsStringwhen reading in a CSV file that was exported usingsystem.dataset.toCSV.  The CSV string must be formatted in a specific way: The second line must list the names of the columns of the dataset separated by commas
32. [system.dataset.getColumnHeaders](#systemdatasetgetcolumnheaders) - This function is used inPython Scripting. Takes in adatasetand returns the headers as a Python list. This scripting function has noClient Permissionrestrictions.
33. [system.dataset.setValue](#systemdatasetsetvalue) - This function is used inPython Scripting. Takes adatasetand returns a new dataset with one value altered. Datasets are immutable, which means they cannot be directly modified once created. Instead, this scripting function returns a new dataset with some modification applied, which must be assigned to a variable to be used. SeeAltering a Dataset.
34. [system.dataset.sort](#systemdatasetsort) - This function is used inPython Scripting. Takes adatasetand returns a sorted version of the dataset. The sort order is determined by a single column. This works on numeric, as well as alphanumeric columns. When sorting alphanumerically, contiguous numbers are treated as a single number: you may recognize this as a "natural sort". Datasets are immutable, which means they cannot be directly modified once created. Instead, this scripting function returns a new dataset with some modification applied
35. [system.dataset.toCSV](#systemdatasettocsv) - This function is used inPython Scripting. Formats the contents of adatasetas CSV (comma separated values), returning the resulting CSV as a string. If the "forExport" flag is set, then the format will be appropriate for parsing using thesystem.dataset.fromCSVfunction. This scripting function has noClient Permissionrestrictions.
36. [system.dataset.toDataSet](#systemdatasettodataset) - This function is used inPython Scripting. This function is used to convert a PyDataset to a dataset. In addition it can also create new datasets from a raw Python list. When creating a new dataset, headers should have unique names. For more information on datasets and PyDatasets, see theDatasetspage. This scripting function has noClient Permissionrestrictions.
37. [system.dataset.toExcel](#systemdatasettoexcel) - This function is used inPython Scripting. Formats the contents of one or moredatasetsas an Excel spreadsheet, returning the results as a byte array. Each dataset specified will be added as a worksheet in the Excel workbook. This function replaces the deprecatedsystem.dataset.dataSetToExcelfunction.
38. [system.dataset.toPyDataSet](#systemdatasettopydataset) - This function is used inPython Scripting. This function converts from a normaldatasetto a PyDataset, which is a wrapper class which makes working with datasets more Python-esque. For more information on datasets and PyDatasets, see theDatasetspage. This scripting function has noClient Permissionrestrictions.
39. [system.dataset.updateRow](#systemdatasetupdaterow) - This function is used inPython Scripting. Takes adatasetand returns a new dataset with a one row altered. To alter the row, this function takes a Python dictionary to represent the changes to make to the specified row. The keys in the dictionary are used to find the columns to alter. Datasets are immutable, which means they cannot be directly modified once created. Instead, this scripting function returns a new dataset with some modification applied, which must be assigned to a variable to be us
40. [system.date.*Between](#systemdate*between) - This function is used inPython Scripting. This function is a set of functions that include: Order matters when passing in the two dates required by this function. system.date.*Between will subtract the first date from the second date, meaning if date 2 is further in time than date 1, then a positive amount of time has passed. If date 2 is backwards in time from date 1, then a negative amount of time has passed.
41. [system.date.add*](#systemdateadd*) - This function is used inPython Scripting. This function is a set of functions that include: This scripting function has noClient Permissionrestrictions.
42. [system.date.format](#systemdateformat) - This function is used inPython Scripting. Returns the given date as a string and formatted according to a pattern. The pattern is a format that is full of various placeholders that display different parts of the date. These are case-sensitive. These placeholders can be repeated for a different effect. For example, M will give you 1-12, MM will give you 01-12, MMM will give you Jan-Dec, MMMM will give you January-December. This scripting function has noClient Permissionrestrictions.
43. [system.date.fromMillis](#systemdatefrommillis) - This function is used inPython Scripting. Creates a date object given a millisecond value. This scripting function has noClient Permissionrestrictions.
44. [system.date.get*](#systemdateget*) - This function is used inPython Scripting. This function is a set of functions that include: This scripting function has noClient Permissionrestrictions.
45. [system.date.getDate](#systemdategetdate) - This function is used inPython Scripting. Creates a new Date object given a year, month and a day. The time will be set to midnight of that day. This scripting function has noClient Permissionrestrictions.
46. [system.date.getTimezone](#systemdategettimezone) - This function is used inPython Scripting. Returns the ID of the current timezone. If your Client and Gateway are in different time zones, the returned value will be dependent on where this script is run. IE: in a button on a client will return the Client time zone. On a Gateway script (including Perspective scripts), the function will return the Gateway time zone.
47. [system.date.getTimezoneOffset](#systemdategettimezoneoffset) - This function is used inPython Scripting. Returns the current timezone's offset versus UTC for a given instant, taking Daylight Savings Time into account. This scripting function has noClient Permissionrestrictions.
48. [system.date.getTimezoneRawOffset](#systemdategettimezonerawoffset) - This function is used inPython Scripting. Returns the current timezone offset versus UTC, not taking daylight savings into account. This scripting function has noClient Permissionrestrictions.
49. [system.date.isAfter](#systemdateisafter) - This function is used inPython Scripting. Compares two dates to see if date_1 is after date_2. This scripting function has noClient Permissionrestrictions.
50. [system.date.isBefore](#systemdateisbefore) - This function is used inPython Scripting. Compares two dates to see if date_1 is before date_2. This scripting function has noClient Permissionrestrictions.
51. [system.date.isBetween](#systemdateisbetween) - This function is used inPython Scripting. Compares two dates to see if a target date is between two other dates; checks to see if the target date is between the other two dates. This scripting function has noClient Permissionrestrictions.
52. [system.date.isDaylightTime](#systemdateisdaylighttime) - This function is used inPython Scripting. Checks to see if the current timezone is using daylight savings time during the date specified. This scripting function has noClient Permissionrestrictions.
53. [system.date.midnight](#systemdatemidnight) - This function is used inPython Scripting. Returns a copy of a date with the hour, minute, second, and millisecond fields set to zero. This scripting function has noClient Permissionrestrictions.
54. [system.date.now](#systemdatenow) - This function is used inPython Scripting. Returns a java.util.Date object that represents the current time according to the local system clock. This scripting function has noClient Permissionrestrictions.
55. [system.date.parse](#systemdateparse) - This function is used inPython Scripting. Attempts to parse a string and create a Date. Causes ParseException if the date dateString parameter is in an unrecognized format. This scripting function has noClient Permissionrestrictions.
56. [system.date.setTime](#systemdatesettime) - This function is used inPython Scripting. Takes in a date, and returns a copy of it with the time fields set as specified. This scripting function has noClient Permissionrestrictions.
57. [system.date.toMillis](#systemdatetomillis) - This function is used inPython Scripting. Converts a Date object to its millisecond value elapsed since January 1, 1970, 00:00:00 UTC (GMT) This scripting function has noClient Permissionrestrictions.
58. [system.db.addDatasource](#systemdbadddatasource) - This function is used inPython Scripting. Adds a new database connection in Ignition. Permission Type: Datasource Management
59. [system.db.beginNamedQueryTransaction](#systemdbbeginnamedquerytransaction) - This function is used inPython Scripting. Begins a new database transaction usingNamed Queries. Database transactions are used to execute multiple queries in an atomic fashion. After executing queries, you must either commit the transaction to have your changes take effect or rollback the transaction, which will make all operations since the last commit not take place. The transaction is given a new unique string code, which is then returned. You can then use this code as the tx argument for oth
60. [system.db.beginTransaction](#systemdbbegintransaction) - This function is used inPython Scripting. Begins a new database transaction for using run* and runPrep* queries. Database transactions are used to execute multiple queries in an atomic fashion. After executing queries, you must either commit the transaction to have your changes take effect, or rollback the transaction which will make all operations since the last commit not take place. The transaction is given a new unique string code, which is then returned. You can then use this code  as the t
61. [system.db.clearAllNamedQueryCaches](#systemdbclearallnamedquerycaches) - This function is used inPython Scripting. This clears the caches of all Named Queries in a project. If called from the shared scope (i.e., Tag Event Scripts, Alarm Pipelines, etc.), then the name of the project must be passed as a parameter. This scripting function has noClient Permissionrestrictions.
62. [system.db.clearNamedQueryCache](#systemdbclearnamedquerycache) - This function is used inPython Scripting. This clears the cache of a Named Query. If called from the shared scope (i.e., Tag Event Scripts, Alarm Pipelines, etc.) then the name of the project must be passed as a parameter. This scripting function has noClient Permissionrestrictions.
63. [system.db.closeTransaction](#systemdbclosetransaction) - This function is used inPython Scripting. Closes the transaction with the given ID. You must commit or rollback the transaction before you close it. Closing the transaction will return its database connection to the pool. The transaction ID will no longer be valid. This scripting function hasClient Permissionrestrictions.
64. [system.db.commitTransaction](#systemdbcommittransaction) - This function is used inPython Scripting. Performs a commit for the given transaction. This will make all statements executed against the transaction since its beginning or since the last commit or rollback take effect in the database. Until you commit a transaction, any changes that the transaction makes will not be visible to other connections. If you are done with the transaction, you must close it after you commit it.
65. [system.db.createSProcCall](#systemdbcreatesproccall) - This function is used inPython Scripting. Creates an SProcCall object, which is a stored procedure call context. This is an object that is used to configure a call to a stored procedure. Once configured, you'd use system.db.execSProcCall to call the stored procedure. The call context object then holds any results from the stored procedure. The SProcCall object has the following functions used for registering parameters: These functions are used to register any in/out parameters for the stored pr
66. [system.db.dateFormat](#systemdbdateformat) - This function is used inPython Scripting. This function is used to format dates nicely as strings. It uses a format string to guide its formatting behavior. Learn more about date formatting inDates. This scripting function has noClient Permissionrestrictions.
67. [system.db.execSProcCall](#systemdbexecsproccall) - This function is used inPython Scripting. Executes a stored procedure call. The one parameter to this function is an SProcCall - a stored procedure call context. See the description ofsystem.db.createSProcCallfor more information and examples.
68. [system.db.getConnectionInfo](#systemdbgetconnectioninfo) - This function is used inPython Scripting. Returns a dataset of information about a single database connection, as specified by the name argument. This scripting function has noClient Permissionrestrictions.
69. [system.db.getConnections](#systemdbgetconnections) - This function is used inPython Scripting. Returns a dataset of information about each configured database connection. Each row represents a single connection. This scripting function has noClient Permissionrestrictions.
70. [system.db.refresh](#systemdbrefresh) - This function is used inPython Scripting. This function will cause a Vision component binding to execute immediately. This is most often used for bindings that are set to  Polling - Off.  In this way, you cause a binding to execute on demand, when you know that the results of its query will return a new result. To use it, you simply specify the component and name of the property on whose binding you'd like to refresh. Even though the function includes "db" in the name, the function can update al
71. [system.db.removeDatasource](#systemdbremovedatasource) - This function is used inPython Scripting. Removes a database connection from Ignition. Permission Type: Datasource Management
72. [system.db.rollbackTransaction](#systemdbrollbacktransaction) - This function is used inPython Scripting. Performs a rollback on the given connection. This will make all statements executed against this transaction since its beginning or since the last commit or rollback undone. If you are done with the transaction, you must also close it after you do a rollback on it.
73. [system.db.runNamedQuery](#systemdbrunnamedquery) - This function is used inPython Scripting. Runs a Named Query and returns the results. Note that the number of parameters in the function is determined by scope. Both versions of the function are listed below. This function acceptskeyword arguments.
74. [system.db.runPrepQuery](#systemdbrunprepquery) - This function is used inPython Scripting. Runs a  prepared statement  against the database, returning the results in a PyDataSet. Prepared statements differ from regular queries in that they can use a special placeholder, the question-mark character (?), in the query where any dynamic arguments would go, and then use an array of values to provide real information for those arguments. Make sure that the length of your argument array matches the number of question-mark placeholders in your query. 
75. [system.db.runPrepUpdate](#systemdbrunprepupdate) - This function is used inPython Scripting. Runs a prepared statement against the database, returning the number of rows that were affected. Prepared statements differ from regular queries in that they can use a special placeholder, the question-mark character (?), in the query where any dynamic arguments would go, and then use an array of values to provide real information for those arguments. Make sure that the length of your argument array matches the number of question-mark placeholders in you
76. [system.db.runQuery](#systemdbrunquery) - This function is used inPython Scripting. Runs a SQL query, usually a SELECT query, against a database, returning the results as a dataset. If no database is specified, or the database is the empty-string "", then the current project's default database connection will be used. The results are returned as a PyDataSet, which is a wrapper around the standard dataset that is convenient for scripting. Permission Type: Legacy Database Access
77. [system.db.runSFPrepUpdate](#systemdbrunsfprepupdate) - This function is used inPython Scripting. Runs a prepared statement query through theStore and Forwardsystem and to multiple datasources at the same time. Prepared statements differ from regular queries in that they can use a special placeholder, the question-mark character (?) in the query where any dynamic arguments would go, and then use an array of values to provide real information for those arguments. Make sure that the length of your argument array matches the number of question-mark plac
78. [system.db.runSFUpdateQuery](#systemdbrunsfupdatequery) - This function is used inPython Scripting. Runs a query through theStore and Forwardsystem and to multiple datasources at the same time. Permission Type: Legacy Database Access
79. [system.db.runScalarPrepQuery](#systemdbrunscalarprepquery) - This function is used inPython Scripting. Runs a prepared statement against a database connection just like the runPrepQuery function, but only returns the value from the first row and column. If no results are returned from the query, the special value None is returned. Permission Type: Legacy Database Access
80. [system.db.runScalarQuery](#systemdbrunscalarquery) - This function is used inPython Scripting. Runs a query against a database connection just like the runQuery function, but only returns the value from the first row and column.  If no results are returned from the query, the special value None is returned. Permission Type: Legacy Database Access
81. [system.db.runUpdateQuery](#systemdbrunupdatequery) - This function is used inPython Scripting. Runs a query against a database connection, returning the number of rows affected. Typically this is an UPDATE, INSERT, or DELETE query. If no database is specified, or the database is the empty-string "", then the current project's default database connection will be used. You may want to use the runPrepUpdate query if your query is constructed with user input (to avoid the user's input from breaking your syntax) or if you need to insert binary or BLOB 
82. [system.db.setDatasourceConnectURL](#systemdbsetdatasourceconnecturl) - This function is used inPython Scripting. Changes the connect URL for a given database connection. Permission Type: Datasource Management
83. [system.db.setDatasourceEnabled](#systemdbsetdatasourceenabled) - This function is used inPython Scripting. Enables/disables a given database connection. Permission Type: Datasource Management
84. [system.db.setDatasourceMaxConnections](#systemdbsetdatasourcemaxconnections) - This function is used inPython Scripting. Sets theMax ActiveandMax Idleparameters of a given database connection. Permission Type: Datasource Management
85. [system.device.addDevice](#systemdeviceadddevice) - This function is used inPython Scripting. Adds a new device connection in Ignition. Accepts a dictionary of parameters to configure the connection. Acceptable parameters differ by device type: i.e., a Modbus/TCP connection requires a hostname and port, but a simulator doesn't require any parameters. When using this function, the argumentsMUSTbe passed in askeyword arguments.
86. [system.device.addDevice - deviceProps Listing](#systemdeviceadddevice---deviceprops-listing) - Below is a table of properties callable by system.device.addDevice. TheDescriptionandEnabledproperties may not be configured with this function, although a device connection could be disabled with a call to system.device.setDeviceEnabled() after creating the connection.
87. [system.device.getDeviceHostname](#systemdevicegetdevicehostname) - This function is used in Python Scripting. Returns the hostname of the device. This scripting function has noClient Permissionrestrictions.
88. [system.device.listDevices](#systemdevicelistdevices) - This function is used inPython Scripting. Returns a dataset of information about each configured device. Each row represents a single device. This scripting function has noClient Permissionrestrictions.
89. [system.device.refreshBrowse](#systemdevicerefreshbrowse) - This function is used inPython Scripting. Forces Ignition to browse the controller. Only works for Allen-Bradley controllers using legacy Allen-Bradley drivers, such as CompactLogix and ControlLogix. This scripting function has noClient Permissionrestrictions.
90. [system.device.removeDevice](#systemdeviceremovedevice) - This function is used inPython Scripting. Removes a given device from Ignition. Permission Type: Device Management
91. [system.device.restart](#systemdevicerestart) - This function is used inPython Scripting. Restarts the named device connection.
92. [system.device.setDeviceEnabled](#systemdevicesetdeviceenabled) - This function is used inPython Scripting. Enables/disables a device in Ignition. Permission Type: Device Management
93. [system.device.setDeviceHostname](#systemdevicesetdevicehostname) - This function is used inPython Scripting. Changes the hostname of a device. Used for all ethernet based drivers. Permission Type: Device Management
94. [system.dnp.demandPoll](#systemdnpdemandpoll) - The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Issues a poll request for one or more classes.
95. [system.dnp.directOperateAnalog](#systemdnpdirectoperateanalog) - The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Performs a Direct Operate command on an analog point.
96. [system.dnp.directOperateBinary](#systemdnpdirectoperatebinary) - The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Performs a Direct Operate command on a binary point.
97. [system.dnp.freezeAnalogs](#systemdnpfreezeanalogs) - The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Issues an Immediate Freeze command targeting one or more analog points.
98. [system.dnp.freezeAtTimeAnalogs](#systemdnpfreezeattimeanalogs) - The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Issues a Freeze at Time command targeting one or more analog points.
99. [system.dnp.freezeAtTimeCounters](#systemdnpfreezeattimecounters) - The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Issues a Freeze at Time command targeting one or more counters.
100. [system.dnp.freezeClearAnalogs](#systemdnpfreezeclearanalogs) - The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Issues a Freeze and Clear command targeting one or more analog points.
101. [system.dnp.freezeClearCounters](#systemdnpfreezeclearcounters) - The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Issues a Freeze and Clear command targeting one or more counters.
102. [system.dnp.freezeCounters](#systemdnpfreezecounters) - The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Issues an Immediate Freeze command targeting one or more counters.
103. [system.dnp.selectOperateAnalog](#systemdnpselectoperateanalog) - The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Performs a Select then Operate command on an analog point.
104. [system.dnp.selectOperateBinary](#systemdnpselectoperatebinary) - The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Performs a Select then Operate command on a binary point.
105. [system.dnp.synchronizeTime](#systemdnpsynchronizetime) - The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Issues a Synchronize Time command using the current Ignition Gateway time.
106. [system.dnp3.directOperateAnalog](#systemdnp3directoperateanalog) - The following function usessystem.dnp3and theLegacy DNP3 driver. Seesystem.dnpforDNP3functions using theDNP3 driver. This function is used inPython Scripting. Issues a Select-And-Operate command to set an analog value in an analog output point.
107. [system.dnp3.directOperateBinary](#systemdnp3directoperatebinary) - The following function usessystem.dnp3and theLegacy DNP3 driver. Seesystem.dnpforDNP3functions using theDNP3 driver. This function is used inPython Scripting. Issues a Direct-Operate command for digital control operations at binary output points (CROB).
108. [system.dnp3.freezeAnalogs](#systemdnp3freezeanalogs) - The following function usessystem.dnp3and theLegacy DNP3 driver. Seesystem.dnpforDNP3functions using theDNP3 driver. This function is used inPython Scripting. Issues a freeze command on the given analog outputs.
109. [system.dnp3.freezeAnalogsAtTime](#systemdnp3freezeanalogsattime) - The following function usessystem.dnp3and theLegacy DNP3 driver. Seesystem.dnpforDNP3functions using theDNP3 driver. This function is used inPython Scripting. Issues a freeze command on the given analog outputs at the given time for the specified duration.
110. [system.dnp3.freezeCounters](#systemdnp3freezecounters) - The following function usessystem.dnp3and theLegacy DNP3 driver. Seesystem.dnpforDNP3functions using theDNP3 driver. This function is used inPython Scripting. Issues a freeze command on the given counters.
111. [system.dnp3.freezeCountersAtTime](#systemdnp3freezecountersattime) - The following function usessystem.dnp3and theLegacy DNP3 driver. Seesystem.dnpforDNP3functions using theDNP3 driver. This function is used inPython Scripting. Issues a freeze command on the given counters at the given time for the specified duration.
112. [system.dnp3.selectOperateAnalog](#systemdnp3selectoperateanalog) - The following function usessystem.dnp3and theLegacy DNP3 driver. Seesystem.dnpforDNP3functions using theDNP3 driver. This function is used inPython Scripting. Issues a Select-And-Operate command to set an analog value in an analog output point.
113. [system.dnp3.selectOperateBinary](#systemdnp3selectoperatebinary) - The following function usessystem.dnp3and theLegacy DNP3 driver. Seesystem.dnpforDNP3functions using theDNP3 driver. This function is used inPython Scripting. Issues a Select-And-Operate command for digital control operations at binary output points (CROB).
114. [system.eam.getGroups](#systemeamgetgroups) - This function is used inPython Scripting. Returns the names of the defined agent organizational groups in the Gateway. This function can only be called from the Controller. This scripting function has noClient Permissionrestrictions.
115. [system.eam.queryAgentHistory](#systemeamqueryagenthistory) - This function is used inPython Scripting. Returns a list of the most recent agent events. This function can only be called from the Controller. This scripting function has noClient Permissionrestrictions.
116. [system.eam.queryAgentStatus](#systemeamqueryagentstatus) - This function is used inPython Scripting. Returns the current state of the matching agents. This function can only be called from the Controller. This scripting function has noClient Permissionrestrictions.
117. [system.eam.runTask](#systemeamruntask) - This function is used inPython Scripting. Takes the name of a task as an argument as a string (must be configured on the Controller before hand), attempts to execute the task. This function can only be called from the Controller. To run in the client, the user needs arole-based permission. This permission is disabled by default.
118. [system.file.fileExists](#systemfilefileexists) - This function is used inPython Scripting. Checks to see if a file or folder at a given path exists. This function is scoped for Perspective Sessions, but since all scripts in Perspective run on the Gateway, the file must be located on the Gateway's file system.
119. [system.file.getTempFile](#systemfilegettempfile) - This function is used inPython Scripting. Creates a new temp file on the host machine with a certain extension, returning the path to the file. The file is marked to be removed when the Java VM exits. This function is scoped for Perspective Sessions, but since all scripts in Perspective run on the Gateway, the file must be located on the Gateway's file system.
120. [system.file.openFile](#systemfileopenfile) - This function is used inPython Scripting. Shows an "Open File" dialog box, prompting the user to choose a file to open. Returns the path to the file that the user chose, or None if the user canceled the dialog box. An extension can optionally be passed in that sets the filetype filter to that extension. This scripting function has noClient Permissionrestrictions.
121. [system.file.openFiles](#systemfileopenfiles) - This function is used inPython Scripting. Shows an "Open File" dialog box, prompting the user to choose a file or files to open. Returns the paths to the files that the user chooses, or None if the user canceled the dialog box. An extension can optionally be passed in that sets the filetype filter to that extension. This scripting function has noClient Permissionrestrictions.
122. [system.file.readFileAsBytes](#systemfilereadfileasbytes) - This function is used inPython Scripting. Opens the file found at path filename, and reads the entire file. Returns the file as an array of bytes. Commonly this array of bytes is uploaded to a database table with a column of type BLOB (Binary Large OBject). This upload would be done through an INSERT or UPDATE SQL statement run through the system.db.runPrepUpdate function. You could also write the bytes to another file using the system.file.writeFile function, or send the bytes as an email attac
123. [system.file.readFileAsString](#systemfilereadfileasstring) - This function is used inPython Scripting. Opens the file found at path filename, and reads the entire file. Returns the file as a string. Common things to do with this string would be to load it into the text property of a component, upload it to a database table, or save it to another file using system.file.writeFile function. This function is scoped for Perspective Sessions, but since all scripts in Perspective run on the Gateway, the file must be located on the Gateway's file system.
124. [system.file.saveFile](#systemfilesavefile) - This function is used inPython Scripting. Prompts the user to save a new file named filename. The optional extension and typeDesc arguments will be used for a file type filter, if any. If the user accepts the save, the path to that file will be returned. If the user cancels the save, None will be returned. This scripting function has noClient Permissionrestrictions.
125. [system.file.writeFile](#systemfilewritefile) - This function is used inPython Scripting. Writes the given data to the file at file path filename. If the file exists, the append argument determines whether or not it is overwritten (the default) or appended to. The data argument can be either a string or an array of bytes (commonly retrieved from a BLOB in a database or read from another file using system.file.readFileAsBytes). This function is scoped for Perspective Sessions, but since all scripts in Perspective run on the Gateway, the file m
126. [system.groups.loadFromFile](#systemgroupsloadfromfile) - This function is used inPython Scripting. Loads a transaction group configuration from an xml export, into the specified project (creating the project if necessary). The mode parameter dictates how overwrites occur. This function is scoped for Perspective Sessions, but since all scripts in Perspective run on the Gateway, the file must be located on the Gateway's file system.
127. [system.groups.removeGroups](#systemgroupsremovegroups) - This function is used inPython Scripting. Removes the specified groups from the project. The group paths areFolder/Path/To/GroupName, separated by forward slashes. This scripting function has noClient Permissionrestrictions.
128. [system.gui.chooseColor](#systemguichoosecolor) - This function is used inPython Scripting. Prompts the user to pick a color using the default color-chooser dialog box. This scripting function has noClient Permissionrestrictions.
129. [system.gui.closeDesktop](#systemguiclosedesktop) - This function is used inPython Scripting. Allows you to close any of the open desktops associated with the current client. See theMulti-Monitor Clientspage for more details about using multiple monitors. This scripting function has noClient Permissionrestrictions.
130. [system.gui.color](#systemguicolor) - This function is used inPython Scripting. Creates a new color object, either by parsing a string or by having the RGB[A] channels specified explicitly. SeetoColorto see a list of available color names. This scripting function has noClient Permissionrestrictions.
131. [system.gui.confirm](#systemguiconfirm) - This function is used inPython Scripting. Displays a confirmation dialog box to the user with "Yes" and "No" options, and a custom message. This scripting function has noClient Permissionrestrictions.
132. [system.gui.convertPointToScreen](#systemguiconvertpointtoscreen) - This function is used inPython Scripting. Converts a pair of coordinates that are relative to the upper-left corner of a component to be relative to the upper-left corner of the entire screen. This scripting function has noClient Permissionrestrictions.
133. [system.gui.createPopupMenu](#systemguicreatepopupmenu) - This function is used inPython Scripting. Creates a new popup menu, which can then be shown over a component on a mouse event. To use this function, first create a Python sequence whose entries are strings, and another sequence whose entries are function objects. The strings will be the items that are displayed in your popup menu, and when an item is clicked, its corresponding function will be run. Your functions must accept an event object as an argument. See also:Functions. The function return
134. [system.gui.desktop](#systemguidesktop) - This function is used inPython Scripting. Allows for invoking system.gui functions on a specific desktop. See theMulti-Monitor Clientspage for more details.
135. [system.gui.errorBox](#systemguierrorbox) - This function is used inPython Scripting. Displays an error-style message box to the user. This scripting function has noClient Permissionrestrictions.
136. [system.gui.findWindow](#systemguifindwindow) - This function is used inPython Scripting. Finds and returns a list of windows with the given path. If the window is not open, an empty list will be returned. Useful for finding all instances of an open window that were opened withsystem.nav.openWindowInstance. This scripting function has noClient Permissionrestrictions.
137. [system.gui.getCurrentDesktop](#systemguigetcurrentdesktop) - This function is used inPython Scripting. Returns the handle of the desktop this function was called from. Commonly used with thesystem.gui.desktopandsystem.nav.desktopfunctions. This scripting function has noClient Permissionrestrictions.
138. [system.gui.getDesktopHandles](#systemguigetdesktophandles) - This function is used inPython Scripting. Gets a list of allsecondaryhandles of the open desktops associated with the current client. In this case,secondarymeans any desktop frame opened by the original client frame. For example, if the original client opened two new frames ('left client' and 'right client'), then this function would return ['left client', 'right client'].
139. [system.gui.getOpenedWindowNames](#systemguigetopenedwindownames) - This function is used inPython Scripting. Finds all of the currently open windows and returns a tuple of their paths. This scripting function has noClient Permissionrestrictions.
140. [system.gui.getOpenedWindows](#systemguigetopenedwindows) - This function is used inPython Scripting. Finds all of the currently open windows and returns a tuple of references to them. This scripting function has noClient Permissionrestrictions.
141. [system.gui.getParentWindow](#systemguigetparentwindow) - This function is used inPython Scripting. Finds the parent (enclosing) window for the component that fired an event and returns a reference to it. This scripting function has noClient Permissionrestrictions.
142. [system.gui.getQuality](#systemguigetquality) - This function is used inPython Scripting. Returns the data quality for the property of the given component as an integer. This function can be used to check the quality of a Tag binding on a component in the middle of the script so that alternative actions can be taken in the event of device disconnections. A description of the quality codes can be found on theQuality Codes and Overlayspage.
143. [system.gui.getScreenIndex](#systemguigetscreenindex) - This function is used inPython Scripting. Returns an integer value representing the current screen index based on the screen from which this function was called. This scripting function has noClient Permissionrestrictions.
144. [system.gui.getScreens](#systemguigetscreens) - This function is used inPython Scripting. Get a list of all the monitors on the computer this client is open on. Use withsystem.gui.setScreenIndex()to move the client. This scripting function has noClient Permissionrestrictions.
145. [system.gui.getSibling](#systemguigetsibling) - This function is used inPython Scripting. Given a component event object, looks up a sibling component. Shortcut forevent.source.parent.getComponent("siblingName"). If no such sibling is found, the special value None is returned. This scripting function has noClient Permissionrestrictions.
146. [system.gui.getWindow](#systemguigetwindow) - This function is used inPython Scripting. Finds a reference to an open window with the given name. Throws a ValueError if the named window is not open or not found. This scripting function has noClient Permissionrestrictions.
147. [system.gui.getWindowNames](#systemguigetwindownames) - This function is used inPython Scripting. Returns a list of the paths of all windows in the current project, sorted alphabetically. This scripting function has noClient Permissionrestrictions.
148. [system.gui.inputBox](#systemguiinputbox) - This function is used inPython Scripting. Opens up a popup input dialog box. This dialog box will show a prompt message and allow the user to type in a string. When the user is done, they can clickOKorCancel. If OK is pressed, this function will return with the value that they typed in. If Cancel is pressed, this function will return the value None. This scripting function has noClient Permissionrestrictions.
149. [system.gui.isTouchscreenModeEnabled](#systemguiistouchscreenmodeenabled) - This function is used inPython Scripting. Checks whether or not the running Client's Touch Screen mode is currently enabled. This scripting function has noClient Permissionrestrictions.
150. [system.gui.messageBox](#systemguimessagebox) - This function is used inPython Scripting. Displays an informational-style message popup box to the user. This scripting function has noClient Permissionrestrictions.
151. [system.gui.openDesktop](#systemguiopendesktop) - This function is used inPython Scripting. Creates an additional Desktop in a new frame. For more details, see theMulti-Monitor Clientspage. This function acceptskeyword arguments.
152. [system.gui.openDiagnostics](#systemguiopendiagnostics) - This function is used inPython Scripting. Opens the Client runtime Diagnostics window, which provides information regarding performance, logging, active threads, connection status, and the console. This provides an opportunity to open the Diagnostics window in situations where the menu bar in the client is hidden, and the keyboard shortcut (Ctrl+Shift+F7) can not be used. This scripting function has noClient Permissionrestrictions.
153. [system.gui.passwordBox](#systemguipasswordbox) - This function is used inPython Scripting. Pops up a special input box that uses a password field, so the text isn't echoed back in clear-text to the user. Returns the text they entered, or None if they canceled the dialog box. This scripting function has noClient Permissionrestrictions.
154. [system.gui.setScreenIndex](#systemguisetscreenindex) - This function is used inPython Scripting. Moves an open client to a specific monitor. Use withsystem.gui.getScreens()to identify monitors before moving. This scripting function has noClient Permissionrestrictions.
155. [system.gui.setTouchscreenModeEnabled](#systemguisettouchscreenmodeenabled) - This function is used inPython Scripting. Alters a running Client's Touch Screen mode on the fly. This scripting function has noClient Permissionrestrictions.
156. [system.gui.showNumericKeypad](#systemguishownumerickeypad) - This function is used inPython Scripting. Displays a modal on-screen numeric keypad, allowing for arbitrary numeric entry using the mouse, or a finger on a touch screen monitor. Returns the number that the user entered. This scripting function has noClient Permissionrestrictions.
157. [system.gui.showTouchscreenKeyboard](#systemguishowtouchscreenkeyboard) - This function is used inPython Scripting. Displays a modal on-screen keyboard, allowing for arbitrary text entry using the mouse, or a finger on a touchscreen monitor. Returns the text that the user entered. This scripting function has noClient Permissionrestrictions.
158. [system.gui.transform](#systemguitransform) - This function is used inPython Scripting. Sets a component's position and size at runtime.  Additional arguments for the duration, framesPerSecond, and acceleration of the operation exist for animation.  An optional callback argument will be executed when the transformation is complete. The transformation is performed in Designer coordinate space on components that are centered or have more than two anchors.
159. [system.gui.warningBox](#systemguiwarningbox) - This function is used inPython Scripting. Displays a message to the user in a warning style popup dialog. This scripting function has noClient Permissionrestrictions.
160. [system.iec61850.cancel](#systemiec61850cancel) - This function is used inPython Scripting. Cancels the selection of an SBO type control on a configured IEC 61850 device to prevent theoperatecommand from performing.
161. [system.iec61850.getControlParams](#systemiec61850getcontrolparams) - This function is used inPython Scripting. This function returns a list of report control names and their attributes contained in the configured IEC 61850 device.
162. [system.iec61850.listFiles](#systemiec61850listfiles) - This function is used inPython Scripting. This function returns a list of filenames from a remote path for the configured IEC 61850 device.
163. [system.iec61850.operate](#systemiec61850operate) - This function is used inPython Scripting. This function operates on the IEC 61850 device control immediately, such as to change the position of a switch. This can be done directly, or following a select command.
164. [system.iec61850.readFile](#systemiec61850readfile) - This function is used inPython Scripting. This function downloads remote files from the configured IEC 61850 device to an identified local path.
165. [system.iec61850.select](#systemiec61850select) - This function is used inPython Scripting. Select an SBO type control to prepare it for a subsequentoperatecommand for a configured IEC 61850 device. These selections can be removed by using thecancelfunction.
166. [system.iec61850.writeFile](#systemiec61850writefile) - This function is used inPython Scripting. This function uploads a file from a local path to the configured IEC 61850 device remote path.
167. [system.math.geometricMean](#systemmathgeometricmean) - This function is used inPython Scripting. Calculates the geometric mean. Geometric mean is a type of average which indicates a value in a set of numbers by using the product of values in the set and then taking the nth root, wherenis the number of values in the set. This is different than an arithmetic mean, which calculates an average based off the sum of the numbers, and divides it by n number of values. Geometric means can only be positive numbers. Returns NaN (Not a Number) if passed an empt
168. [system.math.kurtosis](#systemmathkurtosis) - This function is used inPython Scripting. Calculates the kurtosis of a sequence of values. Kurtosis measures if data is peaked or flat relative to normal distribution. A set of data with high kurtosis will have distinct peaks near the mean, while a set of data with low kurtosis will have a flat top near the mean. Uniform distribution is typically a flat line. Returns NaN (Not a Number) if passed an empty sequence measure of whether the data are heavy-tailed or light-tailed of a given distributio
169. [system.math.max](#systemmathmax) - This function is used inPython Scripting. Given a sequence of values, returns the greatest value in the sequence, also known as the "max" value. Returns NaN (Not a Number) if passed an empty sequence.
170. [system.math.mean](#systemmathmean) - This function is used inPython Scripting. Given a sequence of values, calculates the arithmetic mean (average). Returns NaN (Not a Number) if passed an empty sequence.
171. [system.math.meanDifference](#systemmathmeandifference) - This function is used inPython Scripting. Given two sequences of values, calculates the mean of the signed difference between both sequences. In other words, returns the absolute difference between the mean values of two different sets of data. Throws a DimensionMismatchException if the two sequences have different lengths.
172. [system.math.median](#systemmathmedian) - This function is used inPython Scripting. Takes a sequence of values, and returns the median. The median represents the middle value in a set of data. Returns NaN (Not a Number) if passed an empty sequence.
173. [system.math.min](#systemmathmin) - This function is used inPython Scripting. Given a sequence of numerical values, returns the minimum value, also known as the "min" value. Returns NaN (Not a Number) if passed an empty sequence.
174. [system.math.mode](#systemmathmode) - This function is used inPython Scripting. Given a sequence of values, returns the 'mode', or most frequent values. Returns an empty list if the sequence was empty or None.
175. [system.math.normalize](#systemmathnormalize) - This function is used inPython Scripting. Given a sequence of values, normalizes the values. Normalizing data refers to adjusting values measured on different scales and brings them into alignment to allow the comparison of corresponding normalized values. This creates uniformity of values by eliminating the different units of measurement, and to more easily compare data from different places. Returns an empty list if the sequence was empty or None.
176. [system.math.percentile](#systemmathpercentile) - This function is used inPython Scripting. Given a sequence of numerical values, estimates the percentile of input. The percentile is a value on a scale that represents a percentage position in a list of data that can be equal to or below that value: i.e., the 25th percentile is a value below which 25% of observable data points may be found.
177. [system.math.populationVariance](#systemmathpopulationvariance) - This function is used inPython Scripting. Given a sequence of values, returns the population variance. Population variance calculates how values in a dataset are spread out from their average value. Returns NaN (Not a Number) if passed an empty sequence.
178. [system.math.product](#systemmathproduct) - This function is used inPython Scripting. Given a sequence of values, calculates the product of the sequence: the result of multiplying of all values in the sequence together. Returns NaN (Not a Number) if passed an empty sequence.
179. [system.math.skewness](#systemmathskewness) - This function is used inPython Scripting. Given a sequence of values, calculates the skewness (third central moment). Skewness is a measure of the degree of asymmetry of a distribution of the mean. If skewed to the left, the distribution has a long tail in the negative direction. If skewed to the right, the tail will be skewed in the positive direction. Skewness values greater than 1 or less than -1 indicate a highly skewed distribution, while skewness values between 0.5 and 1 or -0.5 and -1 ind
180. [system.math.standardDeviation](#systemmathstandarddeviation) - This function is used inPython Scripting. Given a sequence of numerical values, calculates the simple standard deviation. Standard deviation is a calculated number for how close, or how far the values of that dataset are in relation to the mean. Returns NaN (Not a Number) if passed an empty sequence.
181. [system.math.sum](#systemmathsum) - This function is used inPython Scripting. Given a sequence of values, calculates the sum of all values. The sum is the number returned by addition. Returns NaN (Not a Number) if passed an empty sequence.
182. [system.math.sumDifference](#systemmathsumdifference) - This function is used inPython Scripting. Given two sequences of values, calculates the sum of each sequence and finds the difference between them. In other words, the difference between sums from two sets of numbers. Throws a DimensionMismatchException if the two sequences have different lengths.
183. [system.math.sumLog](#systemmathsumlog) - This function is used inPython Scripting. Given a sequence of values, calculates the sum of the natural logs (ln). Returns NaN (Not a Number) if passed an empty sequence.
184. [system.math.sumSquares](#systemmathsumsquares) - This function is used inPython Scripting. Given a sequence of values, calculates the sum of the squares of all values. Sum squares measures how far individual values are from the mean by calculating how much variation there is in a set of values. Returns NaN (Not a Number) if passed an empty sequence.
185. [system.math.variance](#systemmathvariance) - This function is used inPython Scripting. Given a sequence of values, calculates the variance of all values. Variance measures how far values in a set are spread out from their mean value. Returns NaN (Not a Number) if passed an empty sequence.
186. [system.mongodb.aggregate](#systemmongodbaggregate) - This function is used inPython Scripting. Project Library scripts will not provide hints for MongoDB system functions unless the Script Hint Scope is set toGateway. See theScripting in Ignitionpage for more details on scripting hints.
187. [system.mongodb.deleteMany](#systemmongodbdeletemany) - This function is used inPython Scripting. Project Library scripts will not provide hints for MongoDB system functions unless the Script Hint Scope is set toGateway. See theScripting in Ignitionpage for more details on scripting hints.
188. [system.mongodb.deleteOne](#systemmongodbdeleteone) - This function is used inPython Scripting. Project Library scripts will not provide hints for MongoDB system functions unless the Script Hint Scope is set toGateway. See theScripting in Ignitionpage for more details on scripting hints.
189. [system.mongodb.find](#systemmongodbfind) - This function is used inPython Scripting. Project Library scripts will not provide hints for MongoDB system functions unless the Script Hint Scope is set toGateway. See theScripting in Ignitionpage for more details on scripting hints.
190. [system.mongodb.findOne](#systemmongodbfindone) - This function is used inPython Scripting. Project Library scripts will not provide hints for MongoDB system functions unless the Script Hint Scope is set toGateway. See theScripting in Ignitionpage for more details on scripting hints.
191. [system.mongodb.insertMany](#systemmongodbinsertmany) - This function is used inPython Scripting. Project Library scripts will not provide hints for MongoDB system functions unless the Script Hint Scope is set toGateway. See theScripting in Ignitionpage for more details on scripting hints.
192. [system.mongodb.insertOne](#systemmongodbinsertone) - This function is used inPython Scripting. Project Library scripts will not provide hints for MongoDB system functions unless the Script Hint Scope is set toGateway. See theScripting in Ignitionpage for more details on scripting hints.
193. [system.mongodb.listCollectionNames](#systemmongodblistcollectionnames) - This function is used inPython Scripting. Project Library scripts will not provide hints for MongoDB system functions unless the Script Hint Scope is set toGateway. See theScripting in Ignitionpage for more details on scripting hints.
194. [system.mongodb.listConnectorInfo](#systemmongodblistconnectorinfo) - This function is used inPython Scripting. Project Library scripts will not provide hints for MongoDB system functions unless the Script Hint Scope is set toGateway. See theScripting in Ignitionpage for more details on scripting hints.
195. [system.mongodb.replaceOne](#systemmongodbreplaceone) - This function is used inPython Scripting. Project Library scripts will not provide hints for MongoDB system functions unless the Script Hint Scope is set toGateway. See theScripting in Ignitionpage for more details on scripting hints.
196. [system.mongodb.updateMany](#systemmongodbupdatemany) - This function is used inPython Scripting. Project Library scripts will not provide hints for MongoDB system functions unless the Script Hint Scope is set toGateway. See theScripting in Ignitionpage for more details on scripting hints.
197. [system.mongodb.updateOne](#systemmongodbupdateone) - This function is used inPython Scripting. Project Library scripts will not provide hints for MongoDB system functions unless the Script Hint Scope is set toGateway. See theScripting in Ignitionpage for more details on scripting hints.
198. [system.nav.centerWindow](#systemnavcenterwindow) - This function is used inPython Scripting. Given a window path, or a reference to a window itself, it will center the window. The window should be floating an non-maximized. If the window can't be found, this function will do nothing. This scripting function has noClient Permissionrestrictions.
199. [system.nav.closeParentWindow](#systemnavcloseparentwindow) - This function is used inPython Scripting. Closes the parent window given a component event object. This scripting function has noClient Permissionrestrictions.
200. [system.nav.closeWindow](#systemnavclosewindow) - This function is used inPython Scripting. Given a window path, or a reference to a window itself, it will close the window. If the window can't be found, this function will do nothing. This scripting function has noClient Permissionrestrictions.
201. [system.nav.desktop](#systemnavdesktop) - This function is used inPython Scripting. Allows for invokingsystem.navfunctions on a specific desktop. See theMulti-Monitor Clientspage for more details.
202. [system.nav.getCurrentWindow](#systemnavgetcurrentwindow) - This function is used inPython Scripting. Returns the path of the current "main screen" window, which is defined as the maximized window. With theTypical Navigation Strategy, there is only ever one maximized window at a time. This scripting function has noClient Permissionrestrictions.
203. [system.nav.goBack](#systemnavgoback) - This function is used inPython Scripting. When using theTypical Navigation Strategy, this function will navigate back to the previous main screen window. This scripting function has noClient Permissionrestrictions.
204. [system.nav.goForward](#systemnavgoforward) - This function is used inPython Scripting. When using thetypical navigation strategy, this function will navigate "forward" to the last main-screen window the user was on when they executed asystem.nav.goBack(). This scripting function has noClient Permissionrestrictions.
205. [system.nav.goHome](#systemnavgohome) - This function is used inPython Scripting. When using thetypical navigation strategy, this function will navigate to the "home" window. This is automatically detected as the first main-screen window shown in a project. If you are using this system function withsystem.nav.openWindow(), your home window should be closed before navigating to it, or system.nav.goHome() may not work. This scripting function has noClient Permissionrestrictions.
206. [system.nav.openWindow](#systemnavopenwindow) - This function is used inPython Scripting. Opens the window with the given path. If the window is already open, brings it to the front. The optional params dictionary contains key:valuepairs which will be used to set the target window's root container's dynamic variables. For instance, if the window that you are opening is namedTankDisplayand has a dynamic variable in its root container named "TankNumber", then callingsystem.nav.openWindow("TankDisplay", {"TankNumber" : 4})will open the TankDispl
207. [system.nav.openWindowInstance](#systemnavopenwindowinstance) - This function is used inPython Scripting. When called in a Vision Client, it operates exactly likesystem.nav.openWindow(), except that if the named window is already open, then an additional instance of the window will be opened. There is no limit to the number of additional instances of a window that you can open. When called in the Designer, it operates similar to system.nav.openWindow(), except that if the named window is already open the function will swap to the opened window. Additional in
208. [system.nav.swapTo](#systemnavswapto) - This function is used inPython Scripting. Performs a window swap from the current main screen window to the window specified. Swapping means that the opened window will take the place of the closing window - in this case it will be maximized. See also:Navigation Strategies. This function works likesystem.nav.swapWindow, except that you cannot specify the source for the swap.
209. [system.nav.swapWindow](#systemnavswapwindow) - This function is used inPython Scripting. Performs a window swap. This means that one window is closed, and another is opened and takes its place - assuming its size, floating state, and maximization state. This gives a seamless transition - one window seems to simply turn into another. This function works likesystem.nav.swapTo, except that you can specify the source and destination for the swap.
210. [system.net.getExternalIpAddress](#systemnetgetexternalipaddress) - This function is used inPython Scripting. Returns the Client's IP address, as it is detected by the Gateway. This means that this call will communicate with the Gateway, and the Gateway will tell the Client what IP address its incoming traffic is coming from. If you have a client behind a Network Address Translation (NAT) router, then this address will be the Wide Area Network (WAN) address of the router instead of the Local Area Network (LAN) address of the Client, which is what you'd get withs
211. [system.net.getHostName](#systemnetgethostname) - This function is used inPython Scripting. Returns the host name of the computer that the script was ran on. When run in the Gateway scope, returns the Gateway hostname. When run in the Client scope, returns the Client hostname. On Windows, this is typically the "computer name." For example, might return EAST_WING_WORKSTATION or bobs-laptop. This scripting function has noClient Permissionrestrictions.
212. [system.net.getIpAddress](#systemnetgetipaddress) - This function is used inPython Scripting. Returns the IP address of the computer that the script was ran on. When run in the Gateway scope, returns the Gateway IP address. When run in the Client scope, returns the Client IP address. This scripting function has noClient Permissionrestrictions.
213. [system.net.getRemoteServers](#systemnetgetremoteservers) - This function is used inPython Scripting. This function returns a list of Gateway Network servers that are visible from the local Gateway. This scripting function has noClient Permissionrestrictions.
214. [system.net.httpClient](#systemnethttpclient) - This function is used inPython Scripting. Provides a general use object that can be used to send and receive HTTP requests. The object created by this function is a wrapper around Java's HttpClient class. Usage requires creating aJythonHttpClientobject with a call tosystem.net.httpClient, then calling a method (such asget(),post()) on theJythonHttpClientto actually issue a request. To learn more about Java's HttpClient class, click the link corresponding to your version of Ignition:
215. [system.net.httpDelete](#systemnethttpdelete) - This function is used inPython Scripting. Performs an HTTP DELETE to the given URL. Keep in mind thatJRE proxy settingswill influence how these functions conduct their network activities.
216. [system.net.httpGet](#systemnethttpget) - This function is used inPython Scripting. Retrieves the document at the given URL using the HTTP GET protocol. The document is returned as a string. For example, if you use the URL of a website, you'll get the same thing you'd get by going to that website in a browser and using the browser's "View Source" function. Keep in mind thatJRE proxy settingswill influence how these functions conduct their network activities.
217. [system.net.httpPost](#systemnethttppost) - This function is used inPython Scripting. Retrieves the document at the given URL using the HTTP POST protocol. If a parameter dictionary argument is specified, the entries in the dictionary will encoded in "application/x-www-form-urlencoded" format, and then posted. You can post arbitrary data as well, but you'll need to specify the MIME type. The document is then returned as a string. Keep in mind thatJRE proxy settingswill influence how these functions conduct their network activities.
218. [system.net.httpPut](#systemnethttpput) - This function is used inPython Scripting. Performs an HTTP PUT to the given URL. Encodes the given dictionary of parameters using "applications/x-www-form-urlencoded" format. Keep in mind thatJRE proxy settingswill influence how these functions conduct their network activities.
219. [system.net.openURL](#systemnetopenurl) - This function is used inPython Scripting. Opens the given URL or URI scheme outside of the currently running Client in whatever application the host operating system deems appropriate. For example, the URL: will open in the default web browser, whereas this one:
220. [system.net.sendEmail](#systemnetsendemail) - This function is used inPython Scripting. Sends an email through the given SMTP server. Note that this email is relayed first through the Gateway; the Client host machine doesn't need network access to the SMTP server. Note that you can use this function to send emails as text messages. Most phone service providers offer a domain that can be used to convert emails into text messages. For example:1234567890@phone.domain.com. Contact your cell carrier for details.
221. [system.opc.browse](#systemopcbrowse) - This function is used inPython Scripting. Allows browsing of the OPC servers in the runtime, returning a list of tags. This function performs a fully recursive browse that can't be terminated, which can be especially problematic in larger systems. It is highly advised to usesystem.opc.browseServerinstead since recursion with that function is driven by subsequent calls.
222. [system.opc.browseServer](#systemopcbrowseserver) - This function is used inPython Scripting. When called from a Vision Client, Perspective Session, or the Designer, returns a list of OPCBrowseElement objects for the given server. Otherwise returns a list of PyOPCTagEx objects.
223. [system.opc.browseSimple](#systemopcbrowsesimple) - This function is used inPython Scripting. Allows browsing of OPC servers in the runtime returning a list of tags. browseSimple() takes mandatory parameters, which can be null, while browse() uses keyword-style arguments. The spelling on theopcServeranddeviceparameters must be exact. This function performs a fully recursive browse that can't be terminated, which can be especially problematic in larger systems. It is highly advised to usesystem.opc.browseServerinstead since recursion with that fun
224. [system.opc.getServerState](#systemopcgetserverstate) - This function is used inPython Scripting. Retrieves the current state of the given OPC server connection. If the given server is not found, the return value will be None. Otherwise, the return value will be one of these strings: This scripting function has noClient Permissionrestrictions.
225. [system.opc.getServers](#systemopcgetservers) - This function is used inPython Scripting. Returns a list of server names. This scripting function has noClient Permissionrestrictions.
226. [system.opc.isServerEnabled](#systemopcisserverenabled) - This function is used inPython Scripting. Checks if an OPC server connection is enabled or disabled. This scripting function has noClient Permissionrestrictions.
227. [system.opc.readValue](#systemopcreadvalue) - This function is used inPython Scripting. Reads a single value directly from an OPC server connection. The address is specified as a string, for example, [MyDevice]N11/N11:0The object returned from this function has three attributes: value, quality, and timestamp. The value attribute represents the current value for the address specified. The quality attribute is an OPC UA status code. You can easily check a good quality vs a bad quality by calling the isGood() function on the quality object. Th
228. [system.opc.readValues](#systemopcreadvalues) - This function is used inPython Scripting. This function is equivalent to the system.opc.readValue function, except that it can operate in bulk. You can specify a list of multiple addresses to read from, and you will receive a list of the same length, where each entry is the qualified value object for the corresponding address. This scripting function has noClient Permissionrestrictions.
229. [system.opc.setServerEnabled](#systemopcsetserverenabled) - This function is used inPython Scripting. Enables or disables an OPC server connection. Permission Type: OPC Server Management
230. [system.opc.writeValue](#systemopcwritevalue) - This function is used inPython Scripting. Writes a value directly through an OPC server connection synchronously. Will return an OPC UA status code object. You can quickly check if the write succeeded by calling isGood() on the return value from this function.
231. [system.opc.writeValues](#systemopcwritevalues) - This function is used inPython Scripting. This function is a bulk version ofsystem.opc.writeValue. It takes a list of addresses and a list of objects, which must be the same length. It will write the corresponding object to the corresponding address in bulk. It will return a list of status codes representing the individual write success or failure for each corresponding address. Permission Type: OPC Server Management
232. [system.opchda.browse](#systemopchdabrowse) - This function is used inPython Scripting. Performs a browse at the given root. This scripting function has noClient Permissionrestrictions.
233. [system.opchda.getAggregates](#systemopchdagetaggregates) - This function is used inPython Scripting. Will query the server for aggregates that it supports. This scripting function has noClient Permissionrestrictions.
234. [system.opchda.getAttributes](#systemopchdagetattributes) - This function is used inPython Scripting. Queries the given server for the item attributes that are available withsystem.opchda.readAttributes(). This scripting function has noClient Permissionrestrictions.
235. [system.opchda.getServers](#systemopchdagetservers) - This function is used inPython Scripting. Returns a list of the OPC-HDA servers configured on the system. This call will return all configured and enabled servers, including those that are not currently connected. This scripting function has noClient Permissionrestrictions.
236. [system.opchda.insert](#systemopchdainsert) - This function is used inPython Scripting. Insert values on the OPC-HDA server. Permission Type: OPC Server Management
237. [system.opchda.insertReplace](#systemopchdainsertreplace) - This function is used inPython Scripting. Will insert values on the OPC-HDA server, or replace them if they already exist. Permission Type: OPC Server Management
238. [system.opchda.isServerAvailable](#systemopchdaisserveravailable) - This function is used inPython Scripting. Checks to see if the specified OPC-HDA server is defined, enabled, and connected. This scripting function has noClient Permissionrestrictions.
239. [system.opchda.readAttributes](#systemopchdareadattributes) - This function is used inPython Scripting. Reads the specified attributes for the given item over a time range. Attributes and their IDs are defined in the OPC-HDA specification, and can be discovered by callingsystem.opchda.getAttributes(). This scripting function has noClient Permissionrestrictions.
240. [system.opchda.readProcessed](#systemopchdareadprocessed) - This function is used inPython Scripting. Reads processed values from the OPC-HDA server. Processed values are calculated values, based on the aggregate function requested for each item. The list of aggregates can be obtained by callingsystem.opchda.getAggregates(). This scripting function has noClient Permissionrestrictions.
241. [system.opchda.readRaw](#systemopchdareadraw) - This function is used inPython Scripting. Reads raw values from the OPC-HDA server. This scripting function has noClient Permissionrestrictions.
242. [system.opchda.replace](#systemopchdareplace) - This function is used inPython Scripting. Replaces values on the OPC-HDA server if the given item ID exists. Permission Type: OPC Server Management
243. [system.opcua.addConnection](#systemopcuaaddconnection) - This function is used inPython Scripting. Adds a new OPC UA connection.
244. [system.opcua.callMethod](#systemopcuacallmethod) - This function is used inPython Scripting. Calls a method in an OPC UA server. To make the most of this function, you'll need to be familiar with methods in theOPC UA server. This scripting function has noClient Permissionrestrictions.
245. [system.opcua.removeConnection](#systemopcuaremoveconnection) - This function is used inPython Scripting. Removes an OPC UA Connection.
246. [system.perspective.alterDock](#systemperspectivealterdock) - This function is used inPython Scripting. Changes configuration of a specified dock on a Perspective page.
247. [system.perspective.alterLogging](#systemperspectivealterlogging) - This function is used inPython Scripting. Changes Perspective Session logging attributes and levels. All parameters are optional, with the caveat that at least one of them needs to be used. For thesystem.perspective.alterLoggingfunction to work, the following line needs to be added to theignition.conffile, and the Gateway restarted.  "X" is the next number in the Java Additional Parameters list in theignition.conffile.Warning, this will open potential security holes in the Gateway, and is not ad
248. [system.perspective.authenticationChallenge](#systemperspectiveauthenticationchallenge) - This function is used inPython Scripting. Triggers anauthentication challengeaction.
249. [system.perspective.closeDock](#systemperspectiveclosedock) - This function is used inPython Scripting. Closes a docked view. This function acceptskeyword arguments.
250. [system.perspective.closePage](#systemperspectiveclosepage) - This function is used inPython Scripting. Closes the page with the given page id or the current page if no page id is provided. If a message is provided, it is displayed on the page when the page closes. Otherwise the default message (set in theProject properties) is displayed. system.perspective.closePage([message], [sessionId], [pageID])
251. [system.perspective.closePopup](#systemperspectiveclosepopup) - This function is used inPython Scripting. Closes a popup view. This function acceptskeyword arguments.
252. [system.perspective.closeSession](#systemperspectiveclosesession) - This function is used inPython Scripting. Closes the Perspective Session with the given sessionID or the current Session if no ID is provided. If a message is provided, it is displayed on the page when the Session closes. Otherwise the default message (set in theProject properties) is displayed. In the Perspective App, the user is returned to the launch screen.
253. [system.perspective.download](#systemperspectivedownload) - This function is used inPython Scripting. Downloads data from the Gateway to a device running a Session. When calling from the Gateway scope, the call must include a sessionId.
254. [system.perspective.getProjectInfo](#systemperspectivegetprojectinfo) - This function is used inPython Scripting. Returns a dictionary of meta data from a Perspective Project. Exact fields are as follows:
255. [system.perspective.getSessionInfo](#systemperspectivegetsessioninfo) - This function is used inPython Scripting. Returns information about one or more Perspective Sessions. The information returned by this function is a combination of information available on thePerspective Sessions statuspage on the Gateway, and some Session props (id and userAgent). Exact fields are as follows: This function acceptskeyword arguments.
256. [system.perspective.isAuthorized](#systemperspectiveisauthorized) - This function is used inPython Scripting. Checks if the user in the current Session is authorized against a target collection of security levels. system.perspective.isAuthorized(isAllOf, securityLevels, [sessionID])
257. [system.perspective.login](#systemperspectivelogin) - This function is used inPython Scripting. Triggers a login event that will allow the user to log in with the project's configured Identity Provider (IdP). For this function to work, an IdP must be set in PerspectiveProject properties. This is particularly useful when you want it to be possible to start a session without authentication and sign in to access certain restricted features. Note that calling this function after a user is already logged in willnotlog out the previous user.
258. [system.perspective.logout](#systemperspectivelogout) - This function is used inPython Scripting. Triggers a logout event, which will log the user out. For this function to work, an Identity Provider (IdP) must be set in thePerspective Project properties. Be advised that this function should not be used in the same script, or in the same triggering event assystem.perspective.login. Logging in and Logging out should always be triggered by separate events.
259. [system.perspective.navigate](#systemperspectivenavigate) - This function is used inPython Scripting. Navigate the session to a specified view or mounted page. The function can be used in three different ways, depending on which parameter is specified:
260. [system.perspective.navigateBack](#systemperspectivenavigateback) - This function is used inPython Scripting. Navigate the session to a specified view or mounted page. This is similar to a browser's "back" function.
261. [system.perspective.navigateForward](#systemperspectivenavigateforward) - This function is used inPython Scripting. Navigate the session to a specified view or mounted page. This is similar to a browser's "forward" function.
262. [system.perspective.openDock](#systemperspectiveopendock) - This function is used inPython Scripting. Opens a docked View. Requires the preconfigured dock ID for the view. system.perspective.openDock(id, [sessionId], [pageId])
263. [system.perspective.openPopup](#systemperspectiveopenpopup) - This function is used inPython Scripting. Open apopup viewover the given page. system.perspective.openPopup(id, view, [params], [title], [position], [showCloseIcon], [draggable], [resizable], [modal], [overlayDismiss], [sessionId], [pageId], [viewportBound])
264. [system.perspective.print](#systemperspectiveprint) - This function is used inPython Scripting. Prints the supplied message to the local console (or the gateway logs, as appropriate) - by default, this means the Output Console when in the Designer, and the browser's console when in a live session. system.perspective.print([message], [sessionId], [pageId], [destination])
265. [system.perspective.refresh](#systemperspectiverefresh) - This function is used inPython Scripting. Triggers a refresh of the page. This method should not be confused with therefreshBindingcomponent method, which automatically fires a binding on a Perspective component property.
266. [system.perspective.sendMessage](#systemperspectivesendmessage) - This function is used inPython Scripting. Send a message to acomponent message handlerwithin the same session. This function cannot interact with Session Message Handlers configured in Session Events, even if thescopeof session is specified. Invoked Message Handlersexecute asynchronouslyto the calling script.
267. [system.perspective.setTheme](#systemperspectivesettheme) - This function is used inPython Scripting. Changes the theme in a page to the specified theme. Note that this function only changes the theme for a single page, not the entire session. To change the theme for a session, write directly to thesession.themeproperty instead.
268. [system.perspective.toggleDock](#systemperspectivetoggledock) - This function is used inPython Scripting. Toggles a docked view. system.perspective.toggleDock(id, [sessionId], [pageId])
269. [system.perspective.togglePopup](#systemperspectivetogglepopup) - This function is used inPython Scripting. Toggles apopup view. Will open up the popup if it has not been opened yet. Otherwise, it will close the currently opened popup. system.perspective.togglePopup(id, view, [params], [title], [position], [showCloseIcon], [draggable], [resizable], [modal], [overlayDismiss], [sessionId], [pageId], [viewportBound])
270. [system.perspective.vibrateDevice](#systemperspectivevibratedevice) - This function is used inPython Scripting. When called from thePerspective App, will cause the device to vibrate for the specified number of milliseconds. iOS vibration duration is fixed. This function will cause an iOS device to vibrate for its default duration, 0.4 seconds (400 milliseconds).
271. [system.perspective.workstation](#systemperspectiveworkstation) - The following functions offer various ways to interact with Perspective Workstation from a Python script. Note that the functions here only work when called from a session running in Perspective Workstation. When called from a session running in Workstation, this function will close Workstation. Attempts to put Workstation into Kiosk mode.
272. [system.perspective.workstation.exit](#systemperspectiveworkstationexit) - This function is used inPython Scripting. When called from a session running in Workstation, this function will close Workstation. system.perspective.workstation.exit()
273. [system.perspective.workstation.toKiosk](#systemperspectiveworkstationtokiosk) - This function is used inPython Scripting. When called from a session running inPerspective Workstation, attempts to put Workstation into Kiosk mode. system.perspective.workstation.toKiosk()
274. [system.perspective.workstation.toWindowed](#systemperspectiveworkstationtowindowed) - This function is used inPython Scripting. When called from a Session running inPerspective Workstation, attempts to put Workstation into windowed mode. system.perspective.workstation.toWindowed()
275. [system.print.createImage](#systemprintcreateimage) - This function is used inPython Scripting. Takes a snapshot of a component and creates a Java BufferedImage out of it. You can usejavax.imageio.ImageIOto turn this into bytes that can be saved to a file or a BLOB field in a database. This scripting function has noClient Permissionrestrictions.
276. [system.print.createPrintJob](#systemprintcreateprintjob) - This function is used inPython Scripting. Provides a general printing facility for printing the contents of a window or component to a printer. The general workflow for this function is that you create the print job, set the options you'd like on it, and then call print()  on the job. For printing reports or tables, use those components' dedicated print() functions. The PrintJob object that this function returns has the following properties:
277. [system.print.getDefaultPrinterName](#systemprintgetdefaultprintername) - This function is used inPython Scripting. Obtains the local default printer.
278. [system.print.getPrinterNames](#systemprintgetprinternames) - This function is used inPython Scripting. Lists the available local printers.
279. [system.print.printToImage](#systemprintprinttoimage) - This function is used inPython Scripting. This function prints the given component (such as a graph, container, entire window, etc) to an image file, and saves the file where ever the operating system deems appropriate. A filename and path may be provided to determine the name and location of the saved file. While not required, it is highly recommended to pass in a filename and path. The script may fail if the function attempts to save to a directory that the client does not have access rights t
280. [system.project.getProjectName](#systemprojectgetprojectname) - This function is used inPython Scripting. Returns the name of the project where the function was called from. When called from the Gateway scope from a resource that originates from a singular project (reports, SFCs, etc.), will return that resources project. Resources that run in the Gateway scope, but are configured in a singular project (such as a report), will use that project's name. When called from a scope that does not have an associated project (a Tag Event Script), the function will re
281. [system.project.getProjectNames](#systemprojectgetprojectnames) - This function is used inPython Scripting. Returns an unsorted collection of strings, where each string represents the name of a project on the Gateway. If no projects exist, returns an empty list. This function only ever returns project names, ignoring project titles. The function also ignores the "enabled" property, including disabled projects in the results.
282. [system.project.requestScan](#systemprojectrequestscan) - This function is used inPython Scripting. Requests a manual scan of the projects directory in order to refresh projects and their resources. If a scan is currently running, this method has no effect and will return when the in-progress scan has finished. This function blocks the current thread until a scan has completed. This scripting function has noClient Permissionrestrictions.
283. [system.report.executeAndDistribute](#systemreportexecuteanddistribute) - This function is used inPython Scripting. Executes and distributes a report. Similar toscheduling a report to execute, except a schedule is not required to utilize this function. This is a great way to distribute the report on demand from a Client. Throws an IllegalArgumentException when any of the following occurs: If the file type is not recognized, path does not exist, project does not exist, or a key is not valid. The function system.report.executeAndDistribute() does not run on its own thre
284. [system.report.executeReport](#systemreportexecutereport) - This function is used inPython Scripting. Immediately executes an existing report and returns a List[Byte] of the output. Throws an IllegalArgumentException when any of the following occurs: If the file type is not recognized, path does not exist, project does not exist. This scripting function has noClient Permissionrestrictions.
285. [system.report.getReportNamesAsDataset](#systemreportgetreportnamesasdataset) - This function is used inPython Scripting. Gets a data of all reports for a project. Throws an IllegalArgumentException when any of the following occurs: If the project name is omitted in the Gateway scope, project does not exist. This scripting function has noClient Permissionrestrictions.
286. [system.report.getReportNamesAsList](#systemreportgetreportnamesaslist) - This function is used inPython Scripting. Gets a list of all reports for a project. Throws an IllegalArgumentException when any of the following occurs: If the project name is omitted in the Gateway scope or if project does not exist. This scripting function has noClient Permissionrestrictions.
287. [system.roster.addUsers](#systemrosteraddusers) - This function is used inPython Scripting. Adds a list of users to an existing roster. Users are always appended to the end of the roster. system.roster.addUsers(rosterName, [users])
288. [system.roster.createRoster](#systemrostercreateroster) - This function is used inPython Scripting. Creates a roster with the given name and description, if it does not already exist. This function was designed to run in the Gateway and in Perspective sessions. If creating rosters from Vision clients, usesystem.alarm.createRosterinstead
289. [system.roster.deleteRoster](#systemrosterdeleteroster) - This function is used inPython Scripting. Deletes a roster with the given name.
290. [system.roster.getRoster](#systemrostergetroster) - This function is used inPython Scripting. Returns the roster corresponding to the given name. You can call getUsers() to access a list of User objects in the RosterModel.
291. [system.roster.getRosterNames](#systemrostergetrosternames) - This function is used inPython Scripting. Returns a list of roster names.
292. [system.roster.getRosters](#systemrostergetrosters) - This function is used inPython Scripting. Returns a dictionary of rosters, where the key is the name of the roster, and the value is an array list of string user names. This function was designed to run in the Gateway and in Perspective sessions. If creating rosters from Vision clients, usesystem.alarm.getRostersinstead.
293. [system.roster.removeUsers](#systemrosterremoveusers) - This function is used inPython Scripting. Removes one or more users from an existing roster. system.roster.removeUsers(rosterName, users)
294. [system.secsgem.copyEquipment](#systemsecsgemcopyequipment) - This function is used inPython Scripting. Creates a copy of an equipment connection and places it in the Gateway > Config > SECS/GEM > Equipment. Common settings can be overridden for the new connection. An exception is thrown if the new equipment connection cannot be created.
295. [system.secsgem.deleteToolProgram](#systemsecsgemdeletetoolprogram) - This function is used inPython Scripting. Deletes a process program from the Gateway. Permission Type: SECS/GEM Management
296. [system.secsgem.enableDisableEquipment](#systemsecsgemenabledisableequipment) - This function is used inPython Scripting. Enables or disables a Tuple of equipment connections from a script. Permission Type: SECS/GEM Management
297. [system.secsgem.getResponse](#systemsecsgemgetresponse) - This function is used inPython Scripting. Attempts to retrieve a response message from the Gateway. The transaction id from the sent message is used to retrieve the response. This scripting function has noClient Permissionrestrictions.
298. [system.secsgem.getToolProgram](#systemsecsgemgettoolprogram) - This function is used inPython Scripting. Returns a process program from the Gateway that was previously sent by a a tool in an S7F3 message. This scripting function has noClient Permissionrestrictions.
299. [system.secsgem.getToolProgramDataset](#systemsecsgemgettoolprogramdataset) - This function is used inPython Scripting. Returns a Dataset containing information about all stored process programs. This scripting function has noClient Permissionrestrictions.
300. [system.secsgem.sendRequest](#systemsecsgemsendrequest) - This function is used inPython Scripting. Sends a JSON-formatted SECS message to a tool. An equipment connection must be configured for the tool in the Gateway. This scripting function has noClient Permissionrestrictions.
301. [system.secsgem.sendResponse](#systemsecsgemsendresponse) - This function is used inPython Scripting. Sends a JSON-formatted SECS response message to a message sent by a tool. An equipment connection must be configured for the tool in the Gateway, and this must be used within a Message Handler to create aCustom Message Response Handler. This scripting function has noClient Permissionrestrictions.
302. [system.secsgem.startSimEventRun](#systemsecsgemstartsimeventrun) - This function is used inPython Scripting. Starts a configured simulator event run in the Gateway. Note, that this function only works with the simulators that come included with the SECS/GEM module. The function will throw an exception if the specified Event Run cannot be started.
303. [system.secsgem.toDataset](#systemsecsgemtodataset) - This function is used inPython Scripting. Converts a SECS message data structure, as returned by thesystem.secsgem.getResponsefunction, into a dataset and returns it. This scripting function has noClient Permissionrestrictions.
304. [system.secsgem.toTreeDataset](#systemsecsgemtotreedataset) - This function is used inPython Scripting. Changes an existing dataset, as returned by thesystem.secsgem.toDataSetfunction, to make it usable for theTree Viewcomponent. This scripting function has noClient Permissionrestrictions.
305. [system.security.getRoles](#systemsecuritygetroles) - This function is used inPython Scripting. Finds the roles that the currently logged in user has, returns them as a Python tuple of strings. This scripting function has noClient Permissionrestrictions.
306. [system.security.getUserRoles](#systemsecuritygetuserroles) - This function is used inPython Scripting. Fetches the roles for a user from the Gateway. This may not be the currently logged in user. Requires the password for that user. If the authentication profile name is omitted, then the current project's default authentication profile is used. This scripting function has noClient Permissionrestrictions.
307. [system.security.getUsername](#systemsecuritygetusername) - This function is used inPython Scripting. Returns the currently logged-in username. This scripting function has noClient Permissionrestrictions.
308. [system.security.isScreenLocked](#systemsecurityisscreenlocked) - This function is used inPython Scripting. Returns whether or not the screen is currently locked. This scripting function has noClient Permissionrestrictions.
309. [system.security.lockScreen](#systemsecuritylockscreen) - This function is used inPython Scripting. Used to put a running client in lock-screen mode. The screen can be unlocked by the user with the proper credentials, or by scripting via thesystem.security.unlockScreen()function. This scripting function has noClient Permissionrestrictions.
310. [system.security.logout](#systemsecuritylogout) - This function is used inPython Scripting. Logs out of the Client for the current user and brings the Client to the login screen. This scripting function has noClient Permissionrestrictions.
311. [system.security.switchUser](#systemsecurityswitchuser) - This function is used inPython Scripting. Attempts to switch the current user on the fly. If the given username and password fail, this function will return false. If it succeeds, then all currently opened windows are closed, the user is switched, and windows are then re-opened in the states that they were in. If an event object is passed to this function, the parent window of the event object will not be re-opened after a successful user switch. This is to support the common case of having a sw
312. [system.security.unlockScreen](#systemsecurityunlockscreen) - This function is used inPython Scripting. Unlocks the client, if it is currently in lock-screen mode. This scripting function has noClient Permissionrestrictions.
313. [system.security.validateUser](#systemsecurityvalidateuser) - This function is used inPython Scripting. Tests credentials (username and password) against an authentication profile. Returns a boolean based upon whether or not the authentication profile accepts the credentials. If the authentication profile name is omitted, then the current project's default authentication profile is used. This scripting function has noClient Permissionrestrictions.
314. [system.serial.closeSerialPort](#systemserialcloseserialport) - This function is used inPython Scripting. Closes a previously opened serial port. Returns without doing anything if the named serial port is not currently open. Will throw an exception if the port is open and cannot be closed. This scripting function has noClient Permissionrestrictions.
315. [system.serial.configureSerialPort](#systemserialconfigureserialport) - This function is used inPython Scripting. Configure a serial port for use in a later call. This only needs to be done once unless the configuration has changed after the initial call. All access to constants must be prefixed by " system.serial. ". This scripting function has noClient Permissionrestrictions.
316. [system.serial.openSerialPort](#systemserialopenserialport) - This function is used inPython Scripting. Opens a previously configured serial port for use. Will throw an exception if the serial port cannot be opened. This scripting function has noClient Permissionrestrictions.
317. [system.serial.port](#systemserialport) - This function is used inPython Scripting. Returns acontext managerwrapping a serial port, allowing the rest of the system to interact with that port. This function effectively combines thesystem.serial.configureSerialPort,system.serial.openSerialPort, andsystem.serial.closeSerialPortfunctions into a single call. Intended to be used with thePython 'with' statement. The object aliased in the 'with' statement has special access to all of the othersystem.serialfunctions, allowing for reads and write
318. [system.serial.readBytes](#systemserialreadbytes) - This function is used inPython Scripting. ReadnumberOfBytesbytes from a serial port. This scripting function has noClient Permissionrestrictions.
319. [system.serial.readBytesAsString](#systemserialreadbytesasstring) - This function is used inPython Scripting. Read numberOfBytes bytes from a serial port and convert them to a String. If a specific encoding is needed to match the source of the data, usesystem.serial.readBytesand use the desired encoding to decode the byte array returned. This scripting function has noClient Permissionrestrictions.
320. [system.serial.readLine](#systemserialreadline) - This function is used inPython Scripting. Attempts to read a line from a serial port. A "line" is considered to be terminated by either a line feed ('\n'), a carriage return ('\r'), or a carriage return followed immediately by a line feed. The function will wait until the timeout period for a terminator. If the timeout is reached before the line is properly terminated, then the buffer will be dumped, possibly resulting in data loss.
321. [system.serial.readUntil](#systemserialreaduntil) - This function is used inPython Scripting. Reads a byte at a time from a serial port until a delimiter character is encountered. The read will block for up to timeout milliseconds before returning. If the delimiter is not found before the timeout period, then the buffer will dump, potentially resulting in data loss.
322. [system.serial.sendBreak](#systemserialsendbreak) - This function is used inPython Scripting. Sends a break signal for approximately millis milliseconds. This scripting function has noClient Permissionrestrictions.
323. [system.serial.write](#systemserialwrite) - This function is used inPython Scripting. Write a String to a serial port using the platforms default character encoding. This scripting function has noClient Permissionrestrictions.
324. [system.serial.writeBytes](#systemserialwritebytes) - This function is used inPython Scripting. Write a List[Byte] to a serial port. This scripting function has noClient Permissionrestrictions.
325. [system.sfc.cancelChart](#systemsfccancelchart) - This function is used inPython Scripting. Cancels the execution of a running chart instance. Any running steps will be told to stop, and the SFC chart will enter Canceling state. Will throw a KeyError if the ID does not match any running chart instance. Permission Type: SFC Management
326. [system.sfc.getRunningCharts](#systemsfcgetrunningcharts) - This function is used inPython Scripting. Retrieves information about running charts. Can search all running charts, or be filtered charts at a specific path. This function will return charts that are in a Paused state. This scripting function has noClient Permissionrestrictions.
327. [system.sfc.getVariables](#systemsfcgetvariables) - This function is used inPython Scripting. Get the variables in a chart instance's scope. Commonly used to check the value of a Chart Parameter, or determine how long the chart has been running for. This scripting function has noClient Permissionrestrictions.
328. [system.sfc.pauseChart](#systemsfcpausechart) - This function is used inPython Scripting. Pauses a running chart instance. Any running steps will be told to pause, and the chart will enter Pausing state. Will throw a KeyError if the ID does not match any running chart instance. Permission Type: SFC Management
329. [system.sfc.redundantCheckpoint](#systemsfcredundantcheckpoint) - This function is used inPython Scripting. Synchronizes chart and step variables of the specified chart instance across a redundant cluster, allowing the chart instance to continue where it left off if a redundant failover occurs. Check outredundancy syncfor more information. Permission Type: SFC Management
330. [system.sfc.resumeChart](#systemsfcresumechart) - This function is used inPython Scripting. Resumes a chart that was paused. Steps which were previously paused will be resumed, and chart will enter Resuming state. Will throw a KeyError if the ID does not match any running chart instance. Permission Type: SFC Management
331. [system.sfc.setVariable](#systemsfcsetvariable) - This function is used inPython Scripting. Sets a variable inside a currently runningSFC chart. Permission Type: SFC Management
332. [system.sfc.setVariables](#systemsfcsetvariables) - This function is used inPython Scripting. Sets any number of variables inside a currently running chart. Permission Type: SFC Management
333. [system.sfc.startChart](#systemsfcstartchart) - This function is used inPython Scripting. Starts a new instance of a chart. The chart must be set to "Callable" execution mode. Permission Type: SFC Management
334. [system.tag.browse](#systemtagbrowse) - This function is used inPython Scripting. Returns a list ofnodesfound at the specified path. The list objects are returned as dictionaries with some basic information about each node. This scripting function has noClient Permissionrestrictions.
335. [system.tag.browseHistoricalTags](#systemtagbrowsehistoricaltags) - This function is used inPython Scripting. Will browse for any historical tags at the provided historical path. It will only browse for tags at the path, and will not go down through any children. Will return with a BrowseResults object, which can be accessed using the methods below: The result set returned from .getResults() is a list of Results objects. This list can be iterated through with a standard for loop, and each object in the list can be accessed with the following methods:
336. [system.tag.configure](#systemtagconfigure) - This function is used inPython Scripting. Creates tags from a given list of Python dictionaries or from a JSON source string. Can be used to overwrite a current tag's configuration. When utilizing this function, the tag definitions must specify the names of properties with their scripting/JSON name. A reference of these properties can be found on theTag PropertiesandTag Alarm Propertiespages.
337. [system.tag.copy](#systemtagcopy) - This function is used inPython Scripting. Copies tags from one folder to another. Multiple Tag and folder paths may be passed to a single call of this function. The new destination can be a separate tag provider. When copying UDTs to a different provider, the destination provider must have a matching UDT definition. The function copies Tags sequentially, so definitions can be placed earlier in the list, with instances following after:
338. [system.tag.deleteAnnotations](#systemtagdeleteannotations) - This function is used inPython Scripting. Removes stored annotations from the sqlth_annotations table.  Requires the full Tag path (including history provider) for each annotation, as well as each annotation's storage ID.
339. [system.tag.deleteTags](#systemtagdeletetags) - This function is used inPython Scripting. Deletes multiple tags or tag folders. When deleting a tag folder, all tags under the folder are also deleted. Permission Type: Tag Editing
340. [system.tag.exists](#systemtagexists) - This function is used inPython Scripting. Checks whether or not a tag with a given path exists. This scripting function has noClient Permissionrestrictions.
341. [system.tag.exportTags](#systemtagexporttags) - This function is used inPython Scripting. Exports tags to a file on a local file system. The term "local file system" refers to the scope in which the script was running; for example, running this script in a Gateway Timer script will export the file to the Gateway file system.
342. [system.tag.getConfiguration](#systemtaggetconfiguration) - This function is used inPython Scripting. Retrieves tags from the Gateway as Python dictionaries. These can be edited and then saved back usingsystem.tag.configure. The configurations returned by this function can only contain properties that arenotusing their default values. Thus, if a property on a tag has not been modified from its default value, then it willnotbe included in the returned list.
343. [system.tag.importTags](#systemtagimporttags) - This function is used inPython Scripting. Imports a JSON tag file at the provided path. Also supports XML and CSV Tag file exports from legacy systems. Permission Type: Tag Editing
344. [system.tag.isOverlaysEnabled](#systemtagisoverlaysenabled) - This function is used inPython Scripting. Returns whether or not the current client's quality overlay system is currently enabled. This scripting function has noClient Permissionrestrictions.
345. [system.tag.move](#systemtagmove) - This function is used inPython Scripting. Moves tags or folders to a new destination. The new destination can be a separate tag provider. If interested in copying the tags to a new destination, instead of moving them, please see thesystem.tag.copypage. When moving UDTs to a different provider, the destination provider must have a matching UDT definition. This function moves folders/tags sequentially, so definitions can be placed earlier in the list, with instances following after.
346. [system.tag.query](#systemtagquery) - This function is used inPython Scripting. Queries a Tag Provider to produce a list of tags that meet the specified criteria. Provides the same functionality as theTag Report Tool.
347. [system.tag.queryAnnotations](#systemtagqueryannotations) - This function is used inPython Scripting. Queries annotations stored in the Tag History system for a set of paths for a given time range.
348. [system.tag.queryTagCalculations](#systemtagquerytagcalculations) - This function is used inPython Scripting. Queries various calculations (aggregations) for a set of tags over a specified range. Returns a dataset with a row per tag, and a column per calculation. This is useful when you wish to aggregate tag history collected over a period of time into a single value per aggregate. If you want multiple values aggregated to a single time slice (i.e., hourly aggregates for the same tag over an 8 hour period) consider usingsystem.tag.queryTagHistory.
349. [system.tag.queryTagDensity](#systemtagquerytagdensity) - This function is used inPython Scripting. Queries the Tag history system for information about the density of data. In other words, how much data is available for a given time span. This function is called with a list of Tag paths, and a start and end date. The result set is a two column dataset specifying the timestamp, and a relative weight. Each row is valid from the given time until the next row. Tags are assigned a 1 or a 0 if they are present or not. All values are then multiplied together
350. [system.tag.queryTagHistory](#systemtagquerytaghistory) - This function is used inPython Scripting. Issues a query to the Tag Historian. Querying tag history involves specifying the tags and the date range, as well as a few optional parameters. The Tag Historian will find the relevant history and then interpolate and aggregate it together into a coherent, tabular result set. This function takes a list of strings, where each string is a tag path, likeTanks/Tank5or[OracleProvider]Sump/Out2. This function also supports historical tag paths, seeTag Pathsfo
351. [system.tag.readAsync](#systemtagreadasync) - This function is used inPython Scripting. Asynchronously reads the value of the tags at the given paths. Meaning, execution of the calling script will continue without waiting for this function to finish. This is useful in cases where the rest of the script should continue without waiting for the results from system.tag.readAsync. Instead of returning the tag read results to the calling script, the results are processed by a Python callback function.
352. [system.tag.readBlocking](#systemtagreadblocking) - This function is used inPython Scripting. Reads the value of the tags at the given paths. Will "block" until the read operation is complete or times out. Meaning, execution of the calling script will pause until this function finishes. This is useful in cases where the tag read must complete before further lines in the same script should execute. This scripting function has noClient Permissionrestrictions.
353. [system.tag.rename](#systemtagrename) - This function is used inPython Scripting. Renames a single tag or folder. Permission Type: Tag Editing
354. [system.tag.requestGroupExecution](#systemtagrequestgroupexecution) - This function is used inPython Scripting. Sends a request to the specified tag group to execute now. This scripting function has noClient Permissionrestrictions.
355. [system.tag.setOverlaysEnabled](#systemtagsetoverlaysenabled) - This function is used inPython Scripting. Enables or disables the component quality overlay system. This scripting function has noClient Permissionrestrictions.
356. [system.tag.storeAnnotations](#systemtagstoreannotations) - This function is used inPython Scripting. Stores annotations into the tag history system. Annotations are stored by the underlying historian implementations, so different providers may store in different ways, and some providers may not support annotation storage. All parameters are 1-to-1, so all provided lists should be of the same length. If a particular annotation doesn't need a parameter, that element can be None in the list.
357. [system.tag.storeTagHistory](#systemtagstoretaghistory) - This function was originally deprecated in 8.0.0. It was reintroduced in version 8.1.8. This function is used inPython Scripting. Inserts data into the tag history system, allowing Tag history to be recorded via scripting.
358. [system.tag.writeAsync](#systemtagwriteasync) - This function is used inPython Scripting. Asynchronously writes values to tags at specified paths. The script will not wait for the write operation to complete before moving on, but you can provide a callback function to run further code after the write has finished. For a blocking tag write operation, seesystem.tag.writeBlocking.
359. [system.tag.writeBlocking](#systemtagwriteblocking) - This function is used inPython Scripting. Writes values to tags at the given paths. This function will "block" until the write operation is complete or times out. Meaning, execution of the calling script will pause until this function finishes. This is useful in cases where the tag write must complete before further lines in the same script should execute. Permission Type: Tag Editing
360. [system.twilio.getAccounts](#systemtwiliogetaccounts) - This function is used inPython Scripting. Returns a list of Twilio account names that have been configured in the Gateway. This scripting function has noClient Permissionrestrictions.
361. [system.twilio.getAccountsDataset](#systemtwiliogetaccountsdataset) - This function is used inPython Scripting. Returns a list of Twilio account names that have been configured in the Gateway as a single-column Dataset. This scripting function has noClient Permissionrestrictions.
362. [system.twilio.getPhoneNumbers](#systemtwiliogetphonenumbers) - This function is used inPython Scripting. Returns a list of outgoing phone numbers for a Twilio account. Note that these numbers are supplied by Twilio, and are not defined on a user in Ignition. This scripting function has noClient Permissionrestrictions.
363. [system.twilio.getPhoneNumbersDataset](#systemtwiliogetphonenumbersdataset) - This function is used inPython Scripting. Returns a list of outgoing phone numbers for a Twilio account as a single-column Dataset. Note that these numbers are supplied by Twilio, and are not defined on a user in Ignition. This scripting function has noClient Permissionrestrictions.
364. [system.twilio.sendSms](#systemtwiliosendsms) - This function is used inPython Scripting. Sends an SMS message. This scripting function has noClient Permissionrestrictions.
365. [system.user.addCompositeSchedule](#systemuseraddcompositeschedule) - This function is used inPython Scripting. Allows two schedules to be combined into a composite schedule. Permission Type: User Management
366. [system.user.addHoliday](#systemuseraddholiday) - This function is used inPython Scripting. Allows a holiday to be added. Permission Type: User Management
367. [system.user.addRole](#systemuseraddrole) - This function is used inPython Scripting. Adds a role to the specified user source. When altering the Gateway System User Source, theAllow User Adminsetting must be enabled. Permission Type: User Management
368. [system.user.addSchedule](#systemuseraddschedule) - This function is used inPython Scripting. Adds a schedule. Permission Type: User Management
369. [system.user.addUser](#systemuseradduser) - This function is used inPython Scripting. Adds a new user to a user source. Used in combination withgetNewUserto create new user. Permission Type: User Management
370. [system.user.createScheduleAdjustment](#systemusercreatescheduleadjustment) - This function is used inPython Scripting. Creates a schedule adjustment. Permission Type: User Management
371. [system.user.editHoliday](#systemusereditholiday) - This function is used inPython Scripting. Allows a holiday to be edited. Permission Type: User Management
372. [system.user.editRole](#systemusereditrole) - This function is used inPython Scripting. Renames a role in the specified user source. When altering the Gateway System User Source, theAllow User Adminsetting must be enabled. Permission Type: User Management
373. [system.user.editSchedule](#systemusereditschedule) - This function is used inPython Scripting. Allows a schedule to be edited. Permission Type: User Management
374. [system.user.editUser](#systemuseredituser) - This function is used inPython Scripting. Alters a specific user in a user source, replacing the previous data with the new data passed in. Permission Type: User Management
375. [system.user.getHoliday](#systemusergetholiday) - This function is used inPython Scripting. Returns a specific holiday. This scripting function has noClient Permissionrestrictions.
376. [system.user.getHolidayNames](#systemusergetholidaynames) - This function is used inPython Scripting. Returns a collection of Strings of all holiday names. This scripting function has noClient Permissionrestrictions.
377. [system.user.getHolidays](#systemusergetholidays) - This function is used inPython Scripting. Returns a sequence of all of the holidays available. This scripting function has noClient Permissionrestrictions.
378. [system.user.getNewUser](#systemusergetnewuser) - This function is used inPython Scripting. Creates a new user object. The user will not be added to the user source untiladdUseris called. Permission Type: User Management
379. [system.user.getRoles](#systemusergetroles) - This function is used inPython Scripting. Returns a sequence of strings representing all of the roles configured in a specific user source. This scripting function has noClient Permissionrestrictions.
380. [system.user.getSchedule](#systemusergetschedule) - This function is used inPython Scripting. Returns a specific schedule. This scripting function has noClient Permissionrestrictions.
381. [system.user.getScheduleNames](#systemusergetschedulenames) - This function is used inPython Scripting. Returns a sequence of strings representing the names of all of the schedules available. This scripting function has noClient Permissionrestrictions.
382. [system.user.getScheduledUsers](#systemusergetscheduledusers) - This function is used inPython Scripting. Returns a list of users that are scheduled. If no users are scheduled, it will return an empty list. This scripting function has noClient Permissionrestrictions.
383. [system.user.getSchedules](#systemusergetschedules) - This function is used inPython Scripting. Returns a sequence of all available schedule models, which can be used to return configuration information on the schedule, such as time for each day of the week. This scripting function has noClient Permissionrestrictions.
384. [system.user.getUser](#systemusergetuser) - This function is used inPython Scripting. Looks up a specific user in a user source, by username. The full User object is returned except for the user's password. This scripting function has noClient Permissionrestrictions.
385. [system.user.getUserSources](#systemusergetusersources) - This function is used inPython Scripting. Returns a sequence of objects representing all of the user source profiles configured in the Gateway. Each object has a "name" property, a "description" property, and a "type" property. This scripting function has noClient Permissionrestrictions.
386. [system.user.getUsers](#systemusergetusers) - This function is used inPython Scripting. Retrieves the list of users in a specific user source. The "User" objects that are returned contain all of the information about that user, except for the user's password. This scripting function has noClient Permissionrestrictions.
387. [system.user.isUserScheduled](#systemuserisuserscheduled) - This function is used inPython Scripting. Will check if a specified User is scheduled currently or on a specified date/time. This scripting function has noClient Permissionrestrictions.
388. [system.user.removeHoliday](#systemuserremoveholiday) - This function is used inPython Scripting. Allows a holiday to be deleted. Permission Type: User Management
389. [system.user.removeRole](#systemuserremoverole) - This function is used inPython Scripting. Removes a role from the specified user source. When altering the Gateway System User Source, theAllow User Adminsetting must be enabled. Permission Type: User Management
390. [system.user.removeSchedule](#systemuserremoveschedule) - This function is used inPython Scripting. Allows a schedule to be deleted. Note that schedules which are used in Composite Schedules can not be deleted until they are removed from the Composite Schedule. Permission Type: User Management
391. [system.user.removeUser](#systemuserremoveuser) - This function is used inPython Scripting. Removes a specific user from the a user source based on username. When altering the Gateway System User Source, theAllow User Adminsetting must be enabled. Permission Type: User Management
392. [system.util.audit](#systemutilaudit) - This function is used inPython Scripting. Inserts a record into an audit profile. This scripting function has noClient Permissionrestrictions.
393. [system.util.beep](#systemutilbeep) - This function is used inPython Scripting. Tells the computer where the script is running to make a "beep" sound. The computer must have a way of producing sound. While this function is technically scoped for Gateway and Perspective Sessions, it's intended for use in Vision Clients.
394. [system.util.execute](#systemutilexecute) - This function is used inPython Scripting. Executes the given commands via the operating system, in a separate process. The commands argument is an array of strings. The first string is the program to execute, with subsequent strings being the arguments to that command. This scripting function has noClient Permissionrestrictions.
395. [system.util.exit](#systemutilexit) - This function is used inPython Scripting. Exits the running client, as long as the shutdown intercept script doesn't cancel the shutdown event. Set force to true to not give the shutdown intercept script a chance to cancel the exit. Note that this will quit the Client completely. you can use system.security.logout() to return to the login screen. This scripting function has noClient Permissionrestrictions.
396. [system.util.getAvailableLocales](#systemutilgetavailablelocales) - This function is used inPython Scripting. Returns a collection of strings representing the Locales added to the Translation Manager, such as 'en' for English. This scripting function has noClient Permissionrestrictions.
397. [system.util.getAvailableTerms](#systemutilgetavailableterms) - This function is used inPython Scripting. Returns a collection of available terms defined in the translation system. This scripting function has noClient Permissionrestrictions.
398. [system.util.getClientId](#systemutilgetclientid) - This function is used inPython Scripting. Returns a hex-string that represents a number unique to the running client's session. You are guaranteed that this number is unique between all running clients. This scripting function has noClient Permissionrestrictions.
399. [system.util.getConnectTimeout](#systemutilgetconnecttimeout) - This function is used inPython Scripting. Returns the connect timeout in milliseconds for all client-to-gateway communication. This is the maximum amount of time that communication operations to the Gateway will be given to connect. The default is 10,000ms (10 seconds). This scripting function has noClient Permissionrestrictions.
400. [system.util.getConnectionMode](#systemutilgetconnectionmode) - This function is used inPython Scripting. Retrieves this client session's current connection mode. 3 is read/write, 2 is read-only, and 1 is disconnected. This scripting function has noClient Permissionrestrictions.
401. [system.util.getEdition](#systemutilgetedition) - This function is used inPython Scripting. Returns the "edition" of the Vision client - "standard", "limited", or "panel". This scripting function has noClient Permissionrestrictions.
402. [system.util.getGatewayAddress](#systemutilgetgatewayaddress) - This function is used inPython Scripting. Returns the address of the Gateway with which the Client is currently communicating. This scripting function has noClient Permissionrestrictions.
403. [system.util.getGatewayStatus](#systemutilgetgatewaystatus) - This function is used inPython Scripting. Returns a string that indicates the status of a Gateway. A status ofRUNNINGmeans the Gateway is fully functional. If an exception occurs, the function returnsERRORwith the associated error message appended. This function can be used to test the availability and operational state of a remote Gateway. This scripting function has noClient Permissionrestrictions.
404. [system.util.getGlobals](#systemutilgetglobals) - This function is used inPython Scripting. This method returns a dictionary that provides access to the legacy global namespace. As of version 7.7.0, most new scripts use the modern style of scoping, which makes the 'global' keyword act very differently. Most importantly, the modern scoping rules mean that variables declared as 'global' are only global within that one module. The system.util.getGlobals() method can be used to interact with older scripts that used the old meaning of the 'global' k
405. [system.util.getInactivitySeconds](#systemutilgetinactivityseconds) - This function is used inPython Scripting. Returns the number of seconds since any keyboard or mouse activity. This function will always return zero in the Designer.
406. [system.util.getLocale](#systemutilgetlocale) - This function is used inPython Scripting. Returns the current string representing the user's Locale, such as 'en' for English. This scripting function has noClient Permissionrestrictions.
407. [system.util.getLogger](#systemutilgetlogger) - This function is used inPython Scripting. Returns a Logger object that can be used to log messages to the console. Each Logger has a name, which is typically structured hierarchically using periods, indicating where in the project the Logger is used. You can use any naming scheme you like, however a well-planned naming scheme makes finding  log entries and setting log levels much easier. Loggers can be shared between scripts simply by giving them the same name. Six levels of logging are availabl
408. [system.util.getModules](#systemutilgetmodules) - This function is used inPython Scripting. Returns a dataset of information about each installed module. Each row represents a single module. This scripting function has noClient Permissionrestrictions.
409. [system.util.getProjectName](#systemutilgetprojectname) - This function is used inPython Scripting. Returns the name of the project that is currently being run. When run from the Gateway scope from a resource that originates from a singular project (reports, SFCs, etc.), will return that resources project. When called from a scope that does not have an associated project (a Tag Event Script), the function will return the name of the Gateway scripting project. If a Gateway scripting project has not been configured, then returns an empty string.
410. [system.util.getProperty](#systemutilgetproperty) - This function is used inPython Scripting. Retrieves the value of a named system property. Some of the available properties are: This scripting function has noClient Permissionrestrictions.
411. [system.util.getReadTimeout](#systemutilgetreadtimeout) - This function is used inPython Scripting. Returns the read timeout in milliseconds for all client-to-gateway communication. This is the maximum amount of time allowed for a communication operation to complete. The default is 60,000ms (1 minute). This scripting function has noClient Permissionrestrictions.
412. [system.util.getSessionInfo](#systemutilgetsessioninfo) - This function is used inPython Scripting. Returns a PyDataSet holding information about all of the open Designer sessions and Vision Clients. Optional regular-expression based filters can be provided to filter the username or the username and the project returned. This function will not return all sessions across a cluster - only the cluster node that is being communicated with by the client who makes the call.
413. [system.util.getSystemFlags](#systemutilgetsystemflags) - This function is used inPython Scripting. Returns an integer that represents a bit field containing information about the currently running system. Each bit corresponds to a specific flag as defined in the bitmask below. The integer return will be a total of all of the bits that are currently active. See the example for tips on how to extract the information in this bit field. Note that the tag[System]Client/System/SystemFlagscontains the same value. This scripting function has noClient Permissi
414. [system.util.getVersion](#systemutilgetversion) - This function is used inPython Scripting. Returns the Ignition version number that is currently being run. If the version is from a nightly build or developer version that is not yet released, the version number will come back as "Dev Version", for example:
415. [system.util.invokeAsynchronous](#systemutilinvokeasynchronous) - This function is used inPython Scripting. Invokes (calls) the given Python function on a different thread. This means that calls to invokeAsynchronous will return immediately, and then the given function will start executing asynchronously on a different thread. This is useful for long-running data intensive functions, where running them synchronously (in the GUI thread) would make the GUI non-responsive for an unacceptable amount of time. This function should not be used to asynchronously inter
416. [system.util.invokeLater](#systemutilinvokelater) - This function is used inPython Scripting. Invokes (calls) the given Python function object after all of the currently processing and pending events are done being processed, or after a specified delay. The function will be executed on the GUI, or event dispatch, thread. This is useful for events like propertyChange events, where the script is called before any bindings are evaluated. If you specify an optional time argument (number of milliseconds), the function will be invoked after all current
417. [system.util.jsonDecode](#systemutiljsondecode) - This function is used inPython Scripting. Takes a JSON string and converts it into a Python object such as a list or a dictionary. If the input is not valid JSON, a string is returned. This scripting function has noClient Permissionrestrictions.
418. [system.util.jsonEncode](#systemutiljsonencode) - This function is used inPython Scripting. Takes a Python object such as a list or dictionary and converts into a JSON string. This scripting function has noClient Permissionrestrictions.
419. [system.util.modifyTranslation](#systemutilmodifytranslation) - This function is used inPython Scripting. This function allows you to add or modify a global translation. Permission Type: Translation Management
420. [system.util.playSoundClip](#systemutilplaysoundclip) - This function is used inPython Scripting. Plays a sound clip from a  wav  file to the system's default audio device. The  wav  file can be specified as a filepath, a URL, or directly as a raw List[Byte]. While this function is technically scoped for Gateway and Perspective Sessions, it's intended for use in Vision Clients.
421. [system.util.queryAuditLog](#systemutilqueryauditlog) - This function is used inPython Scripting. Queries an audit profile for audit history. Returns the results as a dataset. A description of the returned dataset can be found on theIgnition Database Table Referencepage.
422. [system.util.retarget](#systemutilretarget) - This function is used inPython Scripting. This function allows you to programmatically 'retarget' a Vision Client to a different project and/or different Gateway. You can have it switch to another project on the same Gateway, or another Gateway entirely, even across a WAN. This feature makes the vision of a seamless, enterprise-wide SCADA application a reality. The retarget feature will attempt to transfer the current user credentials over to the new project / Gateway. If the credentials fail on
423. [system.util.sendMessage](#systemutilsendmessage) - This function is used inPython Scripting. This function sends a message to clients running under the Gateway or to a project within the Gateway itself. To handle received messages, you must set up event script message handlers within a project. These message handlers run Jython code when a message is received. You can add message handlers under theMessagesection of the client/Gateway event script configuration dialogs. Messages cannot be received within a Designer. However, messages can be sent 
424. [system.util.sendRequest](#systemutilsendrequest) - This function is used inPython Scripting. This function sends a message to the Gateway, working in a similar manner to thesendMessagefunction, except sendRequest expects a response to the message. To handle received messages, you must set up Gateway Event Script message handlers within a project. These message handlers run Jython code when a message is received. You can then place a return at the end of the code to return something to where the sendRequest was originally called from. You can add
425. [system.util.sendRequestAsync](#systemutilsendrequestasync) - This function is used inPython Scripting. This function sends a message to the Gateway and expects a response. Works in a similar manner to thesendRequestfunction, except sendRequestAsync will send the request and then immediately return a handle for it. The Request handle has the following methods: This scripting function has noClient Permissionrestrictions.
426. [system.util.setConnectTimeout](#systemutilsetconnecttimeout) - This function is used inPython Scripting. Sets the connect timeout for Client-to-Gateway communication. Specified in milliseconds. This scripting function has noClient Permissionrestrictions.
427. [system.util.setConnectionMode](#systemutilsetconnectionmode) - This function is used inPython Scripting. Sets the connection mode for the client session. Normally a client runs in mode 3, which is read-write. You may wish to change this to mode 2, which is read-only, which will only allow reading and subscribing to tags, and running SELECT queries. Tag writes and INSERT/UPDATE/DELETE queries will not function. You can also set the connection mode to mode 1, which is disconnected, all tag and query features will not work. This scripting function has noClient
428. [system.util.setLocale](#systemutilsetlocale) - This function is used inPython Scripting. Sets the user's current Locale. Any valid Java locale code (case-insensitive) can be used as a parameter, including ones that have not yet been added to the Translation Manager. An invalid locale code will cause an Illegal Argument Exception. This scripting function has noClient Permissionrestrictions.
429. [system.util.setLoggingLevel](#systemutilsetlogginglevel) - This function is used inPython Scripting. Sets the logging level on the given logger. This can be a logger you create, or a logger already defined in the system. This scripting function has noClient Permissionrestrictions.
430. [system.util.setReadTimeout](#systemutilsetreadtimeout) - This function is used inPython Scripting. Sets the read timeout for Client-to-Gateway communication. Specified in milliseconds. This scripting function has noClient Permissionrestrictions.
431. [system.util.threadDump](#systemutilthreaddump) - This function is used inPython Scripting. Creates a thread dump of the current running JVM. This scripting function has noClient Permissionrestrictions.
432. [system.util.translate](#systemutiltranslate) - This function is used inPython Scripting. This function allows you to retrieve the global translation of a term from the translation database using the current locale. This scripting function has noClient Permissionrestrictions.
433. [system.vision.getKeyboardLayouts](#systemvisiongetkeyboardlayouts) - This function is used inPython Scripting. Returns a list of keyboard layouts available on this system.
434. [system.vision.updateProject](#systemvisionupdateproject) - This function is used inPython Scripting. Updates the Vision Client project with saved changes. This function is intended to be used in conjunction with the "None" option of Vision Project update modes in the Project Properties, and the Vision Client System TagProjectUpdateAvailable.

---

# system.alarm.acknowledge

**版本：** 8.1
**型別：** Scripting
**分類：** Alarm

## 詳述

This function is used inPython Scripting. Acknowledges any number of alarms, specified by their event ids. The event id is generated for an alarm when it becomes active, and it is used to identify a particular event from other events for the same source. The alarms will be acknowledged by the logged in user making the call. Additionally, acknowledgement notes may be included and will be stored along with the acknowledgement. This function uses different parameters based on the scope of the scrip

## 語法

```python
system.alarm.acknowledge(alarmIds, [notes])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| alarmIds | String[] | List of alarm event ids (uuids) to acknowledge. |
| notes | String | A string that will be used as the Ack Note on each acknowledged alarm event. If set to None , then an Ack Note note will not be assigned to the alarm event |
| alarmIds | List[String] | List of alarm event ids (UUIDs) to acknowledge. |
| notes | String | A string that will be used as the Ack Note on each acknowledged alarm event. If set to None , then an Ack Note note will not be assigned to the alarm event. |
| username | String | The user that acknowledged the alarm. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.alarm.acknowledge(alarmIds, [notes])
```


---

# system.alarm.cancel

**版本：** 8.1
**型別：** Scripting
**分類：** Alarm

## 詳述

This function is used inPython Scripting. Cancels any number of alarm pipelines, specified by their event ids. Event ids can be obtains from thesystem.alarm.queryStatusfunction. Canceling a pipeline will not impact the alarm that triggered the pipeline. The alarm will still be active, but will drop out of alarm pipelines. Permission Type: Alarm Management

## 語法

```python
system.alarm.cancel(alarmIds)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| alarmIds | List[String] | List of alarm pipeline event ids (UUIDs) to cancel. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.alarm.cancel(alarmIds)
```

### Example 3

```python
# This example shows the basic syntax for cancelling an alarm.

system.alarm.cancel(['c27c06d8-698f-4814-af89-3c22944f58c5'])
```


---

# system.alarm.createRoster

**版本：** 8.1
**型別：** Scripting
**分類：** Alarm

## 詳述

This function is used inPython Scripting. This function creates a new roster. Users may be added to the roster through the Gateway or the Roster Management component Permission Type: Alarm Management

## 語法

```python
system.alarm.createRoster(name, description)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| name | String | The name for the new roster |
| description | String | A description for the new roster. Required, but can be blank. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.alarm.createRoster(name, description)
```

### Example 3

```python
description
```


---

# system.alarm.getRosters

**版本：** 8.1
**型別：** Scripting
**分類：** Alarm

## 詳述

This function is used inPython Scripting. This function returns a mapping of roster names to a list of usernames contained in the roster. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.alarm.getRosters()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.alarm.getRosters()
```

### Example 2

```python
# This script will get all the rosters and list the users in them.
rosters = system.alarm.getRosters()
for key, values in rosters.iteritems():
    # key is the roster name, values is a dict of usernames
    print 'Roster', key, 'contains these users:'
    for value in values:
        print '  ', value
```

### Example 3

```python
# This script will get all the rosters and list the users in them.
rosters = system.alarm.getRosters()
for key, values in rosters.iteritems():
    # key is the roster name, values is a dict of usernames
    print 'Roster', key, 'contains these users:'
    for value in values:
        print '  ', value
```


---

# system.alarm.getShelvedPaths

**版本：** 8.1
**型別：** Scripting
**分類：** Alarm

## 詳述

This function is used inPython Scripting. Returns a list of ShelvedPath objects, which each represent a shelved alarm. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.alarm.getShelvedPaths()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.alarm.getShelvedPaths()
```

### Example 2

```python
# The following code prints a list of the shelved alarms paths and prints them to the console.
paths = system.alarm.getShelvedPaths()
for p in paths:
   print "Path: %s, Shelved by: %s, expires: %s, is expired? %s" % (p.getPath(), p.getUser(), p.getExpiration(), p.isExpired())
```

### Example 3

```python
# The following code prints a list of the shelved alarms paths and prints them to the console.
paths = system.alarm.getShelvedPaths()
for p in paths:
   print "Path: %s, Shelved by: %s, expires: %s, is expired? %s" % (p.getPath(), p.getUser(), p.getExpiration(), p.isExpired())
```


---

# system.alarm.listPipelines

**版本：** 8.1
**型別：** Scripting
**分類：** Alarm

## 詳述

This function is used inPython Scripting. Will return a list of the available Alarm Notification Pipelines in a project. The order of the returned list is not guaranteed. The legacy behavior of this function (7.9 and prior) did not have any parameters, and it would always check all projects for pipelines. Upon upgrade to version 8.#+, alarm pipelines were migrated to a project named "alarm-pipelines". See theUpgrade Guidefor more details.

## 語法

```python
system.alarm.listPipelines([projectName])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| projectName | String | The project to check alarm pipelines for. If omitted, will look for a project named "alarm-pipelines". [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.alarm.listPipelines([projectName])
```

### Example 2

```python
projectName
```

### Example 3

```python
# This script will print a list of all alarm pipeline names in the current project.
project = system.util.getProjectName()
pipelines = system.alarm.listPipelines(project)
for pipeline in pipelines:
    print pipeline
```


---

# system.alarm.queryJournal

**版本：** 8.1
**型別：** Scripting
**分類：** Alarm

## 詳述

This function is used inPython Scripting. Queries the specified journal for historical alarm events. The result is a list of alarm events, which can be parsed for individual properties. Click herefor more information on alarm properties.

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| startDate | Date | The start of the time range to query. Defaults to 8 hours previous to now if omitted. Time range is inclusive. [optional] |
| endDate | Date | The end of the time range to query. Defaults to now if omitted. [optional] |
| journalName | String | The journal name to query. If only one journal exists on the Gateway, can be omitted. [optional] |
| priority | List[Integer/String] | A list of possible priorities to match. Priorities can be specified by name or number, with the values: Diagnostic(0), Low(1), Medium(2), High(3), Critical(4). [optional] |
| state | List[Integer/String] | A list of event states to match. Valid values can either be integers or strings, representing a number of states. SeeState Parameter Valuesfor a listing of possible values. [optional] |
| path | List[String] | A list of possible source paths to search at. The wildcard*may be used. [optional] |
| source | List[String] | A list of possible source paths to search at. The wildcard*may be used. [optional] |
| displaypath | List[String] | A list of display paths to search at. Display paths are separated by/, and if a path ends in/*, everything below that path will be searched as well. [optional] |
| all_properties | List[Tuple[String, String, Any]] | A set of property conditions, all of which must be met for the condition to pass. This parameter is a list of tuples, in the form (propName,condition, value). Valid propName values can be either associated data or the keys listed on thePyAlarmEvent object. Valid condition values:=,!=,<,<=,>,>=. String values can only be compared using=and!=conditions. [optional] |
| any_properties | List[Tuple[String, String, Any]] | A set of property conditions, any of which will cause the overall condition to pass. This parameter is a list of tuples, in the form (propName,condition, value). Valid propName values can be either associated data or the keys listed on thePyAlarmEvent object. Valid condition values:=,!=,<,<=,>,>=. String values can only be compared using=and!=conditions. [optional] |
| defined | List[String] | A list of string property names, all of which must be present on an event for it to pass. [optional] |
| includeData | Boolean | Whether or not event data should be included in the return. If True, returns Python dictionaries (or nulls) for Active, Clear, Ack, Event Value, and Runtime data inside of the AlarmQueryResult object. Not required when definingall_propertiesorany_properties. [optional]SeeExample #6below for how to return Event Value data. |
| includeSystem | Boolean | Specifies whether system events are included in the return. [optional] |
| includeShelved | Boolean | A flag indicating whether shelved events should be included in the results. Defaults to false. [optional] |
| isSystem | Boolean | Specifies whether the returned event must or must not be a system event. [optional] |
| provider | List[String] | A list of tag providers to include in the query. Omitting this parameter will query all providers. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.alarm.queryJournal([startDate], [endDate], [journalName], [priority], [state], [path], [source], [displaypath], [all_properties], [any_properties], [defined], [includeData], [includeSystem], [includeShelved], [isSystem], [provider])
```


---

# system.alarm.queryStatus

**版本：** 8.1
**型別：** Scripting
**分類：** Alarm

## 詳述

This function is used inPython Scripting. Queries the current state of alarms. The result is a list of alarm events, which can be parsed for individual properties. The results provided by this function represent the current state of alarms, in contrast to the historical alarm events retrieved by thesystem.alarm.queryJournalfunction. Depending on the number of alarm events in the system, this function can be fairly intensive and take a while to finish executing. This can be problematic if the app

## 語法

```python
system.alarm.queryStatus([priority], [state], [path], [source], [displaypath], [all_properties], [any_properties], [defined], [includeShelved], [provider])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| priority | List[Integer/String] | A list of possible priorities to match. Priorities can be specified by name or number, with the values: Diagnostic(0), Low(1), Medium(2), High(3), Critical(4). [optional] |
| state | List[Integer/String] | A list of states to allow. SeeState Valuesfor a list of options. [optional] |
| path | List[String] | A list of possible source paths to search at. The wildcard*may be used. Works the same as the source argument, and either can be used. [optional] |
| source | List[String] | A list of possible source paths to search at. The wildcard*may be used. Works the same as the path argument, and either can be used. [optional] |
| displaypath | List[String] | A list of display paths to search at. Display paths are separated by/, and if a path ends in/*, everything below that path will be searched as well. [optional] |
| all_properties | List[Tuple[String, String, Any]] | A set of property conditions, all of which must be met for the condition to pass. This parameter is a list of tuples, in the form (propName,condition, value). Valid propName values can be either associated data or the keys listed on thePyAlarmEvent object. Valid condition values:=,!=,<,<=,>,>=. String values can only be compared using=and!=conditions. [optional] |
| any_properties | List[Tuple[String, String, Any]] | A set of property conditions, any of which will cause the overall condition to pass. This parameter is a list of tuples, in the form (propName,condition, value). Valid propName values can be either associated data or the keys listed on thePyAlarmEvent object. Valid condition values:=,!=,<,<=,>,>=. String values can only be compared using=and!=conditions.  [optional] |
| defined | List[String] | A list of string property names, all of which must be present on an event for it to pass. [optional] |
| includeShelved | Boolean | A flag indicating whether shelved events should be included in the results. Defaults to false. [optional] |
| provider | List[String] | A list of tag providers to include in the query. Omitting this parameter will query all providers. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.alarm.queryStatus([priority], [state], [path], [source], [displaypath], [all_properties], [any_properties], [defined], [includeShelved], [provider])
```


---

# system.alarm.shelve

**版本：** 8.1
**型別：** Scripting
**分類：** Alarm

## 詳述

This function is used inPython Scripting. This function shelves the specified alarms for the specified amount of time. The time can be specified in minutes (timeoutMinutes) or seconds (timeoutSeconds). If an alarm is already shelved, this will overwrite the remaining time. If no timeout is specified, will default to 15 minutes. Client Permission: Alarm Management

## 語法

```python
system.alarm.shelve(path, [timeoutSeconds], [timeoutMinutes])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| path | List[String] | A list of possible source paths to search at. If a path ends in "/*", the results will include anything below that path. |
| timeoutSeconds | Integer | The amount of time to shelve the matching alarms for, specified in seconds. Setting this to 0 will unshelve the alarms. [optional] |
| timeoutMinutes | Integer | The amount of time to shelve the matching alarms for, specified in minutes. Setting this to 0 will unshelve the alarms. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.alarm.shelve(path, [timeoutSeconds], [timeoutMinutes])
```

### Example 3

```python
timeoutSeconds
```


---

# system.alarm.unshelve

**版本：** 8.1
**型別：** Scripting
**分類：** Alarm

## 詳述

This function is used inPython Scripting. Unshelves a list of alarms based on the source paths provided. Client Permission: Alarm Management

## 語法

```python
system.alarm.unshelve(path)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| path | List[String] | A list of possible source paths to search at. If a path ends in "/*", the results will include anything below that path. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.alarm.unshelve(path)
```

### Example 3

```python
# Unshelve an Alarm at a Path

testPath = "prov:TAG_PROVIDER_NAME:/tag:TAG_PATH:/alm:ALARM_NAME"
system.alarm.unshelve(path= [testPath])
```


---

# system.bacnet.readRaw

**版本：** 8.1
**型別：** Scripting
**分類：** Bacnet

## 詳述

This function is used inPython Scripting. Read from any BACnet object not explicitly supported by the BACnet driver. To use this function, theBACnetdriver must be installed.

## 語法

```python
system.bacnet.readRaw(deviceName, objectType, objectId, propertyId, [propertyArrayIndex])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the configured BACnet/IP device instance to read from. |
| objectType | ObjectType | The numeric id of the objectType of the object instance being read from. See the objectType Reference below. |
| objectId | Integer | The object instance number to read. |
| propertyId | PropertyIdentifier | The PropertyIdentifier of the object instance being read. See the propertyId Reference below. |
| propertyArrayIndex | Integer | [optional] The array index of the property to read from. This parameter is optional and should not be used when reading from the entire array or if the property is not an array. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.bacnet.readRaw(deviceName, objectType, objectId, propertyId, [propertyArrayIndex])
```


---

# system.bacnet.readRawMultiple

**版本：** 8.1
**型別：** Scripting
**分類：** Bacnet

## 詳述

This function is used inPython Scripting. This function is the bulk version ofsystem.bacnet.readRawto allow multiple object/property combinations to be read simultaneously from a single request. Returns a list of corresponding Encodable objects provided equal-length lists of object types, object instance numbers, property IDs, and property array indices. To use this function, theBACnetdriver must be installed.

## 語法

```python
system.bacnet.readRawMultiple(deviceName, objectTypes, objectIds, propertyIds)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the configured BACnet/IP device instance to read from. |
| objectTypes | ObjectTypes | The numeric ids of the objectType of the object instances being read from. See the objectType Reference below. |
| objectIds | Integer | The object instance number to read. |
| propertyIds | PropertyIdentifier | The PropertyIdentifier of the object instance being read. See the propertyId Reference below. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.bacnet.readRawMultiple(deviceName, objectTypes, objectIds, propertyIds)
```

### Example 3

```python
objectTypes
```


---

# system.bacnet.synchronizeTime

**版本：** 8.1
**型別：** Scripting
**分類：** Bacnet

## 詳述

This function is used inPython Scripting. Notifies the remote device of the correct current time, which is the system time (factoring in time zone and DST) of the server Ignition is running on. To use this function, theBACnetdriver must be installed.

## 語法

```python
system.bacnet.synchronizeTime(deviceName)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the configured BACnet/IP device instance to write from. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.bacnet.synchronizeTime(deviceName)
```

### Example 3

```python
deviceName = "BACnet Remote"
system.bacnet.synchronizeTime(deviceName)
```


---

# system.bacnet.synchronizeTimeUtc

**版本：** 8.1
**型別：** Scripting
**分類：** Bacnet

## 詳述

This function is used inPython Scripting. Notifies the remote device of the correct current time in UTC. To use this function, theBACnetdriver must be installed.

## 語法

```python
system.bacnet.synchronizeTimeUtc(deviceName)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the configured BACnet/IP device instance to write from. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.bacnet.synchronizeTimeUtc(deviceName)
```

### Example 3

```python
deviceName = "BACnet Remote"
system.bacnet.synchronizeTimeUtc(deviceName)
```


---

# system.bacnet.writeRaw

**版本：** 8.1
**型別：** Scripting
**分類：** Bacnet

## 詳述

This function is used inPython Scripting. Write to any BACnet object not explicitly supported by the BACnet driver.

## 語法

```python
system.bacnet.writeRaw(deviceName, objectType, objectId, propertyId, value, [priority], [propertyArrayIndex])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the configured BACnet/IP device instance to write from. |
| objectType | ObjectType | The numeric id of the objectType of the object instance being written to. See the objectType Reference below. |
| objectId | Integer | The object instance number to write to. |
| propertyId | PropertyIdentifier | The PropertyIdentifier of the object instance being written to. See the propertyId Reference below. |
| value | Object | The value to write. Clearing a value can be accomplished by writing a None value. |
| priority | Integer | [optional] The priority level to use when writing to commandable properties. Must match a level in the standard BACnet priority array (a value from 1 to 16). See the Priority Reference table below. This parameter is optional and defaults to 8 if not specified. |
| propertyArrayIndex | Integer | [optional] The array index of the property to write to. This parameter is optional and should not be used when writing to the entire array or if the property is not an array. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.bacnet.writeRaw(deviceName, objectType, objectId, propertyId, value, [priority], [propertyArrayIndex])
```


---

# system.bacnet.writeRawMultiple

**版本：** 8.1
**型別：** Scripting
**分類：** Bacnet

## 詳述

This function is used inPython Scripting. This function is the bulk version ofsystem.bacnet.writeRawby writing properties to objects provided equal-length lists of object types, object instance numbers, property IDs, values, priorities, and property array indices. The system.bacnet.writeRawMultiple() function will accept Encodable values on the value parameter.

## 語法

```python
system.bacnet.writeRawMultiple(deviceName, objectTypes, objectIds, propertyIds, values, [priorities], [propertyArrayIndices])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | Name of the configured BACnet/IP device instance to write from. |
| objectTypes | ObjectType | A list of ObjectType(s) for the object instance being written to. |
| objectIds | Integer | A list of object instance numbers to write to. |
| propertyIds | PropertyIdentifier | A list of PropertyIdentifier(s) for the object instances being written to. |
| values | Object | A list of values to write. |
| priorities[optional] | Integer | An optional list of priority levels to use when writing to commandable properties. All elements must be in the range [1..16]. Defaults to 8 for all properties when this parameter is omitted. |
| propertyArrayIndices[optional] | Integer | An optional list of array indices corresponding to array properties being written. None should be specified as an element when writing to the entire array property or if the property is not an array. Defaults to a list of None when this parameter is omitted. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.bacnet.writeRawMultiple(deviceName, objectTypes, objectIds, propertyIds, values, [priorities], [propertyArrayIndices])
```

### Example 3

```python
objectTypes
```


---

# system.bacnet.writeWithPriority

**版本：** 8.1
**型別：** Scripting
**分類：** Bacnet

## 詳述

This function is used inPython Scripting. Write to the Present_Value attribute of an object with a custom priority level. To use this function, theBACnetdriver must be installed.

## 語法

```python
system.bacnet.writeWithPriority(deviceName, objectType, objectId, value, priority)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the configured BACnet/IP device instance to write from. |
| objectType | Integer | The numeric id of the objectType of the object instance being written to. See the objectType Reference table below. |
| objectId | Integer | The object instance number to write to. |
| value | Object | The value to write. Clearing a value can be accomplished by writing a None value. |
| priority | Integer | The priority level to write the value at. Must match a level in the standard BACnet priority array (a value from 1 to 16). See the Priority Reference table below. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.bacnet.writeWithPriority(deviceName, objectType, objectId, value, priority)
```


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

# system.date.*Between

**版本：** 8.1
**型別：** Scripting
**分類：** Date

## 詳述

This function is used inPython Scripting. This function is a set of functions that include: Order matters when passing in the two dates required by this function. system.date.*Between will subtract the first date from the second date, meaning if date 2 is further in time than date 1, then a positive amount of time has passed. If date 2 is backwards in time from date 1, then a negative amount of time has passed.

## 語法

```python
system.date.*Between(date_1, date_2)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| date_1 | Date | The first date to use. |
| date_2 | Date | The second date to use. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.date.*Between(date_1, date_2)
```


---

# system.date.add*

**版本：** 8.1
**型別：** Scripting
**分類：** Date

## 詳述

This function is used inPython Scripting. This function is a set of functions that include: This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.date.add*(date, value)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| date | Date | The starting date. |
| value | Integer | The number of units to add, or subtract if the value is negative. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.date.add*(date, value)
```


---

# system.date.format

**版本：** 8.1
**型別：** Scripting
**分類：** Date

## 詳述

This function is used inPython Scripting. Returns the given date as a string and formatted according to a pattern. The pattern is a format that is full of various placeholders that display different parts of the date. These are case-sensitive. These placeholders can be repeated for a different effect. For example, M will give you 1-12, MM will give you 01-12, MMM will give you Jan-Dec, MMMM will give you January-December. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.date.format(date, format)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| date | Date | The date to format. |
| format | String | A format string such as "yyyy-MM-dd HH:mm:ss". The format argument is optional. The default is "yyyy-MM-dd HH:mm:ss". Refer toData Type Formatting Referencefor a table of acceptable symbols. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.date.format(date, format)
```


---

# system.date.fromMillis

**版本：** 8.1
**型別：** Scripting
**分類：** Date

## 詳述

This function is used inPython Scripting. Creates a date object given a millisecond value. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.date.fromMillis(millis)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| millis | Long | The number of milliseconds elapsed since January 1, 1970, 00:00:00 UTC (GMT) |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.date.fromMillis(millis)
```

### Example 3

```python
# This example will print out the date "Fri Aug 18 14:35:25 PDT 2017"
print system.date.fromMillis(1503092125000)
```


---

# system.date.get*

**版本：** 8.1
**型別：** Scripting
**分類：** Date

## 詳述

This function is used inPython Scripting. This function is a set of functions that include: This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.date.get*(date)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| date | Date | The date to use. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.date.get*(date)
```

### Example 3

```python
# This example would grab the current time, and print the current month.

date = system.date.now()
print system.date.getMonth(date) #This would print the current month.
```


---

# system.date.getDate

**版本：** 8.1
**型別：** Scripting
**分類：** Date

## 詳述

This function is used inPython Scripting. Creates a new Date object given a year, month and a day. The time will be set to midnight of that day. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.date.getDate(year, month, day)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| year | Integer | The year for the new date. |
| month | Integer | The month of the new date. January is month 0. |
| day | Integer | The day of the month for the new date. The first day of the month is day 1. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.date.getDate(year, month, day)
```


---

# system.date.getTimezone

**版本：** 8.1
**型別：** Scripting
**分類：** Date

## 詳述

This function is used inPython Scripting. Returns the ID of the current timezone. If your Client and Gateway are in different time zones, the returned value will be dependent on where this script is run. IE: in a button on a client will return the Client time zone. On a Gateway script (including Perspective scripts), the function will return the Gateway time zone.

## 語法

```python
system.date.getTimezone()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.date.getTimezone()
```

### Example 2

```python
# This example will print out your current Timezone.

print system.date.getTimezone()
```

### Example 3

```python
# This example will print out your current Timezone.

print system.date.getTimezone()
```


---

# system.date.getTimezoneOffset

**版本：** 8.1
**型別：** Scripting
**分類：** Date

## 詳述

This function is used inPython Scripting. Returns the current timezone's offset versus UTC for a given instant, taking Daylight Savings Time into account. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.date.getTimezoneOffset([date])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| date | Date | The instant in time for which to calculate the offset. Uses now() if omitted. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.date.getTimezoneOffset([date])
```

### Example 3

```python
# This example will give the time zone offset using the date February 22, 2021
# and the computers current time zone.

date = system.date.getDate(2021, 1, 22)
print system.date.getTimezoneOffset(date) # returns -8.0 (if you are in Pacific Daylight Time)
```


---

# system.date.getTimezoneRawOffset

**版本：** 8.1
**型別：** Scripting
**分類：** Date

## 詳述

This function is used inPython Scripting. Returns the current timezone offset versus UTC, not taking daylight savings into account. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.date.getTimezoneRawOffset()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.date.getTimezoneRawOffset()
```

### Example 2

```python
# This example will give the Raw timezone offset (ignoring daylight savings) for the computers current timezone.

print system.date.getTimezoneRawOffset() # returns -8.0 (if you are in the Pacific Timezone)
```

### Example 3

```python
# This example will give the Raw timezone offset (ignoring daylight savings) for the computers current timezone.

print system.date.getTimezoneRawOffset() # returns -8.0 (if you are in the Pacific Timezone)
```


---

# system.date.isAfter

**版本：** 8.1
**型別：** Scripting
**分類：** Date

## 詳述

This function is used inPython Scripting. Compares two dates to see if date_1 is after date_2. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.date.isAfter(date_1, date_2)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| date_1 | Date | The first date. |
| date_2 | Date | The second date. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.date.isAfter(date_1, date_2)
```


---

# system.date.isBefore

**版本：** 8.1
**型別：** Scripting
**分類：** Date

## 詳述

This function is used inPython Scripting. Compares two dates to see if date_1 is before date_2. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.date.isBefore(date_1, date_2)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| date_1 | Date | The first date. |
| date_2 | Date | The second date. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.date.isBefore(date_1, date_2)
```


---

# system.date.isBetween

**版本：** 8.1
**型別：** Scripting
**分類：** Date

## 詳述

This function is used inPython Scripting. Compares two dates to see if a target date is between two other dates; checks to see if the target date is between the other two dates. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.date.isBetween(target_date, start_date, end_date)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| target_date | Date | The date to compare. |
| start_date | Date | The start of a date range. |
| end_date | Date | The end of a date range. This date must be after the start date. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.date.isBetween(target_date, start_date, end_date)
```

### Example 2

```python
target_date
```


---

# system.date.isDaylightTime

**版本：** 8.1
**型別：** Scripting
**分類：** Date

## 詳述

This function is used inPython Scripting. Checks to see if the current timezone is using daylight savings time during the date specified. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.date.isDaylightTime([date])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| date | Date | The date you want to check if the current timezone is observing daylight savings time. Uses now() if omitted. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.date.isDaylightTime([date])
```

### Example 3

```python
date = system.date.getDate(2018, 6, 28)
print system.date.isDaylightTime(date) #Will print True in the US Pacific time zone.
```


---

# system.date.midnight

**版本：** 8.1
**型別：** Scripting
**分類：** Date

## 詳述

This function is used inPython Scripting. Returns a copy of a date with the hour, minute, second, and millisecond fields set to zero. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.date.midnight(date)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| date | Date | The starting date. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.date.midnight(date)
```

### Example 3

```python
# This example prints out the current date with the time set to midnight.

date = system.date.now()
print system.date.midnight(date)
```


---

# system.date.now

**版本：** 8.1
**型別：** Scripting
**分類：** Date

## 詳述

This function is used inPython Scripting. Returns a java.util.Date object that represents the current time according to the local system clock. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.date.now()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.date.now()
```

### Example 2

```python
# This example will set a calendar component to the current date and time.

event.source.parent.getComponent('Calendar').date = system.date.now()
```

### Example 3

```python
# This example will set a calendar component to the current date and time.

event.source.parent.getComponent('Calendar').date = system.date.now()
```


---

# system.date.parse

**版本：** 8.1
**型別：** Scripting
**分類：** Date

## 詳述

This function is used inPython Scripting. Attempts to parse a string and create a Date. Causes ParseException if the date dateString parameter is in an unrecognized format. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.date.parse(dateString, [formatString], [locale])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| dateString | String | The string to parse into a date. |
| formatString | String | Format string used by the parser. Default is "yyyy-MM-dd HH:mm:ss" Refer toData Type Formatting Reference. [optional] |
| locale | Object | Locale used for parsing. Can be the locale name such as 'fr', or the Java Locale such as 'Locale.French'. Default is 'Locale.English'. Refer toJava Locale. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.date.parse(dateString, [formatString], [locale])
```

### Example 3

```python
formatString
```


---

# system.date.setTime

**版本：** 8.1
**型別：** Scripting
**分類：** Date

## 詳述

This function is used inPython Scripting. Takes in a date, and returns a copy of it with the time fields set as specified. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.date.setTime(date, hour, minute, second)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| date | Date | The starting date. |
| hour | Integer | The hours (0-23) to set. |
| minute | Integer | The minutes (0-59) to set. |
| second | Integer | The seconds (0-59) to set. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.date.setTime(date, hour, minute, second)
```


---

# system.date.toMillis

**版本：** 8.1
**型別：** Scripting
**分類：** Date

## 詳述

This function is used inPython Scripting. Converts a Date object to its millisecond value elapsed since January 1, 1970, 00:00:00 UTC (GMT) This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.date.toMillis(date)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| date | Date | The date object to convert. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.date.toMillis(date)
```

### Example 3

```python
# This example takes the date Fri Aug 18 14:35:25 PDT 2017,
# and prints it out 1503092125000.

date = system.date.getDate(2017, 7, 18)
datetime = system.date.setTime(date, 14, 35, 25)
print system.date.toMillis(datetime)
```


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

# system.dnp.demandPoll

**版本：** 8.1
**型別：** Scripting
**分類：** Dnp

## 詳述

The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Issues a poll request for one or more classes.

## 語法

```python
system.dnp.demandPoll(deviceName, classList)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the DNP3 device instance. |
| classList | List | A List of classes (1, 2, 3) to issue polls. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dnp.demandPoll(deviceName, classList)
```


---

# system.dnp.directOperateAnalog

**版本：** 8.1
**型別：** Scripting
**分類：** Dnp

## 詳述

The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Performs a Direct Operate command on an analog point.

## 語法

```python
system.dnp.directOperateAnalog(deviceName, variation, index, value)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the DNP3 device instance. |
| variation | Integer | The Group 41 variation to use during the operation. |
| index | Integer | The index of the analog point. |
| value | Numeric | The requested value. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dnp.directOperateAnalog(deviceName, variation, index, value)
```


---

# system.dnp.directOperateBinary

**版本：** 8.1
**型別：** Scripting
**分類：** Dnp

## 詳述

The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Performs a Direct Operate command on a binary point.

## 語法

```python
system.dnp.directOperateBinary(deviceName, index, tcc, opType, count, onTime, offTime)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the DNP3 device instance. |
| index | Integer | The index of the binary point. |
| tcc | Integer | Trip Close Code: 0=NUL, 1=CLOSE, 2=TRIP. |
| opType | Integer | Operation Type: 0=NUL, 1=PULSE_ON, 2=PULSE_OFF, 3=LATCH_ON, 4=LATCH_OFF. |
| count | Integer | The number of times the outstation shall execute the operation. |
| onTime | Integer | Duration (in milliseconds) the output drive remains active. |
| offTime | Integer | Duration (in milliseconds) the output drive remains non-active. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dnp.directOperateBinary(deviceName, index, tcc, opType, count, onTime, offTime)
```


---

# system.dnp.freezeAnalogs

**版本：** 8.1
**型別：** Scripting
**分類：** Dnp

## 詳述

The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Issues an Immediate Freeze command targeting one or more analog points.

## 語法

```python
system.dnp.freezeAnalogs(deviceName, indexes)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the DNP3 device instance. |
| indexes | List | The indices of the analog points to freeze. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dnp.freezeAnalogs(deviceName, indexes)
```


---

# system.dnp.freezeAtTimeAnalogs

**版本：** 8.1
**型別：** Scripting
**分類：** Dnp

## 詳述

The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Issues a Freeze at Time command targeting one or more analog points.

## 語法

```python
system.dnp.freezeAtTimeAnalogs(deviceName, absoluteTime, intervalTime, indexes)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the DNP3 device instance. |
| absoluteTime | Long | Absolute time (in milliseconds since epoch UTC) when the initial action should occur. |
| intervalTime | Long | Interval time (in milliseconds) between periodic actions. |
| indexes | List | The indices of the analog points to freeze. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dnp.freezeAtTimeAnalogs(deviceName, absoluteTime, intervalTime, indexes)
```

### Example 3

```python
absoluteTime
```


---

# system.dnp.freezeAtTimeCounters

**版本：** 8.1
**型別：** Scripting
**分類：** Dnp

## 詳述

The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Issues a Freeze at Time command targeting one or more counters.

## 語法

```python
system.dnp.freezeAtTimeCounters(deviceName, absoluteTime, intervalTime, indexes)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the DNP3 device instance. |
| absoluteTime | Long | Absolute time (in milliseconds since epoch UTC) when the initial action should occur. |
| intervalTime | Long | Interval time (in milliseconds) between periodic actions. |
| indexes | List | The indices of the counters to freeze. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dnp.freezeAtTimeCounters(deviceName, absoluteTime, intervalTime, indexes)
```

### Example 3

```python
absoluteTime
```


---

# system.dnp.freezeClearAnalogs

**版本：** 8.1
**型別：** Scripting
**分類：** Dnp

## 詳述

The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Issues a Freeze and Clear command targeting one or more analog points.

## 語法

```python
system.dnp.freezeClearAnalogs(deviceName, indexes)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the DNP3 device instance. |
| indexes | List | The indices of the analog points to freeze. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dnp.freezeClearAnalogs(deviceName, indexes)
```


---

# system.dnp.freezeClearCounters

**版本：** 8.1
**型別：** Scripting
**分類：** Dnp

## 詳述

The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Issues a Freeze and Clear command targeting one or more counters.

## 語法

```python
system.dnp.freezeClearCounters(deviceName, indexes)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the DNP3 device instance. |
| indexes | List | The indices of the counters to freeze. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dnp.freezeClearCounters(deviceName, indexes)
```


---

# system.dnp.freezeCounters

**版本：** 8.1
**型別：** Scripting
**分類：** Dnp

## 詳述

The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Issues an Immediate Freeze command targeting one or more counters.

## 語法

```python
system.dnp.freezeCounters(deviceName, indexes)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the DNP3 device instance. |
| indexes | List | The indices of the counters to freeze. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dnp.freezeCounters(deviceName, indexes)
```


---

# system.dnp.selectOperateAnalog

**版本：** 8.1
**型別：** Scripting
**分類：** Dnp

## 詳述

The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Performs a Select then Operate command on an analog point.

## 語法

```python
system.dnp.selectOperateAnalog(deviceName, variation, index, value)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the DNP3 device instance. |
| variation | Integer | The Group 41 variation to use during the operation. |
| index | Integer | The index of the analog point. |
| value | Numeric | The requested value. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dnp.selectOperateAnalog(deviceName, variation, index, value)
```


---

# system.dnp.selectOperateBinary

**版本：** 8.1
**型別：** Scripting
**分類：** Dnp

## 詳述

The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Performs a Select then Operate command on a binary point.

## 語法

```python
system.dnp.selectOperateBinary(deviceName, index, tcc, opType, count, onTime, offTime)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the DNP3 device instance. |
| index | Integer | The index of the binary point. |
| tcc | Integer | Trip Close Code: 0=NUL, 1=CLOSE, 2=TRIP. |
| opType | Integer | Operation Type: 0=NUL, 1=PULSE_ON, 2=PULSE_OFF, 3=LATCH_ON, 4=LATCH_OFF. |
| count | Integer | The number of times the outstation shall execute the operation. |
| onTime | Integer | Duration (in milliseconds) the output drive remains active. |
| offTime | Integer | Duration (in milliseconds) the output drive remains non-active. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dnp.selectOperateBinary(deviceName, index, tcc, opType, count, onTime, offTime)
```


---

# system.dnp.synchronizeTime

**版本：** 8.1
**型別：** Scripting
**分類：** Dnp

## 詳述

The following function usessystem.dnpand theDNP3 driver. Forsystem.dnp3functions and theLegacy DNP3 driver, seeDNP3. This function is used inPython Scripting. Issues a Synchronize Time command using the current Ignition Gateway time.

## 語法

```python
system.dnp.synchronizeTime(deviceName)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the DNP3 device instance. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dnp.synchronizeTime(deviceName)
```

### Example 3

```python
system.dnp.synchronizeTime("DNP3")
```


---

# system.dnp3.directOperateAnalog

**版本：** 8.1
**型別：** Scripting
**分類：** Dnp3

## 詳述

The following function usessystem.dnp3and theLegacy DNP3 driver. Seesystem.dnpforDNP3functions using theDNP3 driver. This function is used inPython Scripting. Issues a Select-And-Operate command to set an analog value in an analog output point.

## 語法

```python
system.dnp3.directOperateAnalog(deviceName, index, value, [variation])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the DNP3 device driver. |
| index | Integer | The index of the object to be modified in the outstation. |
| value | Numeric | The analog value that is requested (of type int, short, float, or double). |
| variation | Integer | The DNP3 object variation to use in the request. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dnp3.directOperateAnalog(deviceName, index, value, [variation])
```


---

# system.dnp3.directOperateBinary

**版本：** 8.1
**型別：** Scripting
**分類：** Dnp3

## 詳述

The following function usessystem.dnp3and theLegacy DNP3 driver. Seesystem.dnpforDNP3functions using theDNP3 driver. This function is used inPython Scripting. Issues a Direct-Operate command for digital control operations at binary output points (CROB).

## 語法

```python
system.dnp3.directOperateBinary(deviceName, indexes, opType, tcCode, count, onTime, offTime)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the DNP3 device driver. |
| indexes | List | A list of indexes of the objects to be modified in the outstation. |
| opType | Integer | The type of the operation. 0=NUL, 1=PULSE_ON, 2=PULSE_OFF, 3=LATCH_ON, 4=LATCH_OFF |
| tcCode | Integer | The Trip-Close code, used in conjunction with the opType. 0=NUL, 1=CLOSE, 2=TRIP |
| count | Integer | The number of times the outstation shall execute the operation. |
| onTime | Long | The duration that the output drive remains active, in millis. [optional] |
| offTime | Long | The duration that the output drive remains non-active, in millis. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dnp3.directOperateBinary(deviceName, indexes, opType, tcCode, count, onTime, offTime)
```


---

# system.dnp3.freezeAnalogs

**版本：** 8.1
**型別：** Scripting
**分類：** Dnp3

## 詳述

The following function usessystem.dnp3and theLegacy DNP3 driver. Seesystem.dnpforDNP3functions using theDNP3 driver. This function is used inPython Scripting. Issues a freeze command on the given analog outputs.

## 語法

```python
system.dnp3.freezeAnalogs(deviceName, [indexes])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the DNP3 device driver. |
| indexes | List | A list of specific indexes on which to issue the freeze command. An empty list can be passed to freeze all analogs. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dnp3.freezeAnalogs(deviceName, [indexes])
```


---

# system.dnp3.freezeAnalogsAtTime

**版本：** 8.1
**型別：** Scripting
**分類：** Dnp3

## 詳述

The following function usessystem.dnp3and theLegacy DNP3 driver. Seesystem.dnpforDNP3functions using theDNP3 driver. This function is used inPython Scripting. Issues a freeze command on the given analog outputs at the given time for the specified duration.

## 語法

```python
system.dnp3.freezeAnalogsAtTime(deviceName, absoluteTime, intervalTime, indexes)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the DNP3 device driver. |
| absoluteTime | Integer | The absolute time at which to freeze, in millis. |
| intervalTime | Integer | The interval at which to periodically freeze, in millis. |
| indexes | List | A list of specific indexes on which to issue the freeze command. An empty list will freeze all points. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dnp3.freezeAnalogsAtTime(deviceName, absoluteTime, intervalTime, indexes)
```

### Example 3

```python
absoluteTime
```


---

# system.dnp3.freezeCounters

**版本：** 8.1
**型別：** Scripting
**分類：** Dnp3

## 詳述

The following function usessystem.dnp3and theLegacy DNP3 driver. Seesystem.dnpforDNP3functions using theDNP3 driver. This function is used inPython Scripting. Issues a freeze command on the given counters.

## 語法

```python
system.dnp3.freezeCounters(deviceName, [indexes])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the DNP3 device driver. |
| indexes | List | A list of specific indexes on which to issue the freeze command. An empty list can be passed to freeze all counters. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dnp3.freezeCounters(deviceName, [indexes])
```


---

# system.dnp3.freezeCountersAtTime

**版本：** 8.1
**型別：** Scripting
**分類：** Dnp3

## 詳述

The following function usessystem.dnp3and theLegacy DNP3 driver. Seesystem.dnpforDNP3functions using theDNP3 driver. This function is used inPython Scripting. Issues a freeze command on the given counters at the given time for the specified duration.

## 語法

```python
system.dnp3.freezeCountersAtTime(deviceName, absoluteTime, intervalTime, indexes)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the DNP3 device driver. |
| absoluteTime | Integer | The absolute time at which to freeze, in millis. |
| intervalTime | Integer | The interval at which to periodically freeze, in millis. |
| indexes | List | A list of specific indexes on which to issue the freeze command. An empty list will freeze all counters. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dnp3.freezeCountersAtTime(deviceName, absoluteTime, intervalTime, indexes)
```

### Example 3

```python
absoluteTime
```


---

# system.dnp3.selectOperateAnalog

**版本：** 8.1
**型別：** Scripting
**分類：** Dnp3

## 詳述

The following function usessystem.dnp3and theLegacy DNP3 driver. Seesystem.dnpforDNP3functions using theDNP3 driver. This function is used inPython Scripting. Issues a Select-And-Operate command to set an analog value in an analog output point.

## 語法

```python
system.dnp3.selectOperateAnalog(deviceName, index, value, [variation])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the DNP3 device driver. |
| index | Integer | The index of the object to be modified in the outstation. |
| value | Numeric | The analog value that is requested (of type int, short, float, or double). |
| variation | Integer | The DNP3 object variation to use in the request. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dnp3.selectOperateAnalog(deviceName, index, value, [variation])
```


---

# system.dnp3.selectOperateBinary

**版本：** 8.1
**型別：** Scripting
**分類：** Dnp3

## 詳述

The following function usessystem.dnp3and theLegacy DNP3 driver. Seesystem.dnpforDNP3functions using theDNP3 driver. This function is used inPython Scripting. Issues a Select-And-Operate command for digital control operations at binary output points (CROB).

## 語法

```python
system.dnp3.selectOperateBinary(deviceName, indexes, opType, tcCode, [count], [onTime], [offTime])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of theDNP3 driver. |
| indexes | List | A list of indexes of the objects to be modified in the outstation. |
| opType | Integer | The type of operation. 0=NUL, 1=PULSE_ON, 2=PULSE_OFF, 3=LATCH_ON, 4=LATCH_OFF |
| tcCode | Integer | The Trip-Close code, used in conjunction with the opType. 0=NUL, 1=CLOSE, 2=TRIP |
| count | Integer | The number of times the outstation shall execute the operation. [optional] |
| onTime | Integer | The duration that the output drive remains active, in millis. [optional] |
| offTime | Integer | The duration that the output drive remains non-active, in millis. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.dnp3.selectOperateBinary(deviceName, indexes, opType, tcCode, [count], [onTime], [offTime])
```


---

# system.eam.getGroups

**版本：** 8.1
**型別：** Scripting
**分類：** Eam

## 詳述

This function is used inPython Scripting. Returns the names of the defined agent organizational groups in the Gateway. This function can only be called from the Controller. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.eam.getGroups()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.eam.getGroups()
```

### Example 2

```python
# Return and print all of the EAM groups
groups = system.eam.getGroups()
for group in groups:
    print group
```

### Example 3

```python
# Return and print all of the EAM groups
groups = system.eam.getGroups()
for group in groups:
    print group
```


---

# system.eam.queryAgentHistory

**版本：** 8.1
**型別：** Scripting
**分類：** Eam

## 詳述

This function is used inPython Scripting. Returns a list of the most recent agent events. This function can only be called from the Controller. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.eam.queryAgentHistory(groupIds, agentIds, startDate, endDate, limit)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| groupIds | List | A list of groups to restrict the results to. If not specified, all groups will be included. |
| agentIds | List | A list of agent names to restrict the results to. If not specified, all agents will be allowed. |
| startDate | Date | The starting time for history events. If null, defaults to 8 hours previous to now. |
| endDate | Date | The ending time for the query range. If null, defaults to "now". |
| limit | int | The limit of results to return. Defaults to 100. A value of 0 means "no limit". |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.eam.queryAgentHistory(groupIds, agentIds, startDate, endDate, limit)
```


---

# system.eam.queryAgentStatus

**版本：** 8.1
**型別：** Scripting
**分類：** Eam

## 詳述

This function is used inPython Scripting. Returns the current state of the matching agents. This function can only be called from the Controller. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.eam.queryAgentStatus(groupIds, agentIds, isConnected)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| groupIds | List | A list of groups to restrict the results to. If not specified, all groups will be included. |
| agentIds | List | A list of agent names to restrict the results to. If not specified, all agents will be allowed. |
| isConnected | Boolean | If True, only returns agents that are currently connected. If False, only agents that are considered down will be returned, and if not specified, all agents will be returned. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.eam.queryAgentStatus(groupIds, agentIds, isConnected)
```


---

# system.eam.runTask

**版本：** 8.1
**型別：** Scripting
**分類：** Eam

## 詳述

This function is used inPython Scripting. Takes the name of a task as an argument as a string (must be configured on the Controller before hand), attempts to execute the task. This function can only be called from the Controller. To run in the client, the user needs arole-based permission. This permission is disabled by default.

## 語法

```python
system.eam.runTask(taskname)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| taskname | String | Name of the task to run. If more than one task has this name, an error will be returned. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.eam.runTask(taskname)
```


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

# system.groups.loadFromFile

**版本：** 8.1
**型別：** Scripting
**分類：** Groups

## 詳述

This function is used inPython Scripting. Loads a transaction group configuration from an xml export, into the specified project (creating the project if necessary). The mode parameter dictates how overwrites occur. This function is scoped for Perspective Sessions, but since all scripts in Perspective run on the Gateway, the file must be located on the Gateway's file system.

## 語法

```python
 system.groups.loadFromFile(filePath, projectName, mode)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| filePath | String | The path to a valid transaction group xml or csv file. |
| projectName | String | The name of the project to load into. |
| mode | int | How duplicates will be handled. 0 = Overwrite, 1 = Ignore, 2 = Replace the existing project with this one. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
 system.groups.loadFromFile(filePath, projectName, mode)
```

### Example 3

```python
projectName
```


---

# system.groups.removeGroups

**版本：** 8.1
**型別：** Scripting
**分類：** Groups

## 詳述

This function is used inPython Scripting. Removes the specified groups from the project. The group paths areFolder/Path/To/GroupName, separated by forward slashes. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.groups.removeGroups(projectName, paths)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| projectName | String | The project to remove from. If the project does not exist, throws an IllegalArgumentException. |
| paths | List[String] | A list of paths to remove. Group paths are the full path to the resource, separated by forward slashes, e.g., "Folder/Path/To/GroupName". |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
Folder/Path/To/GroupName
```

### Example 2

```python
system.groups.removeGroups(projectName, paths)
```

### Example 3

```python
projectName
```


---

# system.gui.chooseColor

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Prompts the user to pick a color using the default color-chooser dialog box. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.chooseColor(initialColor, [dialogTitle])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| initialColor | Color | A color to use as a starting point in the color choosing popup. |
| dialogTitle | String | The title for the color choosing popup. Defaults to "Choose Color". [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.chooseColor(initialColor, [dialogTitle])
```

### Example 2

```python
initialColor
```

### Example 3

```python
dialogTitle
```


---

# system.gui.closeDesktop

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Allows you to close any of the open desktops associated with the current client. See theMulti-Monitor Clientspage for more details about using multiple monitors. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.closeDesktop(handle)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| handle | String | The handle for the desktop to close. The screen index cast as a string may be used instead of the handle. If omitted, this will default to the primary desktop. Alternatively, the handle "primary" can be used to refer to the primary desktop. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.closeDesktop(handle)
```

### Example 3

```python
# The following example will close this desktop
system.gui.closeDesktop()
```


---

# system.gui.color

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Creates a new color object, either by parsing a string or by having the RGB[A] channels specified explicitly. SeetoColorto see a list of available color names. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.color(color)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| color | String | A string that will be coerced into a color. Can accept many formats, such as "red" or "#FF0000" or "255,0,0". |
| red | Integer | The red component of the color, an integer 0-255. |
| green | Integer | The green component of the color, an integer 0-255. |
| blue | Integer | The blue component of the color, an integer 0-255. |
| alpha | Integer | The alpha component of the color, an integer 0-255. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.color(color)
```

### Example 3

```python
system.gui.color(red, green, blue, [alpha])
```


---

# system.gui.confirm

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Displays a confirmation dialog box to the user with "Yes" and "No" options, and a custom message. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.confirm(message, [title], [allowCancel])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| message | String | The message to show in the confirmation dialog. |
| title | String | The title for the confirmation dialog. [optional] |
| allowCancel | Boolean | Show a cancel button in the dialog. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.confirm(message, [title], [allowCancel])
```


---

# system.gui.convertPointToScreen

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Converts a pair of coordinates that are relative to the upper-left corner of a component to be relative to the upper-left corner of the entire screen. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.convertPointToScreen(x, y, event)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| x | Integer | The X-coordinate, relative to the component that fired the event. |
| y | Integer | The Y-coordinate, relative to the component that fired the event. |
| event | EventObject | An event object for a component event. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.convertPointToScreen(x, y, event)
```


---

# system.gui.createPopupMenu

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Creates a new popup menu, which can then be shown over a component on a mouse event. To use this function, first create a Python sequence whose entries are strings, and another sequence whose entries are function objects. The strings will be the items that are displayed in your popup menu, and when an item is clicked, its corresponding function will be run. Your functions must accept an event object as an argument. See also:Functions. The function return

## 語法

```python
system.gui.createPopupMenu(itemNames, itemFunctions)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| itemNames | List[String] | A list of names to create popup menu items with. |
| itemFunctions | List[String] | A list of functions to match up with the names. Passing in a None object will cause a separator line to appear in the popup menu, and the corresponding string will not be displayed (note that a corresponding string must be supplied, since the number of elements in the itemFunctions parameter must always match the number of elements in the itemNames parameter). |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.createPopupMenu(itemNames, itemFunctions)
```

### Example 3

```python
itemFunctions
```


---

# system.gui.desktop

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Allows for invoking system.gui functions on a specific desktop. See theMulti-Monitor Clientspage for more details.

## 語法

```python
system.gui.desktop(handle)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| handle | String | The handle for the desktop to use. The screen index cast as a string may be used instead of the handle. If omitted, this will default to the primary desktop. Alternatively, the handle "primary" can be used to refer to the primary desktop. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.desktop(handle)
```

### Example 3

```python
# The following example makes a message box appear on the primary desktop,
# regardless of where the script originates.
# system.gui.desktop() function requires a handle be passed to it for this example
# to work properly.

system.gui.desktop().messageBox("This will appear on the Primary Desktop")
```


---

# system.gui.errorBox

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Displays an error-style message box to the user. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.errorBox(message, [title])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| message | String | The message to display in an error box. Will accept HTML formatting. |
| title | String | The title for the error box. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.errorBox(message, [title])
```


---

# system.gui.findWindow

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Finds and returns a list of windows with the given path. If the window is not open, an empty list will be returned. Useful for finding all instances of an open window that were opened withsystem.nav.openWindowInstance. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.findWindow(path)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| path | String | The path of the window to search for. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.findWindow(path)
```

### Example 3

```python
# This example finds all open instances of the window named "Popup" and closes them all.

allInstances = system.gui.findWindow("Popup")
for window in allInstances:
    system.nav.closeWindow(window)
```


---

# system.gui.getCurrentDesktop

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Returns the handle of the desktop this function was called from. Commonly used with thesystem.gui.desktopandsystem.nav.desktopfunctions. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.getCurrentDesktop( )
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.getCurrentDesktop( )
```

### Example 2

```python
# Shows the desktop's handle in a message box.
system.gui.messageBox("This desktop's handle is: %s" % system.gui.getCurrentDesktop())
```

### Example 3

```python
# Shows the desktop's handle in a message box.
system.gui.messageBox("This desktop's handle is: %s" % system.gui.getCurrentDesktop())
```


---

# system.gui.getDesktopHandles

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Gets a list of allsecondaryhandles of the open desktops associated with the current client. In this case,secondarymeans any desktop frame opened by the original client frame. For example, if the original client opened two new frames ('left client' and 'right client'), then this function would return ['left client', 'right client'].

## 語法

```python
system.gui.getDesktopHandles()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.getDesktopHandles()
```

### Example 2

```python
# The following example list all handles (except the main client)
# in the client console (Help -> Diagnostics -> Console)

print system.gui.getDesktopHandles()
```

### Example 3

```python
# The following example list all handles (except the main client)
# in the client console (Help -> Diagnostics -> Console)

print system.gui.getDesktopHandles()
```


---

# system.gui.getOpenedWindowNames

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Finds all of the currently open windows and returns a tuple of their paths. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.getOpenedWindowNames()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.getOpenedWindowNames()
```

### Example 2

```python
# This example prints out into the console the full path for each opened window.

windows = system.gui.getOpenedWindowNames()
print 'There are %d windows open' % len(windows)
for path in windows:
    print path
```

### Example 3

```python
# This example prints out into the console the full path for each opened window.

windows = system.gui.getOpenedWindowNames()
print 'There are %d windows open' % len(windows)
for path in windows:
    print path
```


---

# system.gui.getOpenedWindows

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Finds all of the currently open windows and returns a tuple of references to them. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.getOpenedWindows()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.getOpenedWindows()
```

### Example 2

```python
# This example prints out the path of each currently opened window to the console.

windows = system.gui.getOpenedWindows()
print 'There are %d windows open' % len(windows)
for window in windows:
    print window.getPath()
```

### Example 3

```python
# This example prints out the path of each currently opened window to the console.

windows = system.gui.getOpenedWindows()
print 'There are %d windows open' % len(windows)
for window in windows:
    print window.getPath()
```


---

# system.gui.getParentWindow

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Finds the parent (enclosing) window for the component that fired an event and returns a reference to it. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.getParentWindow(event)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| event | EventObject | A component event object. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.getParentWindow(event)
```

### Example 3

```python
# Use this in an event script to change the window's title.

window = system.gui.getParentWindow(event)
window.title='This is a new title'
```


---

# system.gui.getQuality

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Returns the data quality for the property of the given component as an integer. This function can be used to check the quality of a Tag binding on a component in the middle of the script so that alternative actions can be taken in the event of device disconnections. A description of the quality codes can be found on theQuality Codes and Overlayspage.

## 語法

```python
system.gui.getQuality(component, propertyName)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| component | JComponent | The component whose property is being checked. |
| propertyName | String | The name of the property as a string value. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.getQuality(component, propertyName)
```

### Example 3

```python
propertyName
```


---

# system.gui.getScreenIndex

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Returns an integer value representing the current screen index based on the screen from which this function was called. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.getScreenIndex()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.getScreenIndex()
```

### Example 2

```python
# Prints an integer representing the screen from which the function was called.
print system.gui.getScreenIndex()
```

### Example 3

```python
# Prints an integer representing the screen from which the function was called.
print system.gui.getScreenIndex()
```


---

# system.gui.getScreens

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Get a list of all the monitors on the computer this client is open on. Use withsystem.gui.setScreenIndex()to move the client. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.getScreens()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.getScreens()
```

### Example 2

```python
# This example fetches monitor data and pushes it to a table in the same container.

screens = system.gui.getScreens()
pyData = []
for screen in screens:
    pyData.append([screen[0], screen[1], screen[2]])

# Push data to 'Table'.
event.source.parent.getComponent('Table').data = system.dataset.toDataSet(["screen","width","height"], pyData)
```

### Example 3

```python
# This example fetches monitor data and pushes it to a table in the same container.

screens = system.gui.getScreens()
pyData = []
for screen in screens:
    pyData.append([screen[0], screen[1], screen[2]])

# Push data to 'Table'.
event.source.parent.getComponent('Table').data = system.dataset.toDataSet(["screen","width","height"], pyData)
```


---

# system.gui.getSibling

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Given a component event object, looks up a sibling component. Shortcut forevent.source.parent.getComponent("siblingName"). If no such sibling is found, the special value None is returned. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.getSibling(event, name)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| event | EventObject | A component event object. |
| name | String | The name of the sibling component. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.getSibling(event, name)
```


---

# system.gui.getWindow

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Finds a reference to an open window with the given name. Throws a ValueError if the named window is not open or not found. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.getWindow(name)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| name | String | The path to the window to field. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.getWindow(name)
```

### Example 3

```python
# This example will get the window named 'Overview' and then close it.

try:
   window = system.gui.getWindow('Overview')
   system.gui.closeWindow(window)

except ValueError:
   system.gui.warningBox("The Overview window isn't open")
```


---

# system.gui.getWindowNames

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Returns a list of the paths of all windows in the current project, sorted alphabetically. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.getWindowNames()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.getWindowNames()
```

### Example 2

```python
# This example would open windows that begin with "Motor" and pass in the currently selected motor number.

motor = event.source.parent.number
windows = system.gui.getWindowNames()
for path in windows:
   if name[:5] == "Motor":
      system.nav.openWindow(path, {"motorNumber":motor})
```

### Example 3

```python
# This example would open windows that begin with "Motor" and pass in the currently selected motor number.

motor = event.source.parent.number
windows = system.gui.getWindowNames()
for path in windows:
   if name[:5] == "Motor":
      system.nav.openWindow(path, {"motorNumber":motor})
```


---

# system.gui.inputBox

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Opens up a popup input dialog box. This dialog box will show a prompt message and allow the user to type in a string. When the user is done, they can clickOKorCancel. If OK is pressed, this function will return with the value that they typed in. If Cancel is pressed, this function will return the value None. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.inputBox(message, defaultText)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| message | String | The message to display for the input box. Will accept HTML formatting. |
| defaultText | String | The default text to initialize the input box with. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.inputBox(message, defaultText)
```

### Example 3

```python
defaultText
```


---

# system.gui.isTouchscreenModeEnabled

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Checks whether or not the running Client's Touch Screen mode is currently enabled. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.isTouchscreenModeEnabled()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.isTouchscreenModeEnabled()
```

### Example 2

```python
# This example is used in the Client Startup script to check if this Client is being run on a touch screen computer (judged by an IP address) and set Touch Screen mode.

ipAddress = system.net.getIpAddress()
query = "SELECT COUNT(*) FROM touchscreen_computer_ips WHERE ip_address = '%s' "
isTouchscreen = system.db.runScalarQuery(query %(ipAddress))
if isTouchscreen and not system.gui.isTouchscreenModeEnabled():
   system.gui.setTouchscreenModeEnabled(1)
```

### Example 3

```python
# This example is used in the Client Startup script to check if this Client is being run on a touch screen computer (judged by an IP address) and set Touch Screen mode.

ipAddress = system.net.getIpAddress()
query = "SELECT COUNT(*) FROM touchscreen_computer_ips WHERE ip_address = '%s' "
isTouchscreen = system.db.runScalarQuery(query %(ipAddress))
if isTouchscreen and not system.gui.isTouchscreenModeEnabled():
   system.gui.setTouchscreenModeEnabled(1)
```


---

# system.gui.messageBox

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Displays an informational-style message popup box to the user. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.messageBox(message, title)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| message | String | The message to display. Will accept HTML formatting. |
| title | String | A title for the message box. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.messageBox(message, title)
```


---

# system.gui.openDesktop

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Creates an additional Desktop in a new frame. For more details, see theMulti-Monitor Clientspage. This function acceptskeyword arguments.

## 語法

```python
system.gui.openDesktop ([screen], [handle], [title], [width], [height], [x], [y], [windows])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| screen | Integer | The screen index of which screen to place the new frame on. If omitted, screen 0 will be used. [optional] |
| handle | String | A name for the desktop. If omitted, the screen index will be used. [optional] |
| title | String | The title for the new frame. If omitted, the index handle will be used. If the handle and title are omitted, the screen index will be used. [optional] |
| width | Integer | The width for the new desktop's frame. If omitted, frame will become maximized on the specified monitor. [optional] |
| height | Integer | The height for the new desktop's frame. If omitted, frame will become maximized on the specified monitor. [optional] |
| x | Integer | The x coordinate for the new desktop's frame. Only used if both width and height are specified. If omitted, defaults to 0. [optional] |
| y | Integer | The y coordinate for the new desktop's frame. Only used if both width and height are specified. If omitted, defaults to 0. [optional] |
| windows | PySequence | A list of window paths to open in the new Desktop frame. If omitted, the desktop will open without any opened windows. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.openDesktop ([screen], [handle], [title], [width], [height], [x], [y], [windows])
```


---

# system.gui.openDiagnostics

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Opens the Client runtime Diagnostics window, which provides information regarding performance, logging, active threads, connection status, and the console. This provides an opportunity to open the Diagnostics window in situations where the menu bar in the client is hidden, and the keyboard shortcut (Ctrl+Shift+F7) can not be used. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.openDiagnostics()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.openDiagnostics()
```

### Example 2

```python
# Opens the diagnostics window in a running client
system.gui.openDiagnostics()
```

### Example 3

```python
# Opens the diagnostics window in a running client
system.gui.openDiagnostics()
```


---

# system.gui.passwordBox

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Pops up a special input box that uses a password field, so the text isn't echoed back in clear-text to the user. Returns the text they entered, or None if they canceled the dialog box. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.passwordBox(message, [title], [echoChar])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| message | String | The message for the password prompt. Will accept HTML formatting. |
| title | String | A title for the password prompt. [optional] |
| echoChar | String | A custom echo character. Defaults to:*[optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.passwordBox(message, [title], [echoChar])
```


---

# system.gui.setScreenIndex

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Moves an open client to a specific monitor. Use withsystem.gui.getScreens()to identify monitors before moving. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.setScreenIndex(index)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| index | Integer | The new monitor index for this client to move to. 0 based. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.setScreenIndex(index)
```

### Example 3

```python
# This example could be used on a startup script to move the client to a 2nd monitor.

system.gui.setScreenIndex(1)
```


---

# system.gui.setTouchscreenModeEnabled

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Alters a running Client's Touch Screen mode on the fly. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.setTouchscreenModeEnabled(enabled)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| enabled | Boolean | The new value for touchscreen mode being enabled. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.setTouchscreenModeEnabled(enabled)
```

### Example 3

```python
# This example could be used on an input heavy window's internalFrameActivated event to remove Touch Screen mode.

if system.gui.isTouchscreenModeEnabled():
   system.gui.setTouchscreenModeEnabled(False)
```


---

# system.gui.showNumericKeypad

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Displays a modal on-screen numeric keypad, allowing for arbitrary numeric entry using the mouse, or a finger on a touch screen monitor. Returns the number that the user entered. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.showNumericKeypad(initialValue, [fontSize], [usePasswordMode])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| initialValue | Number | The value to start the on-screen keypad with. |
| fontSize | Integer | The font size to display in the keypad. [optional] |
| usePasswordMode | Boolean | If True, display a*for each digit. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.showNumericKeypad(initialValue, [fontSize], [usePasswordMode])
```

### Example 2

```python
initialValue
```


---

# system.gui.showTouchscreenKeyboard

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Displays a modal on-screen keyboard, allowing for arbitrary text entry using the mouse, or a finger on a touchscreen monitor. Returns the text that the user entered. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.showTouchscreenKeyboard(initialText, [fontSize], [passwordMode])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| initialText | String | The text to start the on-screen keyboard with. |
| fontSize | Integer | The font size to display in the keyboard. [optional] |
| passwordMode | Boolean | A True value will activate password mode, where the text entered is not echoed back in cleartext. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.showTouchscreenKeyboard(initialText, [fontSize], [passwordMode])
```

### Example 2

```python
initialText
```


---

# system.gui.transform

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Sets a component's position and size at runtime.  Additional arguments for the duration, framesPerSecond, and acceleration of the operation exist for animation.  An optional callback argument will be executed when the transformation is complete. The transformation is performed in Designer coordinate space on components that are centered or have more than two anchors.

## 語法

```python
system.gui.transform(component, [newX], [newY], [newWidth], [newHeight], [duration], [callback], [framesPerSecond], [acceleration], [coordSpace])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| component | JComponent | The component to move or resize. |
| newX | Integer | An x-coordinate to move to, relative to the upper-left corner of the component's parent container. [optional] |
| newY | Integer | A y-coordinate to move to, relative to the upper-left corner of the component's parent container. [optional] |
| newWidth | Integer | A width for the component. [optional] |
| newHeight | Integer | A height for the component. [optional] |
| duration | Integer | A duration over which the transformation will take place.  If omitted or 0, the transform will take place immediately. [optional] |
| callback | Callable | Function to be called when the transformation is complete. [optional] |
| framesPerSecond | Integer | Frame rate argument which dictates how often the transformation updates over the given duration.  The default is 60 frames per second. [optional] |
| acceleration | Integer | An optional modifier to the acceleration of the transformation over the given duration. Seesystem.gui constantsfor valid arguments. [optional] |
| coordSpace | Integer | The coordinate space to use. When the default screen coordinates are used, the given size and position are absolute, as they appear in the Client at runtime. When Designer Coordinates are used, the given size and position are pre-runtime adjusted values, as they would appear in the Designer. Seesystem.gui constantsfor valid arguments. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.transform(component, [newX], [newY], [newWidth], [newHeight], [duration], [callback], [framesPerSecond], [acceleration], [coordSpace])
```


---

# system.gui.warningBox

**版本：** 8.1
**型別：** Scripting
**分類：** Gui

## 詳述

This function is used inPython Scripting. Displays a message to the user in a warning style popup dialog. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.gui.warningBox(message, [title])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| message | String | The message to display in the warning box. Will accept HTML formatting if the message parameter is encapsulated in an <html> tag. |
| title | String | The title for the warning box. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.gui.warningBox(message, [title])
```


---

# system.iec61850.cancel

**版本：** 8.1
**型別：** Scripting
**分類：** Iec61850

## 詳述

This function is used inPython Scripting. Cancels the selection of an SBO type control on a configured IEC 61850 device to prevent theoperatecommand from performing.

## 語法

```python
system.iec81650.cancel(deviceName, mapParams)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the configured IEC 61850 device. |
| mapParams | PyDictionary | Control parameters dictionary that requires the following keys to be specified: name, T, orCat, orIdent, Check, and Test. These keys must match the params from the select function. If you do not know the required key value pairs, they can be found using thegetControlParamsfunction. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.iec81650.cancel(deviceName, mapParams)
```


---

# system.iec61850.getControlParams

**版本：** 8.1
**型別：** Scripting
**分類：** Iec61850

## 詳述

This function is used inPython Scripting. This function returns a list of report control names and their attributes contained in the configured IEC 61850 device.

## 語法

```python
system.iec81650.getControlParams(deviceName)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the configured IEC 61850 device. |

## 回傳值

**型別：** Object

## 範例

### Example 2

```python
system.iec81650.getControlParams(deviceName)
```


---

# system.iec61850.listFiles

**版本：** 8.1
**型別：** Scripting
**分類：** Iec61850

## 詳述

This function is used inPython Scripting. This function returns a list of filenames from a remote path for the configured IEC 61850 device.

## 語法

```python
system.iec61850.listFiles(deviceName, remoteFilePath)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the configured IEC 61850 device. |
| remoteFilePath | String | The remote file path on the server of the configured IEC 61850 device for the file to read. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.iec61850.listFiles(deviceName, remoteFilePath)
```

### Example 3

```python
remoteFilePath
```


---

# system.iec61850.operate

**版本：** 8.1
**型別：** Scripting
**分類：** Iec61850

## 詳述

This function is used inPython Scripting. This function operates on the IEC 61850 device control immediately, such as to change the position of a switch. This can be done directly, or following a select command.

## 語法

```python
system.iec61850.operate(deviceName, mapParams, controlValue)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the configured IEC 61850 device. |
| mapParams | PyDictionary | Control parameters dictionary that requires the following keys to be specified: name, T, orCat, orIdent, Check, and Test. Use the same params as theselectfunction when operating on an SBO type control. If you do not know the required key value pairs, they can be found using thegetControlParamsfunction. |
| controlValue | Float | Control value (32-bit float). |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.iec61850.operate(deviceName, mapParams, controlValue)
```


---

# system.iec61850.readFile

**版本：** 8.1
**型別：** Scripting
**分類：** Iec61850

## 詳述

This function is used inPython Scripting. This function downloads remote files from the configured IEC 61850 device to an identified local path.

## 語法

```python
system.iec61850.readFile(deviceName, remoteFilePath, localFilePath)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the configured IEC 61850 device. |
| remoteFilePath | String | The remote file path on the server of the file to read. |
| localFilePath | String | The local file path on client to store the file contents. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.iec61850.readFile(deviceName, remoteFilePath, localFilePath)
```

### Example 3

```python
remoteFilePath
```


---

# system.iec61850.select

**版本：** 8.1
**型別：** Scripting
**分類：** Iec61850

## 詳述

This function is used inPython Scripting. Select an SBO type control to prepare it for a subsequentoperatecommand for a configured IEC 61850 device. These selections can be removed by using thecancelfunction.

## 語法

```python
system.iec61850.select(device_name, mapParams, value)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the configured IEC 61850 device. |
| mapParams | PyDictionary | Control parameters dictionary that requires the following keys to be specified: name, T, orCat, orIdent, Check, and Test. If you do not know the required key value pairs, they can be found using thegetControlParamsfunction. |
| controlValue | Float | Control value (32-bit float). |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.iec61850.select(device_name, mapParams, value)
```


---

# system.iec61850.writeFile

**版本：** 8.1
**型別：** Scripting
**分類：** Iec61850

## 詳述

This function is used inPython Scripting. This function uploads a file from a local path to the configured IEC 61850 device remote path.

## 語法

```python
system.iec61850.writeFile(deviceName, localFilePath, remoteFilePath)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| deviceName | String | The name of the configured IEC 61850 device. |
| localFilePath | String | The local file path on client to pull the file contents from. |
| remoteFilePath | String | The remote file path on the server of the file to write to. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.iec61850.writeFile(deviceName, localFilePath, remoteFilePath)
```

### Example 3

```python
localFilePath
```


---

# system.math.geometricMean

**版本：** 8.1
**型別：** Scripting
**分類：** Math

## 詳述

This function is used inPython Scripting. Calculates the geometric mean. Geometric mean is a type of average which indicates a value in a set of numbers by using the product of values in the set and then taking the nth root, wherenis the number of values in the set. This is different than an arithmetic mean, which calculates an average based off the sum of the numbers, and divides it by n number of values. Geometric means can only be positive numbers. Returns NaN (Not a Number) if passed an empt

## 語法

```python
system.math.geometricMean(values)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| values | List[Float] | A sequence of numerical values. Accepts both integers and floats. The sequence may not contain None type values. However, passing a None type object instead of a sequence of numerical values will return NaN. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.math.geometricMean(values)
```

### Example 3

```python
# Create a List of values.
values = [3.5, 5.6, 7.8, 7.4, 3.8]

# Prints the resulting value.
print system.math.geometricMean(values)
```


---

# system.math.kurtosis

**版本：** 8.1
**型別：** Scripting
**分類：** Math

## 詳述

This function is used inPython Scripting. Calculates the kurtosis of a sequence of values. Kurtosis measures if data is peaked or flat relative to normal distribution. A set of data with high kurtosis will have distinct peaks near the mean, while a set of data with low kurtosis will have a flat top near the mean. Uniform distribution is typically a flat line. Returns NaN (Not a Number) if passed an empty sequence measure of whether the data are heavy-tailed or light-tailed of a given distributio

## 語法

```python
system.math.kurtosis(values)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| values | List[Float] | A sequence of numerical values. Accepts both integers and floats. The sequence may not contain None type values. However, passing a None type object instead of a sequence of numerical values will return NaN. Requires at least four items in the list. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.math.kurtosis(values)
```

### Example 3

```python
# Create a List of values.
values = [3.5, 5.6, 7.8, 7.4, 3.8]

# Prints the resulting value.
print system.math.kurtosis(values)
```


---

# system.math.max

**版本：** 8.1
**型別：** Scripting
**分類：** Math

## 詳述

This function is used inPython Scripting. Given a sequence of values, returns the greatest value in the sequence, also known as the "max" value. Returns NaN (Not a Number) if passed an empty sequence.

## 語法

```python
system.math.max(values)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| values | List[Float] | A sequence of numerical values. Accepts both integers and floats. The sequence may not contain None type values. However, passing a None type object instead of a sequence of numerical values will return NaN. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.math.max(values)
```

### Example 3

```python
# Create a List of values.
values = [3.5, 5.6, 7.8, 7.4, 3.8]

# Prints the resulting value.
print system.math.max(values)
```


---

# system.math.mean

**版本：** 8.1
**型別：** Scripting
**分類：** Math

## 詳述

This function is used inPython Scripting. Given a sequence of values, calculates the arithmetic mean (average). Returns NaN (Not a Number) if passed an empty sequence.

## 語法

```python
system.math.mean(values)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| values | Float[] | A sequence of numerical values. Accepts both integers and floats. The sequence may not contain None type values. However, passing a None type object instead of a sequence of numerical values will return NaN. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.math.mean(values)
```

### Example 3

```python
# Create a list of values.
values = [3.5, 5.6, 7.8, 7.4, 3.8]

# Prints the resulting value.
print system.math.mean(values)
```


---

# system.math.meanDifference

**版本：** 8.1
**型別：** Scripting
**分類：** Math

## 詳述

This function is used inPython Scripting. Given two sequences of values, calculates the mean of the signed difference between both sequences. In other words, returns the absolute difference between the mean values of two different sets of data. Throws a DimensionMismatchException if the two sequences have different lengths.

## 語法

```python
system.math.meanDifference(values1, values2)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| values1 | List[Float] | A sequence of numerical values. Accepts both integers and floats. The sequence may not contain None type values. However, passing a None type object instead of a sequence of numerical values will return NaN. |
| values2 | List[Float] | A sequence of numerical values. Accepts both integers and floats. The sequence may not contain None type values. However, passing a None type object instead of a sequence of numerical values will return NaN. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.math.meanDifference(values1, values2)
```


---

# system.math.median

**版本：** 8.1
**型別：** Scripting
**分類：** Math

## 詳述

This function is used inPython Scripting. Takes a sequence of values, and returns the median. The median represents the middle value in a set of data. Returns NaN (Not a Number) if passed an empty sequence.

## 語法

```python
system.math.median(values)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| values | List[Float] | A sequence of numerical values. Accepts both integers and floats. The sequence may not contain None type values. However, passing a None type object instead of a sequence of numerical values will return NaN. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.math.median(values)
```

### Example 3

```python
# Create a list of values.
values = [3.5, 5.6, 7.8, 7.4, 3.8]

# Prints the resulting value.
print system.math.median(values)
```


---

# system.math.min

**版本：** 8.1
**型別：** Scripting
**分類：** Math

## 詳述

This function is used inPython Scripting. Given a sequence of numerical values, returns the minimum value, also known as the "min" value. Returns NaN (Not a Number) if passed an empty sequence.

## 語法

```python
system.math.min(values)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| values | List[Float] | A sequence of numerical values. Accepts both integers and floats. The sequence may not contain None type values. However, passing a None type object instead of a sequence of numerical values will return NaN. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.math.min(values)
```

### Example 3

```python
# Create a list of values.
values = [3.5, 5.6, 7.8, 7.4, 3.8]

# Prints the resulting value.
print system.math.min(values)
```


---

# system.math.mode

**版本：** 8.1
**型別：** Scripting
**分類：** Math

## 詳述

This function is used inPython Scripting. Given a sequence of values, returns the 'mode', or most frequent values. Returns an empty list if the sequence was empty or None.

## 語法

```python
system.math.mode(values)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| values | List[Float] | A sequence of numerical values. Accepts both integers and floats. The sequence may not contain None type values. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.math.mode(values)
```

### Example 3

```python
# Create a list of values.
values = [3.5, 5.6, 7.8, 7.4, 7.8]

# Return the most common values.
modes = system.math.mode(values)

# Print the first item in the result.
print modes[0]

# Iterate over the results.
for number in modes:
    print number
```


---

# system.math.normalize

**版本：** 8.1
**型別：** Scripting
**分類：** Math

## 詳述

This function is used inPython Scripting. Given a sequence of values, normalizes the values. Normalizing data refers to adjusting values measured on different scales and brings them into alignment to allow the comparison of corresponding normalized values. This creates uniformity of values by eliminating the different units of measurement, and to more easily compare data from different places. Returns an empty list if the sequence was empty or None.

## 語法

```python
system.math.normalize(values)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| values | List[Float] | A sequence of numerical values. Accepts both integers and floats. The sequence may not contain None type values. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.math.normalize(values)
```

### Example 3

```python
# Create a list of values.
values = [3.5, 5.6, 7.8, 7.4, 7.8]

# Return the most common values.
normalized = system.math.normalize(values)

# Print the first item in the result.
print normalized[0]

# Iterate over the results.
for number in normalized:
    print number
```


---

# system.math.percentile

**版本：** 8.1
**型別：** Scripting
**分類：** Math

## 詳述

This function is used inPython Scripting. Given a sequence of numerical values, estimates the percentile of input. The percentile is a value on a scale that represents a percentage position in a list of data that can be equal to or below that value: i.e., the 25th percentile is a value below which 25% of observable data points may be found.

## 語法

```python
system.math.percentile(values, percentile)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| values | List[Float] | A sequence of numerical values. Accepts both integers and floats. The sequence may not contain None type values. However, passing a None type object instead of a sequence of numerical values will return NaN. |
| percentile | Float | The percentile to compute. A float greater than 0 and less than or equal to 100. Will throw an exception if the percentile is out of bounds. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.math.percentile(values, percentile)
```


---

# system.math.populationVariance

**版本：** 8.1
**型別：** Scripting
**分類：** Math

## 詳述

This function is used inPython Scripting. Given a sequence of values, returns the population variance. Population variance calculates how values in a dataset are spread out from their average value. Returns NaN (Not a Number) if passed an empty sequence.

## 語法

```python
system.math.populationVariance(values)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| values | List[Float] | A sequence of numerical values. Accepts both integers and floats. The sequence may not contain None type values. However, passing a None type object instead of a sequence of numerical values will return NaN. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.math.populationVariance(values)
```

### Example 3

```python
# Create a list of values.
values = [3.5, 5.6, 7.8, 7.4, 3.8]

# Print the resulting value.
print system.math.populationVariance(values)
```


---

# system.math.product

**版本：** 8.1
**型別：** Scripting
**分類：** Math

## 詳述

This function is used inPython Scripting. Given a sequence of values, calculates the product of the sequence: the result of multiplying of all values in the sequence together. Returns NaN (Not a Number) if passed an empty sequence.

## 語法

```python
system.math.product(values)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| values | List[Float] | A sequence of numerical values. Accepts both integers and floats. The sequence may not contain None type values. However, passing a None type object instead of a sequence of numerical values will return NaN. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.math.product(values)
```

### Example 3

```python
# Create a list of values.
values = [3.5, 5.6, 7.8, 7.4, 3.8]

# Print the resulting value.
print system.math.product(values)
```


---

# system.math.skewness

**版本：** 8.1
**型別：** Scripting
**分類：** Math

## 詳述

This function is used inPython Scripting. Given a sequence of values, calculates the skewness (third central moment). Skewness is a measure of the degree of asymmetry of a distribution of the mean. If skewed to the left, the distribution has a long tail in the negative direction. If skewed to the right, the tail will be skewed in the positive direction. Skewness values greater than 1 or less than -1 indicate a highly skewed distribution, while skewness values between 0.5 and 1 or -0.5 and -1 ind

## 語法

```python
system.math.skewness(values)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| values | List[Float] | A sequence of numerical values. Accepts both integers and floats. The sequence may not contain None type values. However, passing a None type object instead of a sequence of numerical values will return NaN. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.math.skewness(values)
```

### Example 3

```python
# Create a list of values.
values = [3.5, 5.6, 7.8, 7.4, 3.8]

# Print the resulting value.
print system.math.skewness(values)
```


---

# system.math.standardDeviation

**版本：** 8.1
**型別：** Scripting
**分類：** Math

## 詳述

This function is used inPython Scripting. Given a sequence of numerical values, calculates the simple standard deviation. Standard deviation is a calculated number for how close, or how far the values of that dataset are in relation to the mean. Returns NaN (Not a Number) if passed an empty sequence.

## 語法

```python
system.math.standardDeviation(values)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| values | List[Float] | A sequence of numerical values. Accepts both integers and floats. The sequence may not contain None type values. However, passing a None type object instead of a sequence of numerical values will return NaN. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.math.standardDeviation(values)
```

### Example 3

```python
# Create a list of values.
values = [3.5, 5.6, 7.8, 7.4, 3.8]

# Print the resulting value.
print system.math.standardDeviation(values)
```


---

# system.math.sum

**版本：** 8.1
**型別：** Scripting
**分類：** Math

## 詳述

This function is used inPython Scripting. Given a sequence of values, calculates the sum of all values. The sum is the number returned by addition. Returns NaN (Not a Number) if passed an empty sequence.

## 語法

```python
system.math.sum(values)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| values | List[Float] | A sequence of numerical values. Accepts both integers and floats. The sequence may not contain None type values. However, passing a None type object instead of a Sequence of numerical values will return NaN. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.math.sum(values)
```

### Example 3

```python
# Create a list of values.
values = [3.5, 5.6, 7.8, 7.4, 3.8]

# Print the resulting value.
print system.math.sum(values)
```


---

# system.math.sumDifference

**版本：** 8.1
**型別：** Scripting
**分類：** Math

## 詳述

This function is used inPython Scripting. Given two sequences of values, calculates the sum of each sequence and finds the difference between them. In other words, the difference between sums from two sets of numbers. Throws a DimensionMismatchException if the two sequences have different lengths.

## 語法

```python
system.math.sumDifference(values1, values2)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| values1 | List[Float] | A sequence of numerical values. Accepts both integers and floats. The sequence may not contain None type values. However, passing a None type object instead of a sequence of numerical values will return NaN. |
| values2 | List[Float] | A sequence of numerical values. Accepts both integers and floats. The sequence may not contain None type values. However, passing a None type object instead of a sequence of numerical values will return NaN. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.math.sumDifference(values1, values2)
```


---

# system.math.sumLog

**版本：** 8.1
**型別：** Scripting
**分類：** Math

## 詳述

This function is used inPython Scripting. Given a sequence of values, calculates the sum of the natural logs (ln). Returns NaN (Not a Number) if passed an empty sequence.

## 語法

```python
system.math.sumLog(values)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| values | List[Float] | A sequence of numerical values. Accepts both integers and floats. The sequence may not contain None type values. However, passing a None type object instead of a sequence of numerical values will return NaN. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.math.sumLog(values)
```

### Example 3

```python
# Create a list of values.
values = [3.5, 5.6, 7.8, 7.4, 3.8]

# Print the resulting value.
print system.math.sumLog(values)
```


---

# system.math.sumSquares

**版本：** 8.1
**型別：** Scripting
**分類：** Math

## 詳述

This function is used inPython Scripting. Given a sequence of values, calculates the sum of the squares of all values. Sum squares measures how far individual values are from the mean by calculating how much variation there is in a set of values. Returns NaN (Not a Number) if passed an empty sequence.

## 語法

```python
system.math.sumSquares(values)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| values | List[Float] | A sequence of numerical values. Accepts both integers and floats. The sequence may not contain None type values. However, passing a None type object instead of a sequence of numerical values will return NaN. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.math.sumSquares(values)
```

### Example 3

```python
# Create a list of values.
values = [3.5, 5.6, 7.8, 7.4, 3.8]

# Print the resulting value.
print system.math.sumSquares(values)
```


---

# system.math.variance

**版本：** 8.1
**型別：** Scripting
**分類：** Math

## 詳述

This function is used inPython Scripting. Given a sequence of values, calculates the variance of all values. Variance measures how far values in a set are spread out from their mean value. Returns NaN (Not a Number) if passed an empty sequence.

## 語法

```python
system.math.variance(values)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| values | List[Float] | A sequence of numerical values. Accepts both integers and floats. The sequence may not contain None type values. However, passing a None type object instead of a sequence of numerical values will return NaN. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.math.variance(values)
```

### Example 3

```python
# Create a list of values.
values = [3.5, 5.6, 7.8, 7.4, 3.8]

# Print the resulting value.
print system.math.variance(values)
```


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

# system.nav.centerWindow

**版本：** 8.1
**型別：** Scripting
**分類：** Nav

## 詳述

This function is used inPython Scripting. Given a window path, or a reference to a window itself, it will center the window. The window should be floating an non-maximized. If the window can't be found, this function will do nothing. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.nav.centerWindow(windowPath)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| windowPath | String | The path of the window to center. |
| window | FPMIWindow | A reference to the window to center. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.nav.centerWindow(windowPath)
```

### Example 3

```python
system.nav.centerWindow(window)
```


---

# system.nav.closeParentWindow

**版本：** 8.1
**型別：** Scripting
**分類：** Nav

## 詳述

This function is used inPython Scripting. Closes the parent window given a component event object. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.nav.closeParentWindow(event)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| event | EventObject | A component event object. The enclosing window for the component will be closed. Refer toEventObject. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.nav.closeParentWindow(event)
```

### Example 3

```python
# This code would be placed in the actionPerformed event of a button,
# and would close the window that contained the button.
system.nav.closeParentWindow(event)
```


---

# system.nav.closeWindow

**版本：** 8.1
**型別：** Scripting
**分類：** Nav

## 詳述

This function is used inPython Scripting. Given a window path, or a reference to a window itself, it will close the window. If the window can't be found, this function will do nothing. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.nav.closeWindow(window)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| window | FPMIWindow | A reference to the window to close. |
| windowPath | String | The path of a window to close. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.nav.closeWindow(window)
```

### Example 3

```python
system.nav.closeWindow(windowPath)
```


---

# system.nav.desktop

**版本：** 8.1
**型別：** Scripting
**分類：** Nav

## 詳述

This function is used inPython Scripting. Allows for invokingsystem.navfunctions on a specific desktop. See theMulti-Monitor Clientspage for more details.

## 語法

```python
system.nav.desktop(handle)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| handle | String | The handle for the desktop to use. May be omitted for the primary desktop. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.nav.desktop(handle)
```

### Example 3

```python
# The following example will close a window at path "Main Windows/Overview" in the Primary Desktop,
# regardless of where the script originates from.
system.nav.desktop().closeWindow("Main Windows/Overview")
```


---

# system.nav.getCurrentWindow

**版本：** 8.1
**型別：** Scripting
**分類：** Nav

## 詳述

This function is used inPython Scripting. Returns the path of the current "main screen" window, which is defined as the maximized window. With theTypical Navigation Strategy, there is only ever one maximized window at a time. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.nav.getCurrentWindow()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.nav.getCurrentWindow()
```

### Example 2

```python
# This code could run in a global timer script.
# After a 5-minute timeout, navigate back to the home screen.
if system.util.getInactivitySeconds()>300 and system.nav.getCurrentWindow()!="Home":
   system.nav.swapTo("Home")
```

### Example 3

```python
# This code could run in a global timer script.
# After a 5-minute timeout, navigate back to the home screen.
if system.util.getInactivitySeconds()>300 and system.nav.getCurrentWindow()!="Home":
   system.nav.swapTo("Home")
```


---

# system.nav.goBack

**版本：** 8.1
**型別：** Scripting
**分類：** Nav

## 詳述

This function is used inPython Scripting. When using theTypical Navigation Strategy, this function will navigate back to the previous main screen window. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.nav.goBack()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.nav.goBack()
```

### Example 2

```python
# This code would go in a button to move to the previous screen.
system.nav.goBack()
```

### Example 3

```python
# This code would go in a button to move to the previous screen.
system.nav.goBack()
```


---

# system.nav.goForward

**版本：** 8.1
**型別：** Scripting
**分類：** Nav

## 詳述

This function is used inPython Scripting. When using thetypical navigation strategy, this function will navigate "forward" to the last main-screen window the user was on when they executed asystem.nav.goBack(). This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.nav.goForward()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.nav.goForward()
```

### Example 2

```python
# This code would go in a button to move to the last screen that used system.nav.goBack().
system.nav.goForward()
```

### Example 3

```python
# This code would go in a button to move to the last screen that used system.nav.goBack().
system.nav.goForward()
```


---

# system.nav.goHome

**版本：** 8.1
**型別：** Scripting
**分類：** Nav

## 詳述

This function is used inPython Scripting. When using thetypical navigation strategy, this function will navigate to the "home" window. This is automatically detected as the first main-screen window shown in a project. If you are using this system function withsystem.nav.openWindow(), your home window should be closed before navigating to it, or system.nav.goHome() may not work. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.nav.goHome()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.nav.goHome()
```

### Example 2

```python
# This code would go in a button to move to the Home screen.
system.nav.goHome()
```

### Example 3

```python
# This code would go in a button to move to the Home screen.
system.nav.goHome()
```


---

# system.nav.openWindow

**版本：** 8.1
**型別：** Scripting
**分類：** Nav

## 詳述

This function is used inPython Scripting. Opens the window with the given path. If the window is already open, brings it to the front. The optional params dictionary contains key:valuepairs which will be used to set the target window's root container's dynamic variables. For instance, if the window that you are opening is namedTankDisplayand has a dynamic variable in its root container named "TankNumber", then callingsystem.nav.openWindow("TankDisplay", {"TankNumber" : 4})will open the TankDispl

## 語法

```python
system.nav.openWindow("TankDisplay", {"TankNumber" : 4})
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| path | String | The path to the window to open. |
| params | Dictionary[String, Any] | A dictionary of parameters to pass into the window. The keys in the dictionary must match dynamic property names on the target window's root container. The values for each key will be used to set those properties. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.nav.openWindow("TankDisplay", {"TankNumber" : 4})
```

### Example 2

```python
system.nav.openWindow(path, [params])
```


---

# system.nav.openWindowInstance

**版本：** 8.1
**型別：** Scripting
**分類：** Nav

## 詳述

This function is used inPython Scripting. When called in a Vision Client, it operates exactly likesystem.nav.openWindow(), except that if the named window is already open, then an additional instance of the window will be opened. There is no limit to the number of additional instances of a window that you can open. When called in the Designer, it operates similar to system.nav.openWindow(), except that if the named window is already open the function will swap to the opened window. Additional in

## 語法

```python
system.nav.openWindowInstance(path, [params])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| path | String | The path to the window to open. |
| params | Dictionary[String, Any] | A dictionary of parameters to pass into the window. The keys in the dictionary must match dynamic property names on the target window's root container. The values for each key will be used to set those properties. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.nav.openWindowInstance(path, [params])
```


---

# system.nav.swapTo

**版本：** 8.1
**型別：** Scripting
**分類：** Nav

## 詳述

This function is used inPython Scripting. Performs a window swap from the current main screen window to the window specified. Swapping means that the opened window will take the place of the closing window - in this case it will be maximized. See also:Navigation Strategies. This function works likesystem.nav.swapWindow, except that you cannot specify the source for the swap.

## 語法

```python
system.nav.swapTo(path, [params])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| path | String | The path of a window to swap to. |
| params | Dictionary[String, Any] | A dictionary of parameters to pass into the window. The keys in the dictionary must match dynamic property names on the target window's root container. The values for each key will be used to set those properties. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.nav.swapTo(path, [params])
```


---

# system.nav.swapWindow

**版本：** 8.1
**型別：** Scripting
**分類：** Nav

## 詳述

This function is used inPython Scripting. Performs a window swap. This means that one window is closed, and another is opened and takes its place - assuming its size, floating state, and maximization state. This gives a seamless transition - one window seems to simply turn into another. This function works likesystem.nav.swapTo, except that you can specify the source and destination for the swap.

## 語法

```python
system.nav.swapWindow(swapFromPath, swapToPath, [params])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| swapFromPath | String | The path of the window to swap from. Must be a currently open window, otherwise this will act like an openWindow. |
| swapToPath | String | The name of the window to swap to. |
| params | Dictionary[String, Any] | A dictionary of parameters to pass into the window. The keys in the dictionary must match dynamic property names on the target window's root container. The values for each key will be used to set those properties. [optional] |
| event | EventObject | A component event whose enclosing window will be used as the "swap-from" window. |
| swapToPath | String | The name of the window to swap to. |
| params | Dictionary[String, Any] | A dictionary of parameters to pass into the window. The keys in the dictionary must match dynamic property names on the target window's root container. The values for each key will be used to set those properties. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.nav.swapWindow(swapFromPath, swapToPath, [params])
```

### Example 2

```python
swapFromPath
```


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

# system.opchda.browse

**版本：** 8.1
**型別：** Scripting
**分類：** Opchda

## 詳述

This function is used inPython Scripting. Performs a browse at the given root. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.opchda.browse(root)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| root | String | The root at which to browse. Needs to be a qualified path. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.opchda.browse(root)
```


---

# system.opchda.getAggregates

**版本：** 8.1
**型別：** Scripting
**分類：** Opchda

## 詳述

This function is used inPython Scripting. Will query the server for aggregates that it supports. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.opchda.getAggregates(serverName)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| serverName | String | The name of the definedOPC-HDAserver to query. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.opchda.getAggregates(serverName)
```


---

# system.opchda.getAttributes

**版本：** 8.1
**型別：** Scripting
**分類：** Opchda

## 詳述

This function is used inPython Scripting. Queries the given server for the item attributes that are available withsystem.opchda.readAttributes(). This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.opchda.getAttributes(serverName)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| serverName | String | The name of the defined OPC-HDA server to query. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.opchda.getAttributes(serverName)
```

### Example 3

```python
# This example gets the description of a Matrikon OPC HDA explorer
# Declare a OPC HDA variable using the system function and prints out the results
opcHda = system.opchda.getAttributes('Matrikon HDA')
print opcHda

# Use the getDesc() method to get the description of the attribute and print out the result
getDesc = hda[1].getDesc()
print getDesc
```


---

# system.opchda.getServers

**版本：** 8.1
**型別：** Scripting
**分類：** Opchda

## 詳述

This function is used inPython Scripting. Returns a list of the OPC-HDA servers configured on the system. This call will return all configured and enabled servers, including those that are not currently connected. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.opchda.getServers()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.opchda.getServers()
```

### Example 2

```python
# This example will get a list of OPC HDA servers
system.opchda.getServers()
```

### Example 3

```python
# This example will get a list of OPC HDA servers
system.opchda.getServers()
```


---

# system.opchda.insert

**版本：** 8.1
**型別：** Scripting
**分類：** Opchda

## 詳述

This function is used inPython Scripting. Insert values on the OPC-HDA server. Permission Type: OPC Server Management

## 語法

```python
system.opchda.insert(serverName, itemId, value, date, quality)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| serverName | String | The name of the defined OPC-HDA server. |
| itemId | String | The item ID to perform the operation on. |
| value | Any | The value to insert. |
| date | Any | The date to insert. |
| quality | Integer | The quality to insert. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.opchda.insert(serverName, itemId, value, date, quality)
```


---

# system.opchda.insertReplace

**版本：** 8.1
**型別：** Scripting
**分類：** Opchda

## 詳述

This function is used inPython Scripting. Will insert values on the OPC-HDA server, or replace them if they already exist. Permission Type: OPC Server Management

## 語法

```python
system.opchda.insertReplace(serverName, itemId, value, date, quality)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| serverName | String | The name of the defined OPC-HDA server. |
| itemId | String | The item ID to perform the operation on. |
| value | Object | The value to insert or replace. |
| date | Object | The date to insert or replace. |
| quality | QualityCode | The quality to insert or replace. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.opchda.insertReplace(serverName, itemId, value, date, quality)
```


---

# system.opchda.isServerAvailable

**版本：** 8.1
**型別：** Scripting
**分類：** Opchda

## 詳述

This function is used inPython Scripting. Checks to see if the specified OPC-HDA server is defined, enabled, and connected. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.opchda.isServerAvailable()
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| serverName | String | The name of the OPC-HDA server to check. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.opchda.isServerAvailable()
```

### Example 3

```python
# This example will check to see if there is an OPC HDA server called "ServerName" available.
system.opchda.isServerAvailable(“ServerName”)
```


---

# system.opchda.readAttributes

**版本：** 8.1
**型別：** Scripting
**分類：** Opchda

## 詳述

This function is used inPython Scripting. Reads the specified attributes for the given item over a time range. Attributes and their IDs are defined in the OPC-HDA specification, and can be discovered by callingsystem.opchda.getAttributes(). This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.opchda.readAttributes(serverName, itemId, attributeIds, startDate, endDate)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| serverName | String | The name of the defined OPC-HDA server to read. |
| itemId | String | The itemID to retrieve attributes for. |
| attributeIds | List[String] | The integer IDs of the attributes to read. The attribute ids are defined in the OPC-HDA specification. The attributes can also be obtained by callingsystem.opchda.getAttributes(). Some servers may not support all attributes. |
| startDate | String (can be other data types, such as int) | The starting date/time of the query. |
| endDate | String (can be other data types, such as int) | The ending date/time of the query. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.opchda.readAttributes(serverName, itemId, attributeIds, startDate, endDate)
```


---

# system.opchda.readProcessed

**版本：** 8.1
**型別：** Scripting
**分類：** Opchda

## 詳述

This function is used inPython Scripting. Reads processed values from the OPC-HDA server. Processed values are calculated values, based on the aggregate function requested for each item. The list of aggregates can be obtained by callingsystem.opchda.getAggregates(). This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.opchda.readProcessed(serverName, itemIds, startDate, endDate, resampleIntervalMS, aggregates)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| serverName | String | The name of the defined OPC-HDA server to read. |
| itemIds | List[String] | A list of item ids to read. |
| startDate | Any | The starting date/time of the query. |
| endDate | Any | The ending date/time of the query. |
| resampleIntervalMS | Integer | The interval, in milliseconds, that each value should cover. |
| aggregates | List[Integer] | A list which should be one-to-one with the item ids requested, specifying the integer id of the aggregation function to use. The aggregation ids are defined in the OPC-HDA specification. The list of aggregates can also be obtained by callingsystem.opchda.getAggregates(). |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.opchda.readProcessed(serverName, itemIds, startDate, endDate, resampleIntervalMS, aggregates)
```


---

# system.opchda.readRaw

**版本：** 8.1
**型別：** Scripting
**分類：** Opchda

## 詳述

This function is used inPython Scripting. Reads raw values from the OPC-HDA server. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.opchda.readRaw(serverName, itemIds, startDate, endDate, maxValues, boundingValues)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| serverName | String | The name of the defined OPC-HDA server to read. |
| itemIds | List | A list of item ids to read. |
| startDate | Object | The starting date/time of the query. |
| endDate | Object | The ending date/time of the query. |
| maxValues | Integer | The maximum number of values to return. 0 or less means unlimited. |
| boundingValues | Boolean | A boolean indicating whether or not the "bounding values" should be included in the result set. The bounding values provide a value exactly at the start and end dates, but may be resource-intensive to retrieve. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.opchda.readRaw(serverName, itemIds, startDate, endDate, maxValues, boundingValues)
```


---

# system.opchda.replace

**版本：** 8.1
**型別：** Scripting
**分類：** Opchda

## 詳述

This function is used inPython Scripting. Replaces values on the OPC-HDA server if the given item ID exists. Permission Type: OPC Server Management

## 語法

```python
system.opchda.replace(serverName, itemId, value, date, quality)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| serverName | String | The name of the defined OPC-HDA server. |
| itemId | String | The item ID to perform the operation on. |
| value | Object | The value to replace. |
| date | Object | The date to replace. |
| quality | Integer | The quality to replace. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.opchda.replace(serverName, itemId, value, date, quality)
```


---

# system.opcua.addConnection

**版本：** 8.1
**型別：** Scripting
**分類：** Opcua

## 詳述

This function is used inPython Scripting. Adds a new OPC UA connection.

## 語法

```python
system.opcua.addConnection(name, description, discoveryUrl, endpointUrl, securityPolicy, securityMode, settings)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| name | String | Name to assign to the new connection. |
| description | String | Description assigned to the new OPC UA connection. |
| discoveryUrl | String | Endpoint URL to use for discovery services. |
| endpointUrl | String | Endpoint URL to use for session services. |
| securityPolicy | String | The name of the SecurityPolicy to use. See the Security Policy table below for possible values. |
| securityMode | String | The name of the MessageSecurityMode to use. See the Message Security Mode table below for possible values. |
| settings | Dictionary[String, Any] | A dictionary of additional settings to apply to the connection. See the Settings table for a table of possible keys. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.opcua.addConnection(name, description, discoveryUrl, endpointUrl, securityPolicy, securityMode, settings)
```

### Example 3

```python
description
```


---

# system.opcua.callMethod

**版本：** 8.1
**型別：** Scripting
**分類：** Opcua

## 詳述

This function is used inPython Scripting. Calls a method in an OPC UA server. To make the most of this function, you'll need to be familiar with methods in theOPC UA server. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.opcua.callMethod(connectionName, objectId, methodId, inputs)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| connectionName | String | The name of the OPC UA connection to the server that the method resides in. |
| objectId | String | The NodeId of the Object Node the Method is a member of. |
| methodId | String | The NodeId of the Method Node to call. |
| inputs | List | A list of input values expected by the method. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.opcua.callMethod(connectionName, objectId, methodId, inputs)
```

### Example 2

```python
connectionName
```


---

# system.opcua.removeConnection

**版本：** 8.1
**型別：** Scripting
**分類：** Opcua

## 詳述

This function is used inPython Scripting. Removes an OPC UA Connection.

## 語法

```python
system.opcua.removeConnection(name)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| name | String | The name of the OPC UA connection to remove. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.opcua.removeConnection(name)
```


---

# system.perspective.alterDock

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Changes configuration of a specified dock on a Perspective page.

## 語法

```python
system.perspective.alterDock(dockId, [config], [sessionId], [pageId])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| dockId | String | The unique identifier of the dock to be modified. If no dock with the specified ID exists on the current page, a warning will be logged to the console. |
| config | PyDictionary | A PyDictionary containing the dock configuration to be applied when the script is run. If omitted, the dock configuration remains unchanged. [optional]The following properties can included in theconfigobject:view: The view to be displayed in the dock.viewParams: A dictionary of name and value pairs to be passed as parameters to the view.display: The display state of the dock. Accepted values are:visibleonDemandautoresizable: The resizable status of the dock.modal: The modal status of the dock.content: How the dock should interact with the main content. Accepted values are:pushcoverautosize: The width or height of the dock, depending on orientation.autoBreakpoint: The minimum page width at which a dock with "display = auto" remains visible. If the session width is smaller than this value, the dock is hidden and can be displayed on demand.anchor: Determines whether the docked view remains visible while scrolling. Only available for North-docked views. Accepted values are:fixedscrollablehandle: Controls the visibility of a handle that allows users to expand or collapse the dock. Accepted values are:showhideautoHidehandleIcon: The path to an icon used to represent the dock when it is hidden. |
| sessionId | String | The ID of the session in which the dock modification is applied. If omitted, the modification applies to the current session. [optional] |
| pageId | String | The ID of the page where the dock is located. If omitted, the modification applies to the current page. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.alterDock(dockId, [config], [sessionId], [pageId])
```


---

# system.perspective.alterLogging

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Changes Perspective Session logging attributes and levels. All parameters are optional, with the caveat that at least one of them needs to be used. For thesystem.perspective.alterLoggingfunction to work, the following line needs to be added to theignition.conffile, and the Gateway restarted.  "X" is the next number in the Java Additional Parameters list in theignition.conffile.Warning, this will open potential security holes in the Gateway, and is not ad

## 語法

```python
system.perspective.alterLogging([remoteLoggingEnabled], [level], [remoteLoggingLevel], [sessionId], [pageId])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| remoteLoggingEnabled | Boolean | Will enable remote logging if True. Remote logging will send log events from the Session to the Gateway under the perspective.client logger if they meet the remoteLevel logging level requirement. [optional] |
| level | String | The desired Session logging level. Possible values are: all, trace, debug, info, warn, error, fatal, or off. The default is info. [optional] |
| remoteLoggingLevel | String | The desired remote logging level. Possible values are: all, trace, debug, info, warn, error, fatal, off. The default is warn. [optional] |
| sessionId | String | Identifier of the Session to target. If omitted, the current Session will be used automatically. When targeting a different session, then the pageId parameter must be included in the call. [optional] |
| pageId | String | Identifier of the page to target. If omitted, the current Page will be used automatically. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.alterLogging
```

### Example 2

```python
ignition.conf
```

### Example 3

```python
ignition.conf
```


---

# system.perspective.authenticationChallenge

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Triggers anauthentication challengeaction.

## 語法

```python
system.perspective.authenticationChallenge([sessionId], [pageId], [idp], [forceAuth], [timeout], [payload], [framing])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| sessionId | String | Identifier of the Session to target. If omitted, the current Session will be used automatically. When targeting a different session, then the pageId parameter must be included in the call. [optional] |
| pageId | String | Identifier of the page to target. If omitted, the current page will be used. [optional] |
| idp | String | The name of the IdP to use for this authentication challenge. If omitted, the Project default IdP will be used. [optional] |
| forceAuth | Boolean | True if Ignition should ask the IdP to re-authenticate the user, even if the user is already signed into the IdP. False if Ignition should not ask the IdP to re-authenticate the user. If the IdP supports this option, the IdP will ask the user to re-enter their credentials, even if the user is already signed into the IdP. If omitted, the default value for this argument will fall back to the value in the Project Properties. [optional] |
| timeout | Integer | The number of minutes the system will wait in between the authentication request and the authentication response before timing out the request. If set to any number <= zero, the request is rejected. If omitted, the default of two minutes will be used as the timeout. [optional] |
| payload | Any | An opaque payload object that may contain any information. This object will be passed to theonAuthenticationChallengeCompletedsession event script. The payload should be a JSON-encodable data structure. [optional] |
| framing | String | A string representing the type of framing that should be used. A value ofselfindicates that the same window should be used. A value ofnewindicates that a new tab should be used. A value ofembeddedindicates that an embedded iframe should be used. If omitted, the default value ofself(same window) is used. [optional]Note:Mobile and Workstation Clients do not supportnewand will fall back toself. Mobile Clients do not supportembeddedand will fall back toself. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.authenticationChallenge([sessionId], [pageId], [idp], [forceAuth], [timeout], [payload], [framing])
```


---

# system.perspective.closeDock

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Closes a docked view. This function acceptskeyword arguments.

## 語法

```python
system.perspective.closeDock(id, [sessionId], [pageId])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| id | String | The unique, preconfigured dock ID for the docked view. Is specified when a view is assigned as docked for a particular page (in Page Configuration). |
| sessionId | String | Identifier of the Session to target. If omitted, the current Session will be used automatically. When targeting a different session, then the pageId parameter must be included in the call. [optional] |
| pageId | String | Identifier of the page to target. If omitted, the current page will be used automatically. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.closeDock(id, [sessionId], [pageId])
```


---

# system.perspective.closePage

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Closes the page with the given page id or the current page if no page id is provided. If a message is provided, it is displayed on the page when the page closes. Otherwise the default message (set in theProject properties) is displayed. system.perspective.closePage([message], [sessionId], [pageID])

## 語法

```python
system.perspective.closePage([message], [sessionId], [pageID])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| message | String | The message to display when the page closes. If omitted, the default message (set in the Project Properties) is shown. [optional] |
| sessionId | String | Identifier of the Session to target. If omitted, the current Session will be used automatically. When targeting a different Session, the pageId parameter must be included in the call. [optional] |
| pageId | String | Identifier of the page to be closed. If omitted, the current pageId is used. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.closePage([message], [sessionId], [pageID])
```


---

# system.perspective.closePopup

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Closes a popup view. This function acceptskeyword arguments.

## 語法

```python
system.perspective.closePopup(id, [sessionId], [pageId])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| id | String | The unique identifier for the popup, given to the popup when first opened. If given an empty string, then the most recently focused popup will be closed. |
| sessionId | String | Identifier of the Session to target. If omitted, the current Session will be used automatically. When targeting a different session, then the pageId parameter must be included in the call. [optional] |
| pageId | String | Identifier of the page to target. If omitted, the current Page will be used automatically. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.closePopup(id, [sessionId], [pageId])
```


---

# system.perspective.closeSession

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Closes the Perspective Session with the given sessionID or the current Session if no ID is provided. If a message is provided, it is displayed on the page when the Session closes. Otherwise the default message (set in theProject properties) is displayed. In the Perspective App, the user is returned to the launch screen.

## 語法

```python
system.perspective.closeSession([message], [sessionId])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| message | String | The message to display when the Session closes. If omitted, the default message (set in theProject properties) is shown. [optional] |
| sessionId | String | Identifier of the Session to be closed. If omitted, the current sessionId is used. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.closeSession([message], [sessionId])
```


---

# system.perspective.download

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Downloads data from the Gateway to a device running a Session. When calling from the Gateway scope, the call must include a sessionId.

## 語法

```python
system.perspective.download(filename, data,  [contentType], sessionId, [pageId])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| filename | String | Suggested name for the downloaded file. |
| data | String | The data to be downloaded. May be a string, a byte[], or an InputStream. Strings will be written in UTF-8 encoding. |
| contentType | String | Value for the "Content-Type" header, for example: "text/plain; charset=utf-8". [optional] |
| sessionId | String | Identifier of the Session to target. If omitted, the current Session will be used automatically. When targeting a different session, then the pageId parameter must be included in the call. |
| pageId | String | Identifier of the page to target. If omitted, the current page will be used automatically. [optional] |
| filename | String | Suggested name for the downloaded file. |
| data | String | The data to be downloaded. May be a string, a byte[], or an InputStream. Strings will be written in UTF-8 encoding. |
| contentType | String | Value for the "Content-Type" header, for example: "text/plain; charset=utf-8". [optional] |
| sessionId | String | Identifier of the Session to target. If omitted, the current Session will be used automatically. When targeting a different session, then the pageId parameter must be included in the call. [optional] |
| pageId | String | Identifier of the page to target. If omitted, the current page will be used automatically. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.download(filename, data,  [contentType], sessionId, [pageId])
```


---

# system.perspective.getProjectInfo

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Returns a dictionary of meta data from a Perspective Project. Exact fields are as follows:

## 語法

```python
system.perspective.getProjectInfo()
```

## 回傳值

**型別：** Object

## 範例

### Example 2

```python
primaryView
```

### Example 3

```python
system.perspective.getProjectInfo()
```


---

# system.perspective.getSessionInfo

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Returns information about one or more Perspective Sessions. The information returned by this function is a combination of information available on thePerspective Sessions statuspage on the Gateway, and some Session props (id and userAgent). Exact fields are as follows: This function acceptskeyword arguments.

## 語法

```python
system.perspective.getSessionInfo([usernameFilter], [projectFilter])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| usernameFilter | String | A filter based on logged in user. [optional] |
| projectFilter | String | A filter based on the project name. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.getSessionInfo([usernameFilter], [projectFilter])
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

# system.perspective.isAuthorized

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Checks if the user in the current Session is authorized against a target collection of security levels. system.perspective.isAuthorized(isAllOf, securityLevels, [sessionID])

## 語法

```python
system.perspective.isAuthorized(isAllOf, securityLevels, [sessionID])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| isAllOf | Boolean | True if the current user must have all of the given security levels to be authorized. False if the current user must have at least one of the given security levels to be authorized. |
| securityLevels | List[String] | An array of string paths to a security level node in the form of "Path/To/Node". Each level in the tree is delimited by a forward slash character. The public node is never a part of the path. |
| sessionId | String | New in8.1.3Identifier of the Session to target. If omitted, the current Session will be used automatically. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.isAuthorized(isAllOf, securityLevels, [sessionID])
```

### Example 3

```python
securityLevels
```


---

# system.perspective.login

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Triggers a login event that will allow the user to log in with the project's configured Identity Provider (IdP). For this function to work, an IdP must be set in PerspectiveProject properties. This is particularly useful when you want it to be possible to start a session without authentication and sign in to access certain restricted features. Note that calling this function after a user is already logged in willnotlog out the previous user.

## 語法

```python
system.perspective.login([sessionId], [pageId], [forceAuth])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| sessionId | String | Identifier of the Session to target. If omitted, the current Session will be used automatically. When targeting a different session, then the pageId parameter must be included in the call. [optional] |
| pageId | String | Identifier of the Page to target. If omitted, the current Page will be used automatically. [optional] |
| forceAuth | Boolean | Determines if Ignition should ask the IdP to re-authenticate the user, even if the user is already signed into the IdP. If set to true, then the IdP will ask the user to re-enter their credentials. If set to false, then the Gateway will request that the IdP use the last provided credentials for the Session, potentially allowing re-authentication without requiring the user to re-type their credentials. Note that support for this argument is determined by the IdP; the IdP may choose to ignore this request. If this parameter is omitted, then the function will use the re-authentication setting defined underProject properties. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.login([sessionId], [pageId], [forceAuth])
```


---

# system.perspective.logout

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Triggers a logout event, which will log the user out. For this function to work, an Identity Provider (IdP) must be set in thePerspective Project properties. Be advised that this function should not be used in the same script, or in the same triggering event assystem.perspective.login. Logging in and Logging out should always be triggered by separate events.

## 語法

```python
system.perspective.logout([sessionId], [pageId], [message])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| sessionId | String | Identifier of the Session to target. If omitted, the current Session will be used automatically. When targeting a different Session, then the pageId parameter must be included in the call. [optional] |
| pageId | String | Identifier of the Page to target. If omitted, the current Page will be used automatically. [optional] |
| message | String | New in8.1.8The message to display when the user logs out of their session. This message is only shown when the project requires authentication. If omitted, the default message (set inProject Properties) is shown. [Optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.logout([sessionId], [pageId], [message])
```


---

# system.perspective.navigate

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Navigate the session to a specified view or mounted page. The function can be used in three different ways, depending on which parameter is specified:

## 語法

```python
system.perspective.navigate(page, [url], [view], [params], [sessionId], [pageId], [newTab])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| page | String | The URL of a Perspective page to navigate to. The path can include an optional leading slash: "new-page" and "/new-page" both result cause the session to navigate to the "new-page" page. SeePage URLs. |
| url | String | The URL of a web address to navigate to. If the page or view parameters are specified, then this parameter is ignored. [optional] |
| view | String | If specified, will navigate to a specific view. Navigating to a view with this parameter does not change the address in the web browser. Thus the web browser's back button will not be able to return the user to the previous view. If the page parameter is specified, then this parameter is ignored. [optional] |
| params | Dictionary[String, String] | Used only in conjunction with the view parameter, Dictionary of values to pass to any parameters on the view. [optional] |
| sessionId | String | Identifier of the Session to target. If omitted, the current Session will be used automatically. When targeting a different session, then the pageId parameter must be included in the call. [optional] |
| pageId | String | Identifier of the page to target. If omitted, the current page will be used automatically. [optional] |
| newTab | Boolean | New in8.1.5If True, opens the contents in a new tab. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.navigate(page, [url], [view], [params], [sessionId], [pageId], [newTab])
```


---

# system.perspective.navigateBack

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Navigate the session to a specified view or mounted page. This is similar to a browser's "back" function.

## 語法

```python
system.perspective.navigateBack([sessionId], [pageId])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| sessionId | String | Identifier of the Session to target. If omitted, the current Session will be used automatically. [optional] |
| pageId | String | Identifier of the page to target. If omitted, the current page will be used automatically. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.navigateBack([sessionId], [pageId])
```


---

# system.perspective.navigateForward

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Navigate the session to a specified view or mounted page. This is similar to a browser's "forward" function.

## 語法

```python
system.perspective.navigateForward([sessionId], [pageId])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| sessionId | String | Identifier of the Session to target. If omitted, the current Session will be used automatically. When targeting a different session, then the pageId parameter must be included in the call. [optional] |
| pageId | String | Identifier of the page to target. If omitted, the current page will be used automatically. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.navigateForward([sessionId], [pageId])
```


---

# system.perspective.openDock

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Opens a docked View. Requires the preconfigured dock ID for the view. system.perspective.openDock(id, [sessionId], [pageId])

## 語法

```python
system.perspective.openDock(id, [sessionId], [pageId])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| id | String | The unique, preconfigured dock ID for the docked View. Is specified when a View is assigned as docked for a particular Page (in Page Configuration). |
| sessionId | String | Identifier of the Session to target. If omitted, the current Session will be used automatically. When targeting a different Session, then the pageId parameter must be included in the call. [optional] |
| pageId | String | Identifier of the Page to target. If omitted, the current Page will be used automatically. [optional] |
| params | Dictionary[String, String] | Parameters that can be passed into the docked view. Must match the docked views View Parameters. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.openDock(id, [sessionId], [pageId])
```


---

# system.perspective.openPopup

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Open apopup viewover the given page. system.perspective.openPopup(id, view, [params], [title], [position], [showCloseIcon], [draggable], [resizable], [modal], [overlayDismiss], [sessionId], [pageId], [viewportBound])

## 語法

```python
system.perspective.openPopup(id, view, [params], [title], [position], [showCloseIcon], [draggable], [resizable], [modal], [overlayDismiss], [sessionId], [pageId], [viewportBound])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| id | String | A unique popup string. Will be used to close the popup from other popup or script actions. |
| view | String | The path to the View to use in the popup. |
| params | Dictionary[String, Any] | Dictionary of key-value pairs to use as input parameters to the View. [optional] |
| title | String | Text to display in the title bar. Defaults to an empty string. [optional] |
| position | Dictionary[String, Integer] | Dictionary of key-value pairs to use for position. Possible position keys are: left, top, right, bottom, width, height. Defaults to the center of the window. [optional] |
| showCloseIcon | Boolean | Shows the close icon if True. Defaults to True. [optional] |
| draggable | Boolean | Allows the popup to be dragged if True. Defaults to True. [optional] |
| resizable | Boolean | Allows the popup to be resized if True. Defaults to False. [optional] |
| modal | Boolean | Makes the popup modal if True. A modal popup is the only view the user can interact with. Defaults to False. [optional] |
| overlayDismiss | Boolean | Allows the user to dismiss and close a modal popup by clicking outside of it if True. Defaults to False.[optional] |
| sessionId | String | Identifier of the Session to target. If omitted, the current Session will be used automatically. [optional] |
| pageId | String | Identifier of the Page to target. If omitted, the current Page will be used automatically. When targeting a different session, then this parameter must be included in the call. [optional] |
| viewportBound | Boolean | New in8.1.3If True,  popups will be "shifted" to always open within the bounds of the viewport. If the popup would be larger than the viewport, then it will be resized to fit within the bounds. Default is False. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.openPopup(id, view, [params], [title], [position], [showCloseIcon], [draggable], [resizable], [modal], [overlayDismiss], [sessionId], [pageId], [viewportBound])
```


---

# system.perspective.print

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Prints the supplied message to the local console (or the gateway logs, as appropriate) - by default, this means the Output Console when in the Designer, and the browser's console when in a live session. system.perspective.print([message], [sessionId], [pageId], [destination])

## 語法

```python
system.perspective.print([message], [sessionId], [pageId], [destination])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| message | String | The print statement that will be displayed on the console. [optional] |
| sessionId | String | Identifier of the Session to target. If omitted, the current Session will be used automatically. When targeting a different session, then the pageId parameter must be included in the call. [optional] |
| pageId | String | Identifier of the page to target. If omitted, the current Page will be used automatically. [optional] |
| destination | String | Where the message should be printed. If specified, must be "client", "gateway", or "all". Default is "client". [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.print([message], [sessionId], [pageId], [destination])
```


---

# system.perspective.refresh

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Triggers a refresh of the page. This method should not be confused with therefreshBindingcomponent method, which automatically fires a binding on a Perspective component property.

## 語法

```python
system.perspective.refresh([sessionId], [pageId])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| sessionId | String | Identifier of the Session to target. If omitted, the current Session will be used automatically. When targeting a different session, then the pageId parameter must be included in the call. [optional] |
| pageId | String | Identifier of the page to target. If omitted, the current Page will be used automatically. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.refresh([sessionId], [pageId])
```


---

# system.perspective.sendMessage

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Send a message to acomponent message handlerwithin the same session. This function cannot interact with Session Message Handlers configured in Session Events, even if thescopeof session is specified. Invoked Message Handlersexecute asynchronouslyto the calling script.

## 語法

```python
system.perspective.sendMessage(messageType, payload, [scope], [sessionId], [pageId])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| messageType | String | The message type that will be invoked. Message handlers configured within the project are listening for messages of a specific messageType. |
| payload | Dictionary[String, String] | A Python dictionary representing any parameters that will be passed to the message handler. |
| scope | String | The scope that the message should be delivered to. Valid values are "session", "page", or "view". If omitted, "page" will be used. [optional] |
| sessionId | String | Identifier of the Session to target. If omitted, the current Session will be used automatically. When targeting a different session, then the pageId parameter must be included in the call. [optional] |
| pageId | String | Identifier of the page to target. If omitted, the current page will be used. [optional] |

## 回傳值

**型別：** Object


---

# system.perspective.setTheme

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Changes the theme in a page to the specified theme. Note that this function only changes the theme for a single page, not the entire session. To change the theme for a session, write directly to thesession.themeproperty instead.

## 語法

```python
system.perspective.setTheme(name, [sessionId], [pageId])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| name | String | The theme name to switch to. Possible values are "dark" or "light". |
| sessionId | String | Identifier of the Session to target. If omitted, the current Session will be used automatically. When targeting a different session, then the pageId parameter must be included in the call. [optional] |
| pageId | String | Identifier of the page to target. If omitted, the current page will be used automatically. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
session.theme
```

### Example 2

```python
system.perspective.setTheme(name, [sessionId], [pageId])
```


---

# system.perspective.toggleDock

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Toggles a docked view. system.perspective.toggleDock(id, [sessionId], [pageId])

## 語法

```python
system.perspective.toggleDock(id, [sessionId], [pageId])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| id | String | The unique, preconfigured 'Dock ID' for the docked view. Is specified when a view is assigned as docked for a particular page (in Page Configuration). |
| sessionId | String | Identifier of the Session to target. If omitted, the current Session will be used automatically. When targeting a different session, then the pageId parameter must be included in the call. [optional] |
| pageId | String | Identifier of the Page to target. If omitted, the current Page will be used automatically. [optional] |
| params | Dictionary[String, String] | Parameters that can be passed into the docked view. Must match the docked views View Parameters. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.toggleDock(id, [sessionId], [pageId])
```


---

# system.perspective.togglePopup

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. Toggles apopup view. Will open up the popup if it has not been opened yet. Otherwise, it will close the currently opened popup. system.perspective.togglePopup(id, view, [params], [title], [position], [showCloseIcon], [draggable], [resizable], [modal], [overlayDismiss], [sessionId], [pageId], [viewportBound])

## 語法

```python
system.perspective.togglePopup(id, view, [params], [title], [position], [showCloseIcon], [draggable], [resizable], [modal], [overlayDismiss], [sessionId], [pageId], [viewportBound])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| id | String | A unique popup string. Will be used to close the popup from other popup or script actions. |
| view | String | The path to the view to use in the popup. |
| params- Dictionary of key-value pairs to us as input parameters to the View. [optional] | Dictionary[String, Any] |  |
| title | String | Text to display in the title bar. Defaults to an empty string. [optional] |
| position | Dictionary[String, Integer] | Dictionary of key-value pairs to use for position. Possible position keys are: left, top, right, bottom, width, height. Defaults to the center of the window. [optional] |
| showCloseIcon | Boolean | Will show the close icon if True. Defaults to True. [optional] |
| draggable | Boolean | Will allow the popup to be dragged if True. Defaults to True. [optional] |
| resizable | Boolean | Will allow the popup to be resized if True. Defaults to False. [optional] |
| modal | Boolean | Will make the popup modal if True. A modal popup is the only view the user can interact with. Defaults to False. [optional] |
| overlayDismiss | Boolean | Will allow the user to dismiss and close a modal popup by clicking outside of it if True. Defaults to False. [optional] |
| sessionId | String | Identifier of the Session to target. If omitted, the current Session will be used automatically. When targeting a different session, then the pageId parameter must be included in the call. [optional] |
| pageId | String | Identifier of the page to target. If omitted, the current Page will be used automatically. [optional] |
| viewportBound | Boolean | New in8.1.3If True,  popups will be "shifted" to open within the bounds of the viewport. If the popup would be larger than the viewport, then it will be resized to fit within the bounds. Default is False. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.togglePopup(id, view, [params], [title], [position], [showCloseIcon], [draggable], [resizable], [modal], [overlayDismiss], [sessionId], [pageId], [viewportBound])
```


---

# system.perspective.vibrateDevice

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. When called from thePerspective App, will cause the device to vibrate for the specified number of milliseconds. iOS vibration duration is fixed. This function will cause an iOS device to vibrate for its default duration, 0.4 seconds (400 milliseconds).

## 語法

```python
system.perspective.vibrateDevice(integer, [sessionId])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| duration | String | The duration in milliseconds to vibrate the device.Note:iOS vibration duration is fixed. Thus, this parameter will not impact the vibration duration on devices running iOS. |
| sessionId | String | Identifier of the Session to target. If omitted, the current Session will be used automatically. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.vibrateDevice(integer, [sessionId])
```


---

# system.perspective.workstation

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

The following functions offer various ways to interact with Perspective Workstation from a Python script. Note that the functions here only work when called from a session running in Perspective Workstation. When called from a session running in Workstation, this function will close Workstation. Attempts to put Workstation into Kiosk mode.

## 回傳值

**型別：** Object


---

# system.perspective.workstation.exit

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. When called from a session running in Workstation, this function will close Workstation. system.perspective.workstation.exit()

## 語法

```python
system.perspective.workstation.exit()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.workstation.exit()
```

### Example 2

```python
# This example will close the current Perspective Workstation Session.
system.perspective.workstation.exit()
```

### Example 3

```python
# This example will close the current Perspective Workstation Session.
system.perspective.workstation.exit()
```


---

# system.perspective.workstation.toKiosk

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. When called from a session running inPerspective Workstation, attempts to put Workstation into Kiosk mode. system.perspective.workstation.toKiosk()

## 語法

```python
system.perspective.workstation.toKiosk()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.workstation.toKiosk()
```

### Example 2

```python
# This example will set a Perspective Workstation Session into Kiosk mode.
system.perspective.workstation.toKiosk()
```

### Example 3

```python
# This example will set a Perspective Workstation Session into Kiosk mode.
system.perspective.workstation.toKiosk()
```


---

# system.perspective.workstation.toWindowed

**版本：** 8.1
**型別：** Scripting
**分類：** Perspective

## 詳述

This function is used inPython Scripting. When called from a Session running inPerspective Workstation, attempts to put Workstation into windowed mode. system.perspective.workstation.toWindowed()

## 語法

```python
system.perspective.workstation.toWindowed()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.perspective.workstation.toWindowed()
```

### Example 2

```python
# This example will set the Perspective Workstation Session to windowed mode.
system.perspective.workstation.toWindowed()
```

### Example 3

```python
# This example will set the Perspective Workstation Session to windowed mode.
system.perspective.workstation.toWindowed()
```


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

# system.project.getProjectName

**版本：** 8.1
**型別：** Scripting
**分類：** Project

## 詳述

This function is used inPython Scripting. Returns the name of the project where the function was called from. When called from the Gateway scope from a resource that originates from a singular project (reports, SFCs, etc.), will return that resources project. Resources that run in the Gateway scope, but are configured in a singular project (such as a report), will use that project's name. When called from a scope that does not have an associated project (a Tag Event Script), the function will re

## 語法

```python
system.project.getProjectName()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.project.getProjectName()
```

### Example 2

```python
# This code displays the name of the currently running project to the appropriate console,
# depending on scope (Designer console, Gateway console, etc.).
system.util.getLogger("myLogger").warn("You are running project: %s" % system.project.getProjectName())
```

### Example 3

```python
# This code displays the name of the currently running project to the appropriate console,
# depending on scope (Designer console, Gateway console, etc.).
system.util.getLogger("myLogger").warn("You are running project: %s" % system.project.getProjectName())
```


---

# system.project.getProjectNames

**版本：** 8.1
**型別：** Scripting
**分類：** Project

## 詳述

This function is used inPython Scripting. Returns an unsorted collection of strings, where each string represents the name of a project on the Gateway. If no projects exist, returns an empty list. This function only ever returns project names, ignoring project titles. The function also ignores the "enabled" property, including disabled projects in the results.

## 語法

```python
system.project.getProjectNames()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.project.getProjectNames()
```

### Example 2

```python
# Calling this from the Script Console prints out each project name.
print system.project.getProjectNames()
```

### Example 3

```python
# Calling this from the Script Console prints out each project name.
print system.project.getProjectNames()
```


---

# system.project.requestScan

**版本：** 8.1
**型別：** Scripting
**分類：** Project

## 詳述

This function is used inPython Scripting. Requests a manual scan of the projects directory in order to refresh projects and their resources. If a scan is currently running, this method has no effect and will return when the in-progress scan has finished. This function blocks the current thread until a scan has completed. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.project.requestScan([timeout])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| timeout | Integer | The amount of time, in seconds, to block the current thread before timing out. Default is 10 seconds. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.project.requestScan([timeout])
```

### Example 3

```python
# This example requests a manual scan of the project directory
# while blocking the current thread for 30 seconds before timing out.
system.project.requestScan(30)
```


---

# system.report.executeAndDistribute

**版本：** 8.1
**型別：** Scripting
**分類：** Report

## 詳述

This function is used inPython Scripting. Executes and distributes a report. Similar toscheduling a report to execute, except a schedule is not required to utilize this function. This is a great way to distribute the report on demand from a Client. Throws an IllegalArgumentException when any of the following occurs: If the file type is not recognized, path does not exist, project does not exist, or a key is not valid. The function system.report.executeAndDistribute() does not run on its own thre

## 語法

```python
system.report.executeAndDistribute(path, project, [parameters], action, [actionSettings])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| path | String | The path to the existing report. |
| project | String | The name of the project where the report is located. Optional in client scope. |
| parameters | Dictionary[String, Integer] | A dictionary of parameter overrides, in the form name:valuepairs. [optional] |
| action | String | The name of the distribution action to use. The action parameter supports the following keys as strings:emailprintsaveftp |
| actionSettings | Dictionary[List, Any] | A dictionary of settings particular to the action. Missing values will use the default value for that action. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.report.executeAndDistribute(path, project, [parameters], action, [actionSettings])
```


---

# system.report.executeReport

**版本：** 8.1
**型別：** Scripting
**分類：** Report

## 詳述

This function is used inPython Scripting. Immediately executes an existing report and returns a List[Byte] of the output. Throws an IllegalArgumentException when any of the following occurs: If the file type is not recognized, path does not exist, project does not exist. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.report.executeReport(path, project, [parameters], fileType)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| path | String | The path to the existing report. |
| project | String | The name of the project where the report is located. Optional in client scope. |
| parameters | Dictionary[String, Integer] | A dictionary of parameter overrides, in the form name:value. [optional] |
| fileType | String | The file type the resulting byte array should represent. Defaults to "pdf". Not case-sensitive |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.report.executeReport(path, project, [parameters], fileType)
```


---

# system.report.getReportNamesAsDataset

**版本：** 8.1
**型別：** Scripting
**分類：** Report

## 詳述

This function is used inPython Scripting. Gets a data of all reports for a project. Throws an IllegalArgumentException when any of the following occurs: If the project name is omitted in the Gateway scope, project does not exist. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.report.getReportNamesAsDataset([ project], [includeReportName])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| project | String | The name of the project where the reports are located. Optional in client scope. |
| includeReportName | Boolean | New in8.1.5When set to False, the end of Path does not include the report name. Default is True. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.report.getReportNamesAsDataset([ project], [includeReportName])
```

### Example 3

```python
includeReportName
```


---

# system.report.getReportNamesAsList

**版本：** 8.1
**型別：** Scripting
**分類：** Report

## 詳述

This function is used inPython Scripting. Gets a list of all reports for a project. Throws an IllegalArgumentException when any of the following occurs: If the project name is omitted in the Gateway scope or if project does not exist. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.report.getReportNamesAsList(project)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| project | String | The name of the project where the reports are located. Optional in Client scope and Perspective Session scope. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.report.getReportNamesAsList(project)
```

### Example 3

```python
# Gets a list of reports for the current project and prints it.
reports = system.report.getReportNamesAsList()
for report in reports:
    print report

"""Output from the above example looks like the following:
Comparisons
Line Reports/Line 1/Defect rates
Line Reports/Line 1/Production
Line Reports/Line 2/Defect Rates
"""
```


---

# system.roster.addUsers

**版本：** 8.1
**型別：** Scripting
**分類：** Roster

## 詳述

This function is used inPython Scripting. Adds a list of users to an existing roster. Users are always appended to the end of the roster. system.roster.addUsers(rosterName, [users])

## 語法

```python
system.roster.addUsers(rosterName, [users])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| rosterName | String | The name of the roster to modify. |
| users | List | A list ofUserobjects that will be added to the end of the roster. User objects can be created with thesystem.user.getUserandsystem.user.addUserfunctions. These users must exist before being added to the roster. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.roster.addUsers(rosterName, [users])
```


---

# system.roster.createRoster

**版本：** 8.1
**型別：** Scripting
**分類：** Roster

## 詳述

This function is used inPython Scripting. Creates a roster with the given name and description, if it does not already exist. This function was designed to run in the Gateway and in Perspective sessions. If creating rosters from Vision clients, usesystem.alarm.createRosterinstead

## 語法

```python
system.roster.createRoster(name, description)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| name | String | The name of the roster to create. |
| description | String | The description for the roster. May be None, but the parameter is mandatory. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.roster.createRoster(name, description)
```

### Example 3

```python
description
```


---

# system.roster.deleteRoster

**版本：** 8.1
**型別：** Scripting
**分類：** Roster

## 詳述

This function is used inPython Scripting. Deletes a roster with the given name.

## 語法

```python
system.roster.deleteRoster(rosterName)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| name | String | The name of the roster to delete. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.roster.deleteRoster(rosterName)
```

### Example 3

```python
system.roster.deleteRoster("some roster")
```


---

# system.roster.getRoster

**版本：** 8.1
**型別：** Scripting
**分類：** Roster

## 詳述

This function is used inPython Scripting. Returns the roster corresponding to the given name. You can call getUsers() to access a list of User objects in the RosterModel.

## 語法

```python
system.roster.getRoster(rosterName)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| name | String | The name of the roster to get the RosterModel object from. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.roster.getRoster(rosterName)
```

### Example 3

```python
# This example gets the RosterModel object from a roster called "some roster" when a Button is pressed and prints the object to the browser console.

roster = system.roster.getRoster("some roster")
system.perspective.print(roster)
```


---

# system.roster.getRosterNames

**版本：** 8.1
**型別：** Scripting
**分類：** Roster

## 詳述

This function is used inPython Scripting. Returns a list of roster names.

## 語法

```python
system.roster.getRosterNames()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.roster.getRosterNames()
```

### Example 2

```python
# This example gets a list of rosters from the Gateway when a Button is pressed and prints the list to the browser console.

roster = system.roster.getRosterNames()
system.perspective.print(roster)
```

### Example 3

```python
# This example gets a list of rosters from the Gateway when a Button is pressed and prints the list to the browser console.

roster = system.roster.getRosterNames()
system.perspective.print(roster)
```


---

# system.roster.getRosters

**版本：** 8.1
**型別：** Scripting
**分類：** Roster

## 詳述

This function is used inPython Scripting. Returns a dictionary of rosters, where the key is the name of the roster, and the value is an array list of string user names. This function was designed to run in the Gateway and in Perspective sessions. If creating rosters from Vision clients, usesystem.alarm.getRostersinstead.

## 語法

```python
system.roster.getRosters()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.roster.getRosters()
```

### Example 2

```python
# This example prints out all existing rosters to the console of a Perspective session:

rosters = system.roster.getRosters()

# Iterate over the rosters, extracting the name and user lists.
for name, users in rosters.items():

    # Format the results in a somewhat presentable manner.
    msg = "{0} : {1}".format(name, users)

    # Output the result.
    system.perspective.print(msg)
```

### Example 3

```python
# This example prints out all existing rosters to the console of a Perspective session:

rosters = system.roster.getRosters()

# Iterate over the rosters, extracting the name and user lists.
for name, users in rosters.items():

    # Format the results in a somewhat presentable manner.
    msg = "{0} : {1}".format(name, users)

    # Output the result.
    system.perspective.print(msg)
```


---

# system.roster.removeUsers

**版本：** 8.1
**型別：** Scripting
**分類：** Roster

## 詳述

This function is used inPython Scripting. Removes one or more users from an existing roster. system.roster.removeUsers(rosterName, users)

## 語法

```python
system.roster.removeUsers(rosterName, users)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| rosterName | String | The name of the roster to modify. |
| users | List | A list ofuserobjects that will be removed from the roster. User objects can be created with thesystem.user.getUserandsystem.user.addUserfunctions. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.roster.removeUsers(rosterName, users)
```


---

# system.secsgem.copyEquipment

**版本：** 8.1
**型別：** Scripting
**分類：** Secsgem

## 詳述

This function is used inPython Scripting. Creates a copy of an equipment connection and places it in the Gateway > Config > SECS/GEM > Equipment. Common settings can be overridden for the new connection. An exception is thrown if the new equipment connection cannot be created.

## 語法

```python
system.secsgem.copyEquipment( equipmentSource, newEquipmentName, enabled, activeAddress, activePort, passiveAddress, passivePort, deviceId [, dbTablePrefix] [,description])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| equipmentSource | String | Some new equipment settings will be retrieved from this equipment connection. Specify the source equipment connection name. |
| newEquipmentName | String | The name of the new equipment connection. |
| enabled | Boolean | If set to false, the new equipment connection will be disabled after it is created. |
| activeAddress | String | IP Address of new equipment. Must be specified if the SECS/GEM module is used in Active mode. Otherwise, do not use this parameter. |
| activePort | Integer | Port number of new equipment. Must be specified if the SECS/GEM module is used in Active mode. Otherwise, do not use this parameter. |
| passiveAddress | String | IP Address of new equipment. Must be specified if the SECS/GEM module is used in Passive mode. Otherwise, do not use this parameter. |
| passivePort | Integer | Port number of new equipment. Must be specified if the SECS/GEM module is used in Passive mode. Otherwise, do not use this parameter. |
| deviceId | Integer | Unique identifier of new equipment. This value must be an integer, and is specified within the equipment. |
| dbTablePrefix | String | SECS/GEM database table names will use the specified prefix for the new equipment connection. If no prefix is specified, the description of the source equipment will be used. Optional. |
| description | String | The description for the new equipment connection. If no description is specified, the description of the source equipment will be used. Optional. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.secsgem.copyEquipment( equipmentSource, newEquipmentName, enabled, activeAddress, activePort, passiveAddress, passivePort, deviceId [, dbTablePrefix] [,description])
```

### Example 2

```python
equipmentSource
```

### Example 3

```python
newEquipmentName
```


---

# system.secsgem.deleteToolProgram

**版本：** 8.1
**型別：** Scripting
**分類：** Secsgem

## 詳述

This function is used inPython Scripting. Deletes a process program from the Gateway. Permission Type: SECS/GEM Management

## 語法

```python
system.secsgem.deleteToolProgram(ppid)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| ppid | String | The PPID that was sent from the tool when the S7F3 message was saved. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.secsgem.deleteToolProgram(ppid)
```

### Example 3

```python
# Name of the Tool Program that will be deleted
targetProgram = "Old Program"

system.secsgem.deleteToolProgram(targetProgram)
```


---

# system.secsgem.enableDisableEquipment

**版本：** 8.1
**型別：** Scripting
**分類：** Secsgem

## 詳述

This function is used inPython Scripting. Enables or disables a Tuple of equipment connections from a script. Permission Type: SECS/GEM Management

## 語法

```python
system.secsgem.enableDisableEquipment(enable, names)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| enable | Boolean | Set to True to enable equipment connections, or set to False to disable them. |
| names | Tuple | A Tuple of Strings. Each String should match an Equipment Connection configured on the Gateway. If this parameter contains the name of an Equipment Connection that does not exist, then a message will be included in the List returned by this function. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.secsgem.enableDisableEquipment(enable, names)
```


---

# system.secsgem.getResponse

**版本：** 8.1
**型別：** Scripting
**分類：** Secsgem

## 詳述

This function is used inPython Scripting. Attempts to retrieve a response message from the Gateway. The transaction id from the sent message is used to retrieve the response. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.secsgem.getResponse(transactionID, equipment, [timeout], [poll])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| transactionID | Integer | The transactionID of the request and response. The transactionID is used to retrieve the response. Typically used in conjunction withsystem.secsgem.sendRequestto generate a transactionID. |
| equipment | String | Name of equipment connection. |
| timeout | Integer | Specifies in seconds how long to wait for a response before returning None. If omitted the timeout will be 5 seconds. |
| poll | Integer | Specifies in milliseconds how often to poll the system for a response. If omitted the poll will be 150 milliseconds. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.secsgem.getResponse(transactionID, equipment, [timeout], [poll])
```

### Example 2

```python
transactionID
```


---

# system.secsgem.getToolProgram

**版本：** 8.1
**型別：** Scripting
**分類：** Secsgem

## 詳述

This function is used inPython Scripting. Returns a process program from the Gateway that was previously sent by a a tool in an S7F3 message. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.secsgem.getToolProgram(ppid)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| ppid | String | The PPID that was sent from the tool when the S7F3 message was saved. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.secsgem.getToolProgram(ppid)
```


---

# system.secsgem.getToolProgramDataset

**版本：** 8.1
**型別：** Scripting
**分類：** Secsgem

## 詳述

This function is used inPython Scripting. Returns a Dataset containing information about all stored process programs. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.secsgem.getToolProgramDataset()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.secsgem.getToolProgramDataset()
```


---

# system.secsgem.sendRequest

**版本：** 8.1
**型別：** Scripting
**分類：** Secsgem

## 詳述

This function is used inPython Scripting. Sends a JSON-formatted SECS message to a tool. An equipment connection must be configured for the tool in the Gateway. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.secsgem.sendRequest(streamFunction, reply, body, equipment)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| streamFunction | String | The stream and function of the SECS message to send. Example: "S1F13" |
| reply | Boolean | Whether or not the SECS message expects a reply message. |
| body | Object | This contains the body of a SECS message. The argument can be a Python Object or JSON string representing the body of a SECS message. If this argument is a string then it will be converted to a Python Object using thesystem.util.jsonDecodefunction. |
| equipment | String | Name of the equipment connection to use. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.secsgem.sendRequest(streamFunction, reply, body, equipment)
```

### Example 2

```python
streamFunction
```


---

# system.secsgem.sendResponse

**版本：** 8.1
**型別：** Scripting
**分類：** Secsgem

## 詳述

This function is used inPython Scripting. Sends a JSON-formatted SECS response message to a message sent by a tool. An equipment connection must be configured for the tool in the Gateway, and this must be used within a Message Handler to create aCustom Message Response Handler. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.secsgem.sendResponse(transactionID, systemBytes, streamFunction, body, equipment)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| transactionID | Integer | The TxID of the response. The TxID from the received request in the payload of the message handler must be specified here. |
| systemBytes | Integer | The SystemBytes of the response. The SystemBytes from the received request in the payload of the message handler must be specified here. |
| streamFunction | String | The stream and function of the SECS message to send. Example: "S1F14" |
| body | Any | This contains the body of a SECS response. The argument can be a Python Object or JSON string representing the body of a SECS message. If this argument is a string then it will be converted to a Python Object using thesystem.util.jsonDecodefunction. |
| equipment | String | Name of the equipment connection to use. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.secsgem.sendResponse(transactionID, systemBytes, streamFunction, body, equipment)
```

### Example 2

```python
transactionID
```

### Example 3

```python
systemBytes
```


---

# system.secsgem.startSimEventRun

**版本：** 8.1
**型別：** Scripting
**分類：** Secsgem

## 詳述

This function is used inPython Scripting. Starts a configured simulator event run in the Gateway. Note, that this function only works with the simulators that come included with the SECS/GEM module. The function will throw an exception if the specified Event Run cannot be started.

## 語法

```python
system.secsgem.startSimEventRun(simulatorName, eventRunName)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| simulatorName | String | The simulator that holds the configured event run. Will throw an exception if the specified simulator can't be found. |
| eventRunName | String | The event run to start. Will throw an exception if the specified simulator can't be found. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.secsgem.startSimEventRun(simulatorName, eventRunName)
```

### Example 2

```python
simulatorName
```

### Example 3

```python
eventRunName
```


---

# system.secsgem.toDataset

**版本：** 8.1
**型別：** Scripting
**分類：** Secsgem

## 詳述

This function is used inPython Scripting. Converts a SECS message data structure, as returned by thesystem.secsgem.getResponsefunction, into a dataset and returns it. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.secsgem.toDataset(secsObject)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| secsObject | Any | A Python object, such as Sequence or a Dictionary, representing a SECS message to convert to a dataset. More information on how to format the Python object can be found on theSECS Definition Language (SDL) Filepage. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.secsgem.toDataset(secsObject)
```

### Example 3

```python
# Receive a SECS message.
object = system.secsgem.getResponse(transactionID, "myEquipment", 2)

# Turn the message into a dataset.
dataset = system.secsgem.toDataSet(object)

# Assuming this script was called from a component script, and a Table component was in the same container as the component that called this script, we could pass
# the dataset to the Data property.
event.source.parent.getComponent('Table').data = dataset
```


---

# system.secsgem.toTreeDataset

**版本：** 8.1
**型別：** Scripting
**分類：** Secsgem

## 詳述

This function is used inPython Scripting. Changes an existing dataset, as returned by thesystem.secsgem.toDataSetfunction, to make it usable for theTree Viewcomponent. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.secsgem.toTreeDataset(dataset)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| dataset | Dataset | A DataSet containing a SECS message. Note that this parameter cannot take a JSON message, so the object returned bysystem.secsgem.getResponsemust first be processed bysystem.secsgem.toDataSet. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.secsgem.toTreeDataset(dataset)
```

### Example 3

```python
# Assuming the variable named "message" contains a SECS message, we will first convert it to a Dataset.
dataset = system.secsgem.toDataset(message)

# The initial dataset generated by toDataSet will not work with the Tree View component, so we'll modify it...
dataset = system.secsgem.toTreeDataset(dataset)

# ...and now pass the dataset into the Tree View component's data property.
event.source.parent.getComponent('Tree View').data = dataset
```


---

# system.security.getRoles

**版本：** 8.1
**型別：** Scripting
**分類：** Security

## 詳述

This function is used inPython Scripting. Finds the roles that the currently logged in user has, returns them as a Python tuple of strings. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.security.getRoles()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.security.getRoles()
```

### Example 2

```python
# This would run on a button to prevent certain users from opening a window

if "Supervisor" in system.security.getRoles():
   system.nav.openWindow("ManagementOnly")
else:
   system.gui.errorBox("You don't have sufficient privileges to continue")
```

### Example 3

```python
# This would run on a button to prevent certain users from opening a window

if "Supervisor" in system.security.getRoles():
   system.nav.openWindow("ManagementOnly")
else:
   system.gui.errorBox("You don't have sufficient privileges to continue")
```


---

# system.security.getUserRoles

**版本：** 8.1
**型別：** Scripting
**分類：** Security

## 詳述

This function is used inPython Scripting. Fetches the roles for a user from the Gateway. This may not be the currently logged in user. Requires the password for that user. If the authentication profile name is omitted, then the current project's default authentication profile is used. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.security.getUserRoles(username, password, [authProfile], [timeout])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| username | String | The username to fetch roles for |
| password | String | The password for the user |
| authProfile | String | The name of the authentication profile to run against. Optional. Leaving this out will use the project's default profile. [optional] |
| timeout | Integer | Timeout for client-to-gateway communication. Default is 60,000ms.  [optional] |
| username | String | The username to fetch roles for. |
| password | String | The password for the user. |
| authProfile | String | The name of the authentication profile to run against. Leaving this out will use the project's default profile. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.security.getUserRoles(username, password, [authProfile], [timeout])
```


---

# system.security.getUsername

**版本：** 8.1
**型別：** Scripting
**分類：** Security

## 詳述

This function is used inPython Scripting. Returns the currently logged-in username. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.security.getUsername()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.security.getUsername()
```

### Example 2

```python
# This code would run on a startup script and does special logic based upon who was logging in
name = system.security.getUsername()
if name == 'Bob':
   system.nav.openWindow("BobsHomepage")
else:
   system.nav.openWindow("NormalHomepage")
```

### Example 3

```python
# This code would run on a startup script and does special logic based upon who was logging in
name = system.security.getUsername()
if name == 'Bob':
   system.nav.openWindow("BobsHomepage")
else:
   system.nav.openWindow("NormalHomepage")
```


---

# system.security.isScreenLocked

**版本：** 8.1
**型別：** Scripting
**分類：** Security

## 詳述

This function is used inPython Scripting. Returns whether or not the screen is currently locked. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.security.isScreenLocked()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.security.isScreenLocked()
```

### Example 2

```python
# This would run in a timer script to lock the screen after 15 seconds of inactivity, and then log the user out after 30 seconds of inactivity.

if system.util.getInactivitySeconds() > 15 and not system.security.isScreenLocked():
   system.security.lockScreen()
elif system.util.getInactivitySeconds() > 30:
   system.security.logout()
```

### Example 3

```python
# This would run in a timer script to lock the screen after 15 seconds of inactivity, and then log the user out after 30 seconds of inactivity.

if system.util.getInactivitySeconds() > 15 and not system.security.isScreenLocked():
   system.security.lockScreen()
elif system.util.getInactivitySeconds() > 30:
   system.security.logout()
```


---

# system.security.lockScreen

**版本：** 8.1
**型別：** Scripting
**分類：** Security

## 詳述

This function is used inPython Scripting. Used to put a running client in lock-screen mode. The screen can be unlocked by the user with the proper credentials, or by scripting via thesystem.security.unlockScreen()function. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.security.lockScreen([obscure])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| obscure | Boolean | If true(1), the locked screen will be opaque, otherwise it will be partially visible. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.security.lockScreen([obscure])
```

### Example 3

```python
# This would run in a timer script to lock the screen after 15 seconds of inactivity, and then log the user out after 30 seconds of inactivity.

if system.util.getInactivitySeconds() > 15 and not system.security.isScreenLocked():
   system.security.lockScreen()
elif system.util.getInactivitySeconds() > 30:
   system.security.logout()
```


---

# system.security.logout

**版本：** 8.1
**型別：** Scripting
**分類：** Security

## 詳述

This function is used inPython Scripting. Logs out of the Client for the current user and brings the Client to the login screen. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.security.logout()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.security.logout()
```

### Example 2

```python
# This would run in a timer script to log the user out after 30 seconds of inactivity.
if system.util.getInactivitySeconds() > 30:
   system.security.logout()
```

### Example 3

```python
# This would run in a timer script to log the user out after 30 seconds of inactivity.
if system.util.getInactivitySeconds() > 30:
   system.security.logout()
```


---

# system.security.switchUser

**版本：** 8.1
**型別：** Scripting
**分類：** Security

## 詳述

This function is used inPython Scripting. Attempts to switch the current user on the fly. If the given username and password fail, this function will return false. If it succeeds, then all currently opened windows are closed, the user is switched, and windows are then re-opened in the states that they were in. If an event object is passed to this function, the parent window of the event object will not be re-opened after a successful user switch. This is to support the common case of having a sw

## 語法

```python
system.security.switchUser(username, password, [event], [hideError])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| username | String | The username to try and switch to. |
| password | String | The password to authenticate with. |
| event | EventObject | If specified, the enclosing window for this event's component will be closed in the switch user process. Refer to the list ofEventobjects. [optional] |
| hideError | Boolean | If true (1), no error will be shown if the switch user function fails. Default is False. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.security.switchUser(username, password, [event], [hideError])
```


---

# system.security.unlockScreen

**版本：** 8.1
**型別：** Scripting
**分類：** Security

## 詳述

This function is used inPython Scripting. Unlocks the client, if it is currently in lock-screen mode. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.security.unlockScreen()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.security.unlockScreen()
```

### Example 2

```python
# This code would go in a global script to automatically unlock the screen on a specific computer

comp = system.net.getHostName()
if comp == 'Line 1':
   system.security.unlockScreen()
```

### Example 3

```python
# This code would go in a global script to automatically unlock the screen on a specific computer

comp = system.net.getHostName()
if comp == 'Line 1':
   system.security.unlockScreen()
```


---

# system.security.validateUser

**版本：** 8.1
**型別：** Scripting
**分類：** Security

## 詳述

This function is used inPython Scripting. Tests credentials (username and password) against an authentication profile. Returns a boolean based upon whether or not the authentication profile accepts the credentials. If the authentication profile name is omitted, then the current project's default authentication profile is used. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.security.validateUser(username, password, [authProfile], [timeout])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| username | String | The username to validate |
| password | String | The password for the user |
| authProfile | String | The name of the authentication profile to run against. Leaving this out will use the project's default profile. [optional] |
| timeout | Integer | Timeout for Client-to-Gateway communication. Default is 60,000ms. [optional] |
| username | String | The username to validate. |
| password | String | The password for the user. |
| authProfile | String | The name of the authentication profile to run against. Optional. Leaving this out will use the project's default profile. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.security.validateUser(username, password, [authProfile], [timeout])
```


---

# system.serial.closeSerialPort

**版本：** 8.1
**型別：** Scripting
**分類：** Serial

## 詳述

This function is used inPython Scripting. Closes a previously opened serial port. Returns without doing anything if the named serial port is not currently open. Will throw an exception if the port is open and cannot be closed. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.serial.closeSerialPort(port)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| port | String | The name of the serial port, e.g., "COM1" or "dev/ttyS0". |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.serial.closeSerialPort(port)
```

### Example 3

```python
# This example will close a port called "COM1".
system.serial.closeSerialPort("COM1")
```


---

# system.serial.configureSerialPort

**版本：** 8.1
**型別：** Scripting
**分類：** Serial

## 詳述

This function is used inPython Scripting. Configure a serial port for use in a later call. This only needs to be done once unless the configuration has changed after the initial call. All access to constants must be prefixed by " system.serial. ". This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.serial.configureSerialPort(port, [bitRate], [dataBits], [hardwareFlowControl], [parity], [stopBits])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| port | String | The name of the serial port, e.g., "COM1" or "/dev/ttyS0". This parameter is required. |
| bitRate | Integer | Configure the bit rate. Valid values are defined by the following constants [optional]:system.serial.BIT_RATE_110, system.serial.BIT_RATE_150,system.serial.BIT_RATE_300, system.serial.BIT_RATE_600,system.serial.BIT_RATE_1200, system.serial.BIT_RATE_2400,system.serial.BIT_RATE_4800, system.serial.BIT_RATE_9600,system.serial.BIT_RATE_19200, system.serial.BIT_RATE_38400,system.serial.BIT_RATE_57600, system.serial.BIT_RATE_115200,system.serial.BIT_RATE_230400, system.serial.BIT_RATE_460800,system.serial.BIT_RATE_921600 |
| dataBits | Integer | Configure the data bits. Valid values are defined by the following constants [optional]:system.serial.DATA_BITS_5, system.serial.DATA_BITS_6,system.serial.DATA_BITS_7, system.serial.DATA_BITS_8 |
| hardwareFlowControl | Boolean | Configure hardware flow control. On or off. [optional] |
| parity | Integer | Configure parity. Valid values are defined by the following constants [optional]:system.serial.PARITY_EVEN, system.serial.PARITY_ODD,system.serial.PARITY_MARK, system.serial.PARITY_SPACE, system.serial.PARITY_NONE |
| stopBits | Integer | Configure stop bits.Valid values are defined by the following constants [optional]:system.serial.STOP_BITS_1, system.serial.STOP_BITS_2 |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.serial.configureSerialPort(port, [bitRate], [dataBits], [hardwareFlowControl], [parity], [stopBits])
```


---

# system.serial.openSerialPort

**版本：** 8.1
**型別：** Scripting
**分類：** Serial

## 詳述

This function is used inPython Scripting. Opens a previously configured serial port for use. Will throw an exception if the serial port cannot be opened. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.serial.openSerialPort(port)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| port | String | The name of the serial port, e.g., "COM1" or "dev/ttyS0". |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.serial.openSerialPort(port)
```

### Example 3

```python
# This example will open a port called "COM1"
system.serial.openSerialPort("COM1")
```


---

# system.serial.port

**版本：** 8.1
**型別：** Scripting
**分類：** Serial

## 詳述

This function is used inPython Scripting. Returns acontext managerwrapping a serial port, allowing the rest of the system to interact with that port. This function effectively combines thesystem.serial.configureSerialPort,system.serial.openSerialPort, andsystem.serial.closeSerialPortfunctions into a single call. Intended to be used with thePython 'with' statement. The object aliased in the 'with' statement has special access to all of the othersystem.serialfunctions, allowing for reads and write

## 語法

```python
system.serial.port(port, [bitRate], [dataBits], [handshake], [hardwareFlowControl], [parity], [stopBits])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| port | String | The name of the serial port, e.g., "COM1" or "/dev/ttyS0". This parameter is required. |
| bitRate | Integer | Configure the bit rate. Valid values are defined by the following constants [optional]:system.serial.BIT_RATE_110, system.serial.BIT_RATE_150,system.serial.BIT_RATE_300, system.serial.BIT_RATE_600,system.serial.BIT_RATE_1200, system.serial.BIT_RATE_2400,system.serial.BIT_RATE_4800, system.serial.BIT_RATE_9600,system.serial.BIT_RATE_19200, system.serial.BIT_RATE_38400,system.serial.BIT_RATE_57600, system.serial.BIT_RATE_115200,system.serial.BIT_RATE_230400, system.serial.BIT_RATE_460800,system.serial.BIT_RATE_921600 |
| dataBits | Integer | Configure the data bits. Valid values are defined by the following constants [optional]:system.serial.DATA_BITS_5, system.serial.DATA_BITS_6,system.serial.DATA_BITS_7, system.serial.DATA_BITS_8 |
| hardwareFlowControl | Boolean | Configure hardware flow control. On or off. [optional] |
| parity | Integer | Configure parity. Valid values are defined by the following constants [optional]:system.serial.PARITY_EVEN, system.serial.PARITY_ODD,system.serial.PARITY_MARK, system.serial.PARITY_SPACE, system.serial.PARITY_NONE |
| stopBits | Integer | Configure stop bits.Valid values are defined by the following constants [optional]:system.serial.STOP_BITS_1, system.serial.STOP_BITS_2 |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.serial.port(port, [bitRate], [dataBits], [handshake], [hardwareFlowControl], [parity], [stopBits])
```


---

# system.serial.readBytes

**版本：** 8.1
**型別：** Scripting
**分類：** Serial

## 詳述

This function is used inPython Scripting. ReadnumberOfBytesbytes from a serial port. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.serial.readBytes(port, numberOfBytes [, timeout])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| port | String | The previously configured serial port to use. |
| numberOfBytes | int | The number of bytes to read. |
| timeout | int | Maximum amount of time, in milliseconds, to block before returning. Default is 5000. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
numberOfBytes
```

### Example 2

```python
system.serial.readBytes(port, numberOfBytes [, timeout])
```


---

# system.serial.readBytesAsString

**版本：** 8.1
**型別：** Scripting
**分類：** Serial

## 詳述

This function is used inPython Scripting. Read numberOfBytes bytes from a serial port and convert them to a String. If a specific encoding is needed to match the source of the data, usesystem.serial.readBytesand use the desired encoding to decode the byte array returned. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.serial.readBytesAsString(port, numberOfBytes, [timeout], [encoding])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| port | String | The previously configured serial port to use. |
| numberOfBytes | Integer | The number of bytes to read. |
| timeout | Integer | Maximum amount of time, in milliseconds, to block before returning. Default is 5000. [optional] |
| encoding | String | Encoding to use when constructing the string. Defaults to the platform's default character set. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.serial.readBytesAsString(port, numberOfBytes, [timeout], [encoding])
```

### Example 3

```python
numberOfBytes
```


---

# system.serial.readLine

**版本：** 8.1
**型別：** Scripting
**分類：** Serial

## 詳述

This function is used inPython Scripting. Attempts to read a line from a serial port. A "line" is considered to be terminated by either a line feed ('\n'), a carriage return ('\r'), or a carriage return followed immediately by a line feed. The function will wait until the timeout period for a terminator. If the timeout is reached before the line is properly terminated, then the buffer will be dumped, possibly resulting in data loss.

## 語法

```python
system.serial.readLine(port [, timeout] [, encoding])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| port | String | The previously configured serial port to use. |
| timeout | Integer | Maximum amount of time, in milliseconds, to block before returning. Default is 5000. [optional] |
| encoding | String | The String encoding to use. Default is UTF8. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.serial.readLine(port [, timeout] [, encoding])
```


---

# system.serial.readUntil

**版本：** 8.1
**型別：** Scripting
**分類：** Serial

## 詳述

This function is used inPython Scripting. Reads a byte at a time from a serial port until a delimiter character is encountered. The read will block for up to timeout milliseconds before returning. If the delimiter is not found before the timeout period, then the buffer will dump, potentially resulting in data loss.

## 語法

```python
system.serial.readUntil(port, delimiter, includeDelimiter, [timeout])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| port | String | The previously configured serial port to use. |
| delimiter | Char | The delimiter to read until. |
| includeDelimiter | Boolean | If true, the delimiter will be included in the return value. |
| timeout | Integer | Timeout in milliseconds. Default is 5000. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.serial.readUntil(port, delimiter, includeDelimiter, [timeout])
```


---

# system.serial.sendBreak

**版本：** 8.1
**型別：** Scripting
**分類：** Serial

## 詳述

This function is used inPython Scripting. Sends a break signal for approximately millis milliseconds. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.serial.sendBreak(port, millis)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| port | String | The name of the serial port, e.g., "COM1" or "dev/ttyS0". |
| millis | Integer | Approximate length of break signal, in milliseconds. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.serial.sendBreak(port, millis)
```


---

# system.serial.write

**版本：** 8.1
**型別：** Scripting
**分類：** Serial

## 詳述

This function is used inPython Scripting. Write a String to a serial port using the platforms default character encoding. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.serial.write(port, toWrite, [timeout], [encoding])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| port | String | The previously configured serial port to use. |
| toWrite | String | The String to write. |
| timeout | Integer | A timeout, in milliseconds. Writes exceeding this period will . Defaults to 5000 [optional] |
| encoding | String | Encoding to decode the string with, for example: UTF-8. Default is the platform default character set. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.serial.write(port, toWrite, [timeout], [encoding])
```


---

# system.serial.writeBytes

**版本：** 8.1
**型別：** Scripting
**分類：** Serial

## 詳述

This function is used inPython Scripting. Write a List[Byte] to a serial port. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.serial.writeBytes(port, toWrite)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| port | String | The previously configured serial port to use. |
| toWrite | List[Byte] | The List[Byte] to write. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.serial.writeBytes(port, toWrite)
```


---

# system.sfc.cancelChart

**版本：** 8.1
**型別：** Scripting
**分類：** Sfc

## 詳述

This function is used inPython Scripting. Cancels the execution of a running chart instance. Any running steps will be told to stop, and the SFC chart will enter Canceling state. Will throw a KeyError if the ID does not match any running chart instance. Permission Type: SFC Management

## 語法

```python
system.sfc.cancelChart(id)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| id | String | The ID of the chart instance to cancel. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.sfc.cancelChart(id)
```

### Example 3

```python
# The following attempts to stop an SFC but will alert the user if the id of the chart is not currently running.
id = 'Some long string value. It can be obtained using system.sfc.getRunningCharts()'
try:
    system.sfc.cancelChart(id)
except:
    system.gui.messageBox("Could not stop the SFC")
```


---

# system.sfc.getRunningCharts

**版本：** 8.1
**型別：** Scripting
**分類：** Sfc

## 詳述

This function is used inPython Scripting. Retrieves information about running charts. Can search all running charts, or be filtered charts at a specific path. This function will return charts that are in a Paused state. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.sfc.getRunningCharts([chartPath])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| chartPath | String | The path to a chart to filter on: i.e., "folder/chartName". If specified, only charts at the path will be included in the returned dataset. If omitted, the function will return data for all active charts. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.sfc.getRunningCharts([chartPath])
```

### Example 3

```python
# This example will check for all running charts, and return a formatted string detailing each chart instance.

# Check for all running charts. The path may be specified as a string to filter the results.
data = system.sfc.getRunningCharts()
# Create a string to append chart data to. The "\n" is a new line character.
chartData = "The following charts are running:\n"

# Iterate through each chart
for row in range(data.rowCount):

    # Extract the instanceId and chartPath values from the current row
    runningChartId = data.getValueAt(row, "instanceId")
    runningChartPath = data.getValueAt(row, "chartPath")

    # Append a string to chartData with the values extracted above
    chartData += "Id: %s, Path: %s\n" % (runningChartId, runningChartPath)

# Print the string of chart Id's and Paths
print chartData
```


---

# system.sfc.getVariables

**版本：** 8.1
**型別：** Scripting
**分類：** Sfc

## 詳述

This function is used inPython Scripting. Get the variables in a chart instance's scope. Commonly used to check the value of a Chart Parameter, or determine how long the chart has been running for. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.sfc.getVariables(instanceId)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| instanceId | String | The instance identifier of the chart. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.sfc.getVariables(instanceId)
```

### Example 3

```python
# This example will show the chart path and start time of a single chart in a messageBox.
# We can make use of the SFC Monitor component to give the users the ability to pick a single running chart

# Fetch the ID of a running chart. In this case, we used the Instance ID property on a SFC Monitor component
id = event.source.parent.getComponent('SFC Monitor').instanceId

# Retrieve the variables from the chart
chartVars = system.sfc.getVariables(id)

# Show the path and starttime of the chart in a messageBox
system.gui.messageBox("Chart Path: %s has been running since %s" % (chartVars["chartPath"], chartVars["startTime"]))
```


---

# system.sfc.pauseChart

**版本：** 8.1
**型別：** Scripting
**分類：** Sfc

## 詳述

This function is used inPython Scripting. Pauses a running chart instance. Any running steps will be told to pause, and the chart will enter Pausing state. Will throw a KeyError if the ID does not match any running chart instance. Permission Type: SFC Management

## 語法

```python
system.sfc.pauseChart(id)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| id | String | The ID of the chart instance to pause |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.sfc.pauseChart(id)
```

### Example 3

```python
# The following attempts to pause a SFC.
id = 'Some long string value. It can be obtained using system.sfc.getRunningCharts()'

system.sfc.cancelChart(id)
```


---

# system.sfc.redundantCheckpoint

**版本：** 8.1
**型別：** Scripting
**分類：** Sfc

## 詳述

This function is used inPython Scripting. Synchronizes chart and step variables of the specified chart instance across a redundant cluster, allowing the chart instance to continue where it left off if a redundant failover occurs. Check outredundancy syncfor more information. Permission Type: SFC Management

## 語法

```python
system.sfc.redundantCheckpoint(instanceId)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| instanceId | String | The instance identifier of the chart. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.sfc.redundantCheckpoint(instanceId)
```

### Example 3

```python
# This example will create a redundant checkpoint in case the primary Gateway in the redundant pair fails.
instanceId = "The ID of the chart you want to synchronize across the redundant pair"

system.sfc.redundantCheckpoint(instanceId)
```


---

# system.sfc.resumeChart

**版本：** 8.1
**型別：** Scripting
**分類：** Sfc

## 詳述

This function is used inPython Scripting. Resumes a chart that was paused. Steps which were previously paused will be resumed, and chart will enter Resuming state. Will throw a KeyError if the ID does not match any running chart instance. Permission Type: SFC Management

## 語法

```python
system.sfc.resumeChart(id)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| id | String | The ID of the chart instance to resume. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.sfc.resumeChart(id)
```

### Example 3

```python
# The following attempts to resume a paused SFC.
id = "The ID of the SFC you want to resume"

system.sfc.resumeChart(id)
```


---

# system.sfc.setVariable

**版本：** 8.1
**型別：** Scripting
**分類：** Sfc

## 詳述

This function is used inPython Scripting. Sets a variable inside a currently runningSFC chart. Permission Type: SFC Management

## 語法

```python
system.sfc.setVariable(instanceId, [stepId], variableName, variableValue)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| instanceId | String | The instance identifier of the chart. |
| stepId | String | The id for a step inside of a chart. If omitted the function will target a chart scoped variable. [optional] |
| variableName | String | The name of the variable to set. |
| variableValue | Object | The value for the variable to be set to. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.sfc.setVariable(instanceId, [stepId], variableName, variableValue)
```


---

# system.sfc.setVariables

**版本：** 8.1
**型別：** Scripting
**分類：** Sfc

## 詳述

This function is used inPython Scripting. Sets any number of variables inside a currently running chart. Permission Type: SFC Management

## 語法

```python
system.sfc.setVariables(instanceId, [stepId], variableMap)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| instanceId | String | The instance identifier of the chart. |
| stepId | String | The id for a step inside of a cart. If omitted the function will target a chart scoped variable. [optional] |
| variablesMap | Dictionary[String, Any] | A dictionary containing the name:valuepairs of the variables to set. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.sfc.setVariables(instanceId, [stepId], variableMap)
```


---

# system.sfc.startChart

**版本：** 8.1
**型別：** Scripting
**分類：** Sfc

## 詳述

This function is used inPython Scripting. Starts a new instance of a chart. The chart must be set to "Callable" execution mode. Permission Type: SFC Management

## 語法

```python
system.sfc.startChart(projectName, chartPath, parameters)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| projectName | String | The name of the project that the chart was created in. |
| chartPath | String | The path to the chart, for example "ChartFolder/ChartName". |
| parameters | Dictionary[String, Any] | A dictionary of arguments. Each key-value pair in the dictionary becomes a variable in the chart scope and will override any default. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.sfc.startChart(projectName, chartPath, parameters)
```

### Example 2

```python
projectName
```


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

# system.twilio.getAccounts

**版本：** 8.1
**型別：** Scripting
**分類：** Twilio

## 詳述

This function is used inPython Scripting. Returns a list of Twilio account names that have been configured in the Gateway. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.twilio.getAccounts()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.twilio.getAccounts()
```

### Example 2

```python
# Retrieves a list of Twilio accounts and then iterates through the resulting list.
# Call system.twilio.getAccounts() and store the returned list into a variable.
twilioAccounts = system.twilio.getAccounts()

# Iterate through the list of accounts.
for account in twilioAccounts:
    # Prints the account name to the console.
    print account
```

### Example 3

```python
# Retrieves a list of Twilio accounts and then iterates through the resulting list.
# Call system.twilio.getAccounts() and store the returned list into a variable.
twilioAccounts = system.twilio.getAccounts()

# Iterate through the list of accounts.
for account in twilioAccounts:
    # Prints the account name to the console.
    print account
```


---

# system.twilio.getAccountsDataset

**版本：** 8.1
**型別：** Scripting
**分類：** Twilio

## 詳述

This function is used inPython Scripting. Returns a list of Twilio account names that have been configured in the Gateway as a single-column Dataset. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.twilio.getAccountsDataset()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.twilio.getAccountsDataset()
```

### Example 2

```python
# Retrieves a list of Twilio accounts and then passes the data to a Table component's data property.

# Call system.twilio.getAccountsDataset() and store the returned list into a variable.
twilioAccounts = system.twilio.getAccountsDataset()


# Pass the dataset to a Table component. The Table is located in the same container as the
# component calling this script.
event.source.parent.getComponent('Table').data = twilioAccounts
```

### Example 3

```python
# Retrieves a list of Twilio accounts and then passes the data to a Table component's data property.

# Call system.twilio.getAccountsDataset() and store the returned list into a variable.
twilioAccounts = system.twilio.getAccountsDataset()


# Pass the dataset to a Table component. The Table is located in the same container as the
# component calling this script.
event.source.parent.getComponent('Table').data = twilioAccounts
```


---

# system.twilio.getPhoneNumbers

**版本：** 8.1
**型別：** Scripting
**分類：** Twilio

## 詳述

This function is used inPython Scripting. Returns a list of outgoing phone numbers for a Twilio account. Note that these numbers are supplied by Twilio, and are not defined on a user in Ignition. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.twilio.getPhoneNumbers(accountName)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| accountName | String | The Twilio account to retrieve phone numbers for |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.twilio.getPhoneNumbers(accountName)
```

### Example 2

```python
accountName
```

### Example 3

```python
# Retrieves a list of phone numbers associated with a Twilio account and then iterates through the resulting list.
# Checks against a Twilio profile configured on the Gateway by the name of "Twilio Account".

# Call system.twilio.getPhoneNumbers() and store the returned list into a variable.
twilioNumbers = system.twilio.getPhoneNumbers("Twilio Account")

# Iterate through the list of numbers.
for number in twilioNumbers:

    # Prints the numbers to the console
    print number
```


---

# system.twilio.getPhoneNumbersDataset

**版本：** 8.1
**型別：** Scripting
**分類：** Twilio

## 詳述

This function is used inPython Scripting. Returns a list of outgoing phone numbers for a Twilio account as a single-column Dataset. Note that these numbers are supplied by Twilio, and are not defined on a user in Ignition. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.twilio.getPhoneNumbersDataset(accountName)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| accountName | String | The Twilio account for which to retrieve phone numbers. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.twilio.getPhoneNumbersDataset(accountName)
```

### Example 2

```python
accountName
```

### Example 3

```python
# Retrieves a list of phone numbers associated with a Twilio account and then passes the resulting list to a Table component's Data property.
# Checks against a Twilio profile configured on the Gateway by the name of "Twilio Account".

# Call system.twilio.getPhoneNumbers() and store the returned list into a variable.
twilioNumbers = system.twilio.getPhoneNumbersDataset("Twilio Account")

# Pass the dataset to a Table component. The Table is located in the same container as the
# component calling this script.
event.source.parent.getComponent('Table').data = twilioNumbers
```


---

# system.twilio.sendSms

**版本：** 8.1
**型別：** Scripting
**分類：** Twilio

## 詳述

This function is used inPython Scripting. Sends an SMS message. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.twilio.sendSms(accountName, fromNumber, toNumber, message)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| accountName | String | The Twilio account to send the SMS from. |
| fromNumber | String | The outbound phone number belonging to the Twilio account to use. |
| toNumber | String | The phone number of the recipient. |
| message | String | The body of the SMS. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.twilio.sendSms(accountName, fromNumber, toNumber, message)
```

### Example 2

```python
accountName
```


---

# system.user.addCompositeSchedule

**版本：** 8.1
**型別：** Scripting
**分類：** User

## 詳述

This function is used inPython Scripting. Allows two schedules to be combined into a composite schedule. Permission Type: User Management

## 語法

```python
system.user.addCompositeSchedule(name, scheduleOne, scheduleTwo, [description])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| name | String | The name of the new composite schedule. |
| scheduleOne | String | The first schedule to combine. |
| scheduleTwo | String | The second schedule to combine. |
| description | String | Description of the new combined schedule. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.user.addCompositeSchedule(name, scheduleOne, scheduleTwo, [description])
```

### Example 3

```python
scheduleOne
```


---

# system.user.addHoliday

**版本：** 8.1
**型別：** Scripting
**分類：** User

## 詳述

This function is used inPython Scripting. Allows a holiday to be added. Permission Type: User Management

## 語法

```python
system.user.addHoliday(holiday)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| holiday | HolidayModel | The holiday to add, as aHolidayModelobject. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.user.addHoliday(holiday)
```


---

# system.user.addRole

**版本：** 8.1
**型別：** Scripting
**分類：** User

## 詳述

This function is used inPython Scripting. Adds a role to the specified user source. When altering the Gateway System User Source, theAllow User Adminsetting must be enabled. Permission Type: User Management

## 語法

```python
system.user.addRole(userSource, role)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| userSource | String | The user source to add a role to. Blank will use the default user source. |
| role | String | The role to add. Role must not be blank and must not already exist. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.user.addRole(userSource, role)
```


---

# system.user.addSchedule

**版本：** 8.1
**型別：** Scripting
**分類：** User

## 詳述

This function is used inPython Scripting. Adds a schedule. Permission Type: User Management

## 語法

```python
system.user.addSchedule(schedule)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| schedule | ScheduleModel | The schedule to add. Can be aBasicScheduleModelorCompositeScheduleModelobject (or any other class that extendsAbstractScheduleModel). |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.user.addSchedule(schedule)
```


---

# system.user.addUser

**版本：** 8.1
**型別：** Scripting
**分類：** User

## 詳述

This function is used inPython Scripting. Adds a new user to a user source. Used in combination withgetNewUserto create new user. Permission Type: User Management

## 語法

```python
system.user.addUser(userSource, user)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| userSource | String | The user source to add a user to. If set to an empty string, the function will attempt to use the project's default user source (if called from a project). |
| user | User | Theuserto add, as a User object. Refer also to the PyUser class. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.user.addUser(userSource, user)
```


---

# system.user.createScheduleAdjustment

**版本：** 8.1
**型別：** Scripting
**分類：** User

## 詳述

This function is used inPython Scripting. Creates a schedule adjustment. Permission Type: User Management

## 語法

```python
system.user.createScheduleAdjustment(startDate, endDate, isAvailable, note)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| startDate | Date | The starting date of the schedule adjustment. |
| endDate | Date | The ending date of the schedule adjustment. |
| isAvailable | Boolean | True if the user is available during this schedule adjustment. |
| note | String | A note about the schedule adjustment. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.user.createScheduleAdjustment(startDate, endDate, isAvailable, note)
```


---

# system.user.editHoliday

**版本：** 8.1
**型別：** Scripting
**分類：** User

## 詳述

This function is used inPython Scripting. Allows a holiday to be edited. Permission Type: User Management

## 語法

```python
system.user.editHoliday(holidayName, holiday)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| holidayName | String | The name of the holiday to edit. Name is case-sensitive. |
| holiday | HolidayModel | The edited holiday, as aHolidayModelobject. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.user.editHoliday(holidayName, holiday)
```

### Example 2

```python
holidayName
```


---

# system.user.editRole

**版本：** 8.1
**型別：** Scripting
**分類：** User

## 詳述

This function is used inPython Scripting. Renames a role in the specified user source. When altering the Gateway System User Source, theAllow User Adminsetting must be enabled. Permission Type: User Management

## 語法

```python
system.user.editRole(userSource, oldName, newName)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| userSource | String | The user source in which the role is found. Blank will use the default user source. |
| oldName | String | The role to edit. Role must not be blank and must exist. |
| newName | String | The new name for the role. Must not be blank. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.user.editRole(userSource, oldName, newName)
```


---

# system.user.editSchedule

**版本：** 8.1
**型別：** Scripting
**分類：** User

## 詳述

This function is used inPython Scripting. Allows a schedule to be edited. Permission Type: User Management

## 語法

```python
system.user.editSchedule(scheduleName, schedule)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| scheduleName | String | The name of the schedule to edit. Name is case-sensitive. |
| schedule | ScheduleModel | The schedule to add. Can be aBasicScheduleModelorCompositeScheduleModelobject (or any other class that extendsAbstractScheduleModel). |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.user.editSchedule(scheduleName, schedule)
```

### Example 2

```python
scheduleName
```


---

# system.user.editUser

**版本：** 8.1
**型別：** Scripting
**分類：** User

## 詳述

This function is used inPython Scripting. Alters a specific user in a user source, replacing the previous data with the new data passed in. Permission Type: User Management

## 語法

```python
system.user.editUser(userSource, user)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| userSource | String | The user source in which the user is found. Blank will use the default user source. |
| user | User | The user to update, as aUserobject. Refer also to thePyUserclass. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.user.editUser(userSource, user)
```


---

# system.user.getHoliday

**版本：** 8.1
**型別：** Scripting
**分類：** User

## 詳述

This function is used inPython Scripting. Returns a specific holiday. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.user.getHoliday(holidayName)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| holidayName | String | The name of the holiday to return. Case-sensitive |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.user.getHoliday(holidayName)
```

### Example 2

```python
holidayName
```

### Example 3

```python
# This example will get a holiday and print info about it.
holidayName = "Labor Day"
holiday = system.user.getHoliday(holidayName)
if holiday == None:
    print holidayName, "not found"
else:
    print holiday.getName(), holiday.getDate(), holiday.isRepeatAnually()

"""The example above outputs the following:
Labor Day 2015-09-07 00:00:00.0 False
"""
```


---

# system.user.getHolidayNames

**版本：** 8.1
**型別：** Scripting
**分類：** User

## 詳述

This function is used inPython Scripting. Returns a collection of Strings of all holiday names. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.user.getHolidayNames()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.user.getHolidayNames()
```

### Example 2

```python
# This example prints the name of every holiday.

holidayNames = system.user.getHolidayNames()
for holidayName in holidayNames:
    print holidayName
```

### Example 3

```python
# This example prints the name of every holiday.

holidayNames = system.user.getHolidayNames()
for holidayName in holidayNames:
    print holidayName
```


---

# system.user.getHolidays

**版本：** 8.1
**型別：** Scripting
**分類：** User

## 詳述

This function is used inPython Scripting. Returns a sequence of all of the holidays available. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.user.getHolidays()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.user.getHolidays()
```

### Example 2

```python
# This example prints information about every holiday.
holidays = system.user.getHolidays()
if len(holidays) == 0:
    print "No holidays defined"
for holiday in holidays:
    print holiday.getName(), holiday.getDate(), holiday.isRepeatAnnually()
```

### Example 3

```python
# This example prints information about every holiday.
holidays = system.user.getHolidays()
if len(holidays) == 0:
    print "No holidays defined"
for holiday in holidays:
    print holiday.getName(), holiday.getDate(), holiday.isRepeatAnnually()
```


---

# system.user.getNewUser

**版本：** 8.1
**型別：** Scripting
**分類：** User

## 詳述

This function is used inPython Scripting. Creates a new user object. The user will not be added to the user source untiladdUseris called. Permission Type: User Management

## 語法

```python
system.user.getNewUser(userSource, username)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| userSource | String | The name of the user source in which to create a user. |
| username | String | The username for the new user. Does not check if the username already exists or is valid. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.user.getNewUser(userSource, username)
```


---

# system.user.getRoles

**版本：** 8.1
**型別：** Scripting
**分類：** User

## 詳述

This function is used inPython Scripting. Returns a sequence of strings representing all of the roles configured in a specific user source. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.user.getRoles(userSource)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| userSource | String | The user source to fetch the roles for. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.user.getRoles(userSource)
```

### Example 3

```python
# This example will print a list of all user roles in the default user source:

roles = system.user.getRoles("")
for role in roles:
    print role
```


---

# system.user.getSchedule

**版本：** 8.1
**型別：** Scripting
**分類：** User

## 詳述

This function is used inPython Scripting. Returns a specific schedule. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.user.getSchedule(scheduleName)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| scheduleName | String | The name of the schedule to return. Case-sensitive |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.user.getSchedule(scheduleName)
```

### Example 2

```python
scheduleName
```

### Example 3

```python
# This example will get a schedule and print info about it.

# This function handles recursive printing of the different schedule types. Modules can register more types than listed here.
def printScheduleInfo(aSchedule):
    if aSchedule.getType() == "basic schedule":
        print "Basic schedule type: ",aSchedule.getName(), aSchedule.getDescription(), aSchedule.isAllDays(), aSchedule.isObserveHolidays()
    elif aSchedule.getType() == "composite schedule":
        compositePieces = aSchedule.getModels()
        print "Composite schedule type:",aSchedule.getName(), aSchedule.getDescription(), " which is made up of..."
        for piece in compositePieces:
            printScheduleInfo(piece)
    else:
        print "Other schedule type: ", aSchedule.getName(), aSchedule.getDescription(), aSchedule.getType(), aSchedule.isObserveHolidays()

# The main function.
scheduleName = "MySchedule"
schedule = system.user.getSchedule(scheduleName)
if schedule == None:
    print "Schedule", scheduleName, "was not found"
else:
    printScheduleInfo(schedule)

"""The example above outputs the following:
Basic schedule type:  MySchedule A description False True"""
```


---

# system.user.getScheduleNames

**版本：** 8.1
**型別：** Scripting
**分類：** User

## 詳述

This function is used inPython Scripting. Returns a sequence of strings representing the names of all of the schedules available. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.user.getScheduleNames()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.user.getScheduleNames()
```

### Example 2

```python
# This example will print a list of all available schedules.

schedules = system.user.getScheduleNames()
for schedule in schedules:
    print schedule
```

### Example 3

```python
# This example will print a list of all available schedules.

schedules = system.user.getScheduleNames()
for schedule in schedules:
    print schedule
```


---

# system.user.getScheduledUsers

**版本：** 8.1
**型別：** Scripting
**分類：** User

## 詳述

This function is used inPython Scripting. Returns a list of users that are scheduled. If no users are scheduled, it will return an empty list. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.user.getScheduledUsers(userSource, [date])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| userSource | String | The name of the user source to check for scheduled users. |
| date | Date | The date to check schedules for. May be a Java Date or Unix Time in ms. If omitted, the current date and time will be used. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.user.getScheduledUsers(userSource, [date])
```


---

# system.user.getSchedules

**版本：** 8.1
**型別：** Scripting
**分類：** User

## 詳述

This function is used inPython Scripting. Returns a sequence of all available schedule models, which can be used to return configuration information on the schedule, such as time for each day of the week. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.user.getSchedules()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.user.getSchedules()
```

### Example 2

```python
# This example will print a list of all available ScheduleModels.

# This function handles recursive printing of the different schedule models. Modules can register more types than listed here.
def printScheduleInfo(aSchedule):
    if aSchedule.getType() == "basic schedule":
        print "Basic schedule type: ",aSchedule.getName(), aSchedule.getDescription(), aSchedule.isAllDays(), aSchedule.getAllDayTime()
    elif aSchedule.getType() == "composite schedule":
        compositePieces = aSchedule.getModels()
        print "Composite schedule type:",aSchedule.getName(), aSchedule.getDescription(), " which is made up of..."
        for piece in compositePieces:
            printScheduleInfo(piece)
    else:
        print "Other schedule type: ", aSchedule.getName(), aSchedule.getDescription(), aSchedule.getType(), aSchedule.isObserveHolidays()


# The main function.
schedules = system.user.getSchedules()
for schedule in schedules:
    printScheduleInfo(schedule)
```

### Example 3

```python
# This example will print a list of all available ScheduleModels.

# This function handles recursive printing of the different schedule models. Modules can register more types than listed here.
def printScheduleInfo(aSchedule):
    if aSchedule.getType() == "basic schedule":
        print "Basic schedule type: ",aSchedule.getName(), aSchedule.getDescription(), aSchedule.isAllDays(), aSchedule.getAllDayTime()
    elif aSchedule.getType() == "composite schedule":
        compositePieces = aSchedule.getModels()
        print "Composite schedule type:",aSchedule.getName(), aSchedule.getDescription(), " which is made up of..."
        for piece in compositePieces:
            printScheduleInfo(piece)
    else:
        print "Other schedule type: ", aSchedule.getName(), aSchedule.getDescription(), aSchedule.getType(), aSchedule.isObserveHolidays()


# The main function.
schedules = system.user.getSchedules()
for schedule in schedules:
    printScheduleInfo(schedule)
```


---

# system.user.getUser

**版本：** 8.1
**型別：** Scripting
**分類：** User

## 詳述

This function is used inPython Scripting. Looks up a specific user in a user source, by username. The full User object is returned except for the user's password. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.user.getUser(userSource, username)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| userSource | String | The name of the user source to search for the user in. Can be a blank string to use the Vision Client's default user source. |
| username | String | The username of the user to search for. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.user.getUser(userSource, username)
```


---

# system.user.getUserSources

**版本：** 8.1
**型別：** Scripting
**分類：** User

## 詳述

This function is used inPython Scripting. Returns a sequence of objects representing all of the user source profiles configured in the Gateway. Each object has a "name" property, a "description" property, and a "type" property. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.user.getUserSources()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.user.getUserSources()
```

### Example 2

```python
uList = system.user.getUserSources()
print len(uList)
```

### Example 3

```python
uList = system.user.getUserSources()
print len(uList)
```


---

# system.user.getUsers

**版本：** 8.1
**型別：** Scripting
**分類：** User

## 詳述

This function is used inPython Scripting. Retrieves the list of users in a specific user source. The "User" objects that are returned contain all of the information about that user, except for the user's password. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.user.getUsers(userSource)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| userSource | String | The name of the user source to find the users in. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.user.getUsers(userSource)
```

### Example 3

```python
# This example will print the first and last name of all users, using the default datasource:

users = system.user.getUsers("")
for user in users:
    print user.get(user.FirstName) + " " + user.get(user.LastName)
```


---

# system.user.isUserScheduled

**版本：** 8.1
**型別：** Scripting
**分類：** User

## 詳述

This function is used inPython Scripting. Will check if a specified User is scheduled currently or on a specified date/time. This scripting function has noClient Permissionrestrictions.

## 語法

```python
system.user.isUserScheduled(user, [date])
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| user | User | The user object to check the schedule for. |
| date | Date / Integer | The date to check schedules for. May be a Java Date or Unix Time in ms. If omitted, the current date and time will be used. [optional] |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.user.isUserScheduled(user, [date])
```


---

# system.user.removeHoliday

**版本：** 8.1
**型別：** Scripting
**分類：** User

## 詳述

This function is used inPython Scripting. Allows a holiday to be deleted. Permission Type: User Management

## 語法

```python
system.user.removeHoliday(holidayName)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| holidayName | String | The name of the holiday to delete. Case-sensitive. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.user.removeHoliday(holidayName)
```

### Example 2

```python
holidayName
```


---

# system.user.removeRole

**版本：** 8.1
**型別：** Scripting
**分類：** User

## 詳述

This function is used inPython Scripting. Removes a role from the specified user source. When altering the Gateway System User Source, theAllow User Adminsetting must be enabled. Permission Type: User Management

## 語法

```python
system.user.removeRole(userSource, role)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| userSource | String | The user source in which the role is found. Blank will use the default user source. |
| role | String | The role to remove. The role must exist. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.user.removeRole(userSource, role)
```


---

# system.user.removeSchedule

**版本：** 8.1
**型別：** Scripting
**分類：** User

## 詳述

This function is used inPython Scripting. Allows a schedule to be deleted. Note that schedules which are used in Composite Schedules can not be deleted until they are removed from the Composite Schedule. Permission Type: User Management

## 語法

```python
system.user.removeSchedule(scheduleName)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| scheduleName | String | The name of the schedule to delete. Case-sensitive. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.user.removeSchedule(scheduleName)
```

### Example 2

```python
scheduleName
```


---

# system.user.removeUser

**版本：** 8.1
**型別：** Scripting
**分類：** User

## 詳述

This function is used inPython Scripting. Removes a specific user from the a user source based on username. When altering the Gateway System User Source, theAllow User Adminsetting must be enabled. Permission Type: User Management

## 語法

```python
system.user.removeUser(userSource, username)
```

## 參數

| 型別 | 參數名 | 說明 |
| --- | --- | --- |
| userSource | String | The user source in which the user is found. Blank will use the default user source. |
| username | String | The username of the user to remove. |

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.user.removeUser(userSource, username)
```


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

# system.vision.getKeyboardLayouts

**版本：** 8.1
**型別：** Scripting
**分類：** Vision

## 詳述

This function is used inPython Scripting. Returns a list of keyboard layouts available on this system.

## 語法

```python
system.vision.getKeyboardLayouts()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.vision.getKeyboardLayouts()
```

### Example 2

```python
# list all keyboard layouts that support English
for layout in system.vision.getKeyboardLayouts():
    if "en" in layout.supportedLanguages:
        print layout.name
```

### Example 3

```python
# list all keyboard layouts that support English
for layout in system.vision.getKeyboardLayouts():
    if "en" in layout.supportedLanguages:
        print layout.name
```


---

# system.vision.updateProject

**版本：** 8.1
**型別：** Scripting
**分類：** Vision

## 詳述

This function is used inPython Scripting. Updates the Vision Client project with saved changes. This function is intended to be used in conjunction with the "None" option of Vision Project update modes in the Project Properties, and the Vision Client System TagProjectUpdateAvailable.

## 語法

```python
system.vision.updateProject()
```

## 回傳值

**型別：** Object

## 範例

### Example 1

```python
system.vision.updateProject()
```

### Example 2

```python
# This script is intended to go on a Button component.
# Upon clicking, the Vision Client project will update with the latest changes.
system.vision.updateProject()
```

### Example 3

```python
# This script is intended to go on a Button component.
# Upon clicking, the Vision Client project will update with the latest changes.
system.vision.updateProject()
```


---
