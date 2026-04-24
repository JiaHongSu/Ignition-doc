# Ignition 8.1 - system.roster 函數文檔


## 📑 目錄

---

1. [system.roster.addUsers](#systemrosteraddusers) - This function is used inPython Scripting. Adds a list of users to an existing roster. Users are always appended to the end of the roster. system.roster.addUsers(rosterName, [users])
2. [system.roster.createRoster](#systemrostercreateroster) - This function is used inPython Scripting. Creates a roster with the given name and description, if it does not already exist. This function was designed to run in the Gateway and in Perspective sessions. If creating rosters from Vision clients, usesystem.alarm.createRosterinstead
3. [system.roster.deleteRoster](#systemrosterdeleteroster) - This function is used inPython Scripting. Deletes a roster with the given name.
4. [system.roster.getRoster](#systemrostergetroster) - This function is used inPython Scripting. Returns the roster corresponding to the given name. You can call getUsers() to access a list of User objects in the RosterModel.
5. [system.roster.getRosterNames](#systemrostergetrosternames) - This function is used inPython Scripting. Returns a list of roster names.
6. [system.roster.getRosters](#systemrostergetrosters) - This function is used inPython Scripting. Returns a dictionary of rosters, where the key is the name of the roster, and the value is an array list of string user names. This function was designed to run in the Gateway and in Perspective sessions. If creating rosters from Vision clients, usesystem.alarm.getRostersinstead.
7. [system.roster.removeUsers](#systemrosterremoveusers) - This function is used inPython Scripting. Removes one or more users from an existing roster. system.roster.removeUsers(rosterName, users)

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

