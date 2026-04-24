# Ignition 8.1 - system.twilio 函數文檔


## 📑 目錄

---

1. [system.twilio.getAccounts](#systemtwiliogetaccounts) - This function is used inPython Scripting. Returns a list of Twilio account names that have been configured in the Gateway. This scripting function has noClient Permissionrestrictions.
2. [system.twilio.getAccountsDataset](#systemtwiliogetaccountsdataset) - This function is used inPython Scripting. Returns a list of Twilio account names that have been configured in the Gateway as a single-column Dataset. This scripting function has noClient Permissionrestrictions.
3. [system.twilio.getPhoneNumbers](#systemtwiliogetphonenumbers) - This function is used inPython Scripting. Returns a list of outgoing phone numbers for a Twilio account. Note that these numbers are supplied by Twilio, and are not defined on a user in Ignition. This scripting function has noClient Permissionrestrictions.
4. [system.twilio.getPhoneNumbersDataset](#systemtwiliogetphonenumbersdataset) - This function is used inPython Scripting. Returns a list of outgoing phone numbers for a Twilio account as a single-column Dataset. Note that these numbers are supplied by Twilio, and are not defined on a user in Ignition. This scripting function has noClient Permissionrestrictions.
5. [system.twilio.sendSms](#systemtwiliosendsms) - This function is used inPython Scripting. Sends an SMS message. This scripting function has noClient Permissionrestrictions.

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

