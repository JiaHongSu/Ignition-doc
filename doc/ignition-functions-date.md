# Ignition 8.1 - system.date 函數文檔

﻿# Ignition 8.1 - 函數文檔（PATTERN 規範）

> 根據 FUNCTION_PATTERN 爬蟲生成
> 生成時間: 2026年04月19日 00:56:44
> 總計函式數: 434

## 📑 目錄

---

1. [system.date.*Between](#systemdate*between) - This function is used inPython Scripting. This function is a set of functions that include: Order matters when passing in the two dates required by this function. system.date.*Between will subtract the first date from the second date, meaning if date 2 is further in time than date 1, then a positive amount of time has passed. If date 2 is backwards in time from date 1, then a negative amount of time has passed.
2. [system.date.add*](#systemdateadd*) - This function is used inPython Scripting. This function is a set of functions that include: This scripting function has noClient Permissionrestrictions.
3. [system.date.format](#systemdateformat) - This function is used inPython Scripting. Returns the given date as a string and formatted according to a pattern. The pattern is a format that is full of various placeholders that display different parts of the date. These are case-sensitive. These placeholders can be repeated for a different effect. For example, M will give you 1-12, MM will give you 01-12, MMM will give you Jan-Dec, MMMM will give you January-December. This scripting function has noClient Permissionrestrictions.
4. [system.date.fromMillis](#systemdatefrommillis) - This function is used inPython Scripting. Creates a date object given a millisecond value. This scripting function has noClient Permissionrestrictions.
5. [system.date.get*](#systemdateget*) - This function is used inPython Scripting. This function is a set of functions that include: This scripting function has noClient Permissionrestrictions.
6. [system.date.getDate](#systemdategetdate) - This function is used inPython Scripting. Creates a new Date object given a year, month and a day. The time will be set to midnight of that day. This scripting function has noClient Permissionrestrictions.
7. [system.date.getTimezone](#systemdategettimezone) - This function is used inPython Scripting. Returns the ID of the current timezone. If your Client and Gateway are in different time zones, the returned value will be dependent on where this script is run. IE: in a button on a client will return the Client time zone. On a Gateway script (including Perspective scripts), the function will return the Gateway time zone.
8. [system.date.getTimezoneOffset](#systemdategettimezoneoffset) - This function is used inPython Scripting. Returns the current timezone's offset versus UTC for a given instant, taking Daylight Savings Time into account. This scripting function has noClient Permissionrestrictions.
9. [system.date.getTimezoneRawOffset](#systemdategettimezonerawoffset) - This function is used inPython Scripting. Returns the current timezone offset versus UTC, not taking daylight savings into account. This scripting function has noClient Permissionrestrictions.
10. [system.date.isAfter](#systemdateisafter) - This function is used inPython Scripting. Compares two dates to see if date_1 is after date_2. This scripting function has noClient Permissionrestrictions.
11. [system.date.isBefore](#systemdateisbefore) - This function is used inPython Scripting. Compares two dates to see if date_1 is before date_2. This scripting function has noClient Permissionrestrictions.
12. [system.date.isBetween](#systemdateisbetween) - This function is used inPython Scripting. Compares two dates to see if a target date is between two other dates; checks to see if the target date is between the other two dates. This scripting function has noClient Permissionrestrictions.
13. [system.date.isDaylightTime](#systemdateisdaylighttime) - This function is used inPython Scripting. Checks to see if the current timezone is using daylight savings time during the date specified. This scripting function has noClient Permissionrestrictions.
14. [system.date.midnight](#systemdatemidnight) - This function is used inPython Scripting. Returns a copy of a date with the hour, minute, second, and millisecond fields set to zero. This scripting function has noClient Permissionrestrictions.
15. [system.date.now](#systemdatenow) - This function is used inPython Scripting. Returns a java.util.Date object that represents the current time according to the local system clock. This scripting function has noClient Permissionrestrictions.
16. [system.date.parse](#systemdateparse) - This function is used inPython Scripting. Attempts to parse a string and create a Date. Causes ParseException if the date dateString parameter is in an unrecognized format. This scripting function has noClient Permissionrestrictions.
17. [system.date.setTime](#systemdatesettime) - This function is used inPython Scripting. Takes in a date, and returns a copy of it with the time fields set as specified. This scripting function has noClient Permissionrestrictions.
18. [system.date.toMillis](#systemdatetomillis) - This function is used inPython Scripting. Converts a Date object to its millisecond value elapsed since January 1, 1970, 00:00:00 UTC (GMT) This scripting function has noClient Permissionrestrictions.

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

