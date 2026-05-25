# Python：在 NumPy 中查找范围内的元素

> 原文：[https://www.geeksforgeeks.org/python-find-elements-within-range-in-numpy/](https://www.geeksforgeeks.org/python-find-elements-within-range-in-numpy/)

给定一个 NumPy 数组，任务是找到特定范围内的元素。让我们讨论一些完成这项任务的方法。

## 方法一：使用 `np.where()`

```py
# python code to demonstrate
# finding elements in range
# in numpy array
import numpy as np

ini_array = np.array([1, 2, 3, 45, 4, 7, 810, 9, 6])

# printing initial array
print("initial_array : ", str(ini_array));

# find elements in range 6 to 10
result = np.where(np.logical_and(ini_array>= 6, ini_array<= 10))

# printing result
print("resultant_array : ", result)
```

**输出：**

```py
initial_array :  [  1   2   3  45   4   7 810   9   6]
resultant_array :  (array([5, 7, 8]),)
```

## 方法二：使用 `numpy.searchsorted()`

```py
# Python code to demonstrate
# finding elements in range
# in numpy array

import numpy as np

ini_array = np.array([1, 2, 3, 45, 4, 7, 9, 6])

# printing initial array
print("initial_array : ", str(ini_array));

# find elements in range 6 to 10
start = np.searchsorted(ini_array, 6, 'left')
end = np.searchsorted(ini_array, 10, 'right')
result = np.arange(start, end)

# printing result
print("resultant_array : ", result)
```

**输出：**

```py
initial_array :  [ 1  2  3 45  4  7  9  6]
resultant_array :  [5 6 7]
```

## 方法三：使用布尔索引

```py
# Python code to demonstrate
# finding elements in range
# in numpy array

import numpy as np

ini_array = np.array([1, 2, 3, 45, 4, 7, 9, 6])

# printing initial array
print("initial_array : ", str(ini_array));

# find elements in range 6 to 10
result = ini_array[(ini_array>6)*(ini_array<10)]

# printing result
print("resultant_array : ", result)
```

**输出：**

```py
initial_array :  [ 1  2  3 45  4  7  9  6]
resultant_array :  [7 9]
```