# Ignition 8.1 - system.math 函數文檔

﻿# Ignition 8.1 - 函數文檔（PATTERN 規範）

> 根據 FUNCTION_PATTERN 爬蟲生成
> 生成時間: 2026年04月19日 00:56:44
> 總計函式數: 434

## 📑 目錄

---

1. [system.math.geometricMean](#systemmathgeometricmean) - This function is used inPython Scripting. Calculates the geometric mean. Geometric mean is a type of average which indicates a value in a set of numbers by using the product of values in the set and then taking the nth root, wherenis the number of values in the set. This is different than an arithmetic mean, which calculates an average based off the sum of the numbers, and divides it by n number of values. Geometric means can only be positive numbers. Returns NaN (Not a Number) if passed an empt
2. [system.math.kurtosis](#systemmathkurtosis) - This function is used inPython Scripting. Calculates the kurtosis of a sequence of values. Kurtosis measures if data is peaked or flat relative to normal distribution. A set of data with high kurtosis will have distinct peaks near the mean, while a set of data with low kurtosis will have a flat top near the mean. Uniform distribution is typically a flat line. Returns NaN (Not a Number) if passed an empty sequence measure of whether the data are heavy-tailed or light-tailed of a given distributio
3. [system.math.max](#systemmathmax) - This function is used inPython Scripting. Given a sequence of values, returns the greatest value in the sequence, also known as the "max" value. Returns NaN (Not a Number) if passed an empty sequence.
4. [system.math.mean](#systemmathmean) - This function is used inPython Scripting. Given a sequence of values, calculates the arithmetic mean (average). Returns NaN (Not a Number) if passed an empty sequence.
5. [system.math.meanDifference](#systemmathmeandifference) - This function is used inPython Scripting. Given two sequences of values, calculates the mean of the signed difference between both sequences. In other words, returns the absolute difference between the mean values of two different sets of data. Throws a DimensionMismatchException if the two sequences have different lengths.
6. [system.math.median](#systemmathmedian) - This function is used inPython Scripting. Takes a sequence of values, and returns the median. The median represents the middle value in a set of data. Returns NaN (Not a Number) if passed an empty sequence.
7. [system.math.min](#systemmathmin) - This function is used inPython Scripting. Given a sequence of numerical values, returns the minimum value, also known as the "min" value. Returns NaN (Not a Number) if passed an empty sequence.
8. [system.math.mode](#systemmathmode) - This function is used inPython Scripting. Given a sequence of values, returns the 'mode', or most frequent values. Returns an empty list if the sequence was empty or None.
9. [system.math.normalize](#systemmathnormalize) - This function is used inPython Scripting. Given a sequence of values, normalizes the values. Normalizing data refers to adjusting values measured on different scales and brings them into alignment to allow the comparison of corresponding normalized values. This creates uniformity of values by eliminating the different units of measurement, and to more easily compare data from different places. Returns an empty list if the sequence was empty or None.
10. [system.math.percentile](#systemmathpercentile) - This function is used inPython Scripting. Given a sequence of numerical values, estimates the percentile of input. The percentile is a value on a scale that represents a percentage position in a list of data that can be equal to or below that value: i.e., the 25th percentile is a value below which 25% of observable data points may be found.
11. [system.math.populationVariance](#systemmathpopulationvariance) - This function is used inPython Scripting. Given a sequence of values, returns the population variance. Population variance calculates how values in a dataset are spread out from their average value. Returns NaN (Not a Number) if passed an empty sequence.
12. [system.math.product](#systemmathproduct) - This function is used inPython Scripting. Given a sequence of values, calculates the product of the sequence: the result of multiplying of all values in the sequence together. Returns NaN (Not a Number) if passed an empty sequence.
13. [system.math.skewness](#systemmathskewness) - This function is used inPython Scripting. Given a sequence of values, calculates the skewness (third central moment). Skewness is a measure of the degree of asymmetry of a distribution of the mean. If skewed to the left, the distribution has a long tail in the negative direction. If skewed to the right, the tail will be skewed in the positive direction. Skewness values greater than 1 or less than -1 indicate a highly skewed distribution, while skewness values between 0.5 and 1 or -0.5 and -1 ind
14. [system.math.standardDeviation](#systemmathstandarddeviation) - This function is used inPython Scripting. Given a sequence of numerical values, calculates the simple standard deviation. Standard deviation is a calculated number for how close, or how far the values of that dataset are in relation to the mean. Returns NaN (Not a Number) if passed an empty sequence.
15. [system.math.sum](#systemmathsum) - This function is used inPython Scripting. Given a sequence of values, calculates the sum of all values. The sum is the number returned by addition. Returns NaN (Not a Number) if passed an empty sequence.
16. [system.math.sumDifference](#systemmathsumdifference) - This function is used inPython Scripting. Given two sequences of values, calculates the sum of each sequence and finds the difference between them. In other words, the difference between sums from two sets of numbers. Throws a DimensionMismatchException if the two sequences have different lengths.
17. [system.math.sumLog](#systemmathsumlog) - This function is used inPython Scripting. Given a sequence of values, calculates the sum of the natural logs (ln). Returns NaN (Not a Number) if passed an empty sequence.
18. [system.math.sumSquares](#systemmathsumsquares) - This function is used inPython Scripting. Given a sequence of values, calculates the sum of the squares of all values. Sum squares measures how far individual values are from the mean by calculating how much variation there is in a set of values. Returns NaN (Not a Number) if passed an empty sequence.
19. [system.math.variance](#systemmathvariance) - This function is used inPython Scripting. Given a sequence of values, calculates the variance of all values. Variance measures how far values in a set are spread out from their mean value. Returns NaN (Not a Number) if passed an empty sequence.

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

