# Ignition 8.1 - system.user 函數文檔


## 📑 目錄

---

1. [system.user.addCompositeSchedule](#systemuseraddcompositeschedule) - This function is used inPython Scripting. Allows two schedules to be combined into a composite schedule. Permission Type: User Management
2. [system.user.addHoliday](#systemuseraddholiday) - This function is used inPython Scripting. Allows a holiday to be added. Permission Type: User Management
3. [system.user.addRole](#systemuseraddrole) - This function is used inPython Scripting. Adds a role to the specified user source. When altering the Gateway System User Source, theAllow User Adminsetting must be enabled. Permission Type: User Management
4. [system.user.addSchedule](#systemuseraddschedule) - This function is used inPython Scripting. Adds a schedule. Permission Type: User Management
5. [system.user.addUser](#systemuseradduser) - This function is used inPython Scripting. Adds a new user to a user source. Used in combination withgetNewUserto create new user. Permission Type: User Management
6. [system.user.createScheduleAdjustment](#systemusercreatescheduleadjustment) - This function is used inPython Scripting. Creates a schedule adjustment. Permission Type: User Management
7. [system.user.editHoliday](#systemusereditholiday) - This function is used inPython Scripting. Allows a holiday to be edited. Permission Type: User Management
8. [system.user.editRole](#systemusereditrole) - This function is used inPython Scripting. Renames a role in the specified user source. When altering the Gateway System User Source, theAllow User Adminsetting must be enabled. Permission Type: User Management
9. [system.user.editSchedule](#systemusereditschedule) - This function is used inPython Scripting. Allows a schedule to be edited. Permission Type: User Management
10. [system.user.editUser](#systemuseredituser) - This function is used inPython Scripting. Alters a specific user in a user source, replacing the previous data with the new data passed in. Permission Type: User Management
11. [system.user.getHoliday](#systemusergetholiday) - This function is used inPython Scripting. Returns a specific holiday. This scripting function has noClient Permissionrestrictions.
12. [system.user.getHolidayNames](#systemusergetholidaynames) - This function is used inPython Scripting. Returns a collection of Strings of all holiday names. This scripting function has noClient Permissionrestrictions.
13. [system.user.getHolidays](#systemusergetholidays) - This function is used inPython Scripting. Returns a sequence of all of the holidays available. This scripting function has noClient Permissionrestrictions.
14. [system.user.getNewUser](#systemusergetnewuser) - This function is used inPython Scripting. Creates a new user object. The user will not be added to the user source untiladdUseris called. Permission Type: User Management
15. [system.user.getRoles](#systemusergetroles) - This function is used inPython Scripting. Returns a sequence of strings representing all of the roles configured in a specific user source. This scripting function has noClient Permissionrestrictions.
16. [system.user.getSchedule](#systemusergetschedule) - This function is used inPython Scripting. Returns a specific schedule. This scripting function has noClient Permissionrestrictions.
17. [system.user.getScheduleNames](#systemusergetschedulenames) - This function is used inPython Scripting. Returns a sequence of strings representing the names of all of the schedules available. This scripting function has noClient Permissionrestrictions.
18. [system.user.getScheduledUsers](#systemusergetscheduledusers) - This function is used inPython Scripting. Returns a list of users that are scheduled. If no users are scheduled, it will return an empty list. This scripting function has noClient Permissionrestrictions.
19. [system.user.getSchedules](#systemusergetschedules) - This function is used inPython Scripting. Returns a sequence of all available schedule models, which can be used to return configuration information on the schedule, such as time for each day of the week. This scripting function has noClient Permissionrestrictions.
20. [system.user.getUser](#systemusergetuser) - This function is used inPython Scripting. Looks up a specific user in a user source, by username. The full User object is returned except for the user's password. This scripting function has noClient Permissionrestrictions.
21. [system.user.getUserSources](#systemusergetusersources) - This function is used inPython Scripting. Returns a sequence of objects representing all of the user source profiles configured in the Gateway. Each object has a "name" property, a "description" property, and a "type" property. This scripting function has noClient Permissionrestrictions.
22. [system.user.getUsers](#systemusergetusers) - This function is used inPython Scripting. Retrieves the list of users in a specific user source. The "User" objects that are returned contain all of the information about that user, except for the user's password. This scripting function has noClient Permissionrestrictions.
23. [system.user.isUserScheduled](#systemuserisuserscheduled) - This function is used inPython Scripting. Will check if a specified User is scheduled currently or on a specified date/time. This scripting function has noClient Permissionrestrictions.
24. [system.user.removeHoliday](#systemuserremoveholiday) - This function is used inPython Scripting. Allows a holiday to be deleted. Permission Type: User Management
25. [system.user.removeRole](#systemuserremoverole) - This function is used inPython Scripting. Removes a role from the specified user source. When altering the Gateway System User Source, theAllow User Adminsetting must be enabled. Permission Type: User Management
26. [system.user.removeSchedule](#systemuserremoveschedule) - This function is used inPython Scripting. Allows a schedule to be deleted. Note that schedules which are used in Composite Schedules can not be deleted until they are removed from the Composite Schedule. Permission Type: User Management
27. [system.user.removeUser](#systemuserremoveuser) - This function is used inPython Scripting. Removes a specific user from the a user source based on username. When altering the Gateway System User Source, theAllow User Adminsetting must be enabled. Permission Type: User Management

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

