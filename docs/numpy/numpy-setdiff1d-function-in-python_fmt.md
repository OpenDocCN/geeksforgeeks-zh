# Python 中的 numpy.setdiff1d()函数

> 原文:[https://www . geesforgeks . org/numpy-setdiff1d-python 中的函数/](https://www.geeksforgeeks.org/numpy-setdiff1d-function-in-python/)

`numpy.setdiff1d()` 函数求两个数组的集合差，返回 `arr1` 中不在 `arr2` 中的唯一值。

> **语法:** `numpy.setdiff1d(arr1, arr2, assume_unique=False)`
>
> **参数:**
> `arr1`:【array_like】输入数组。
> `arr2`:【array_like】输入比较数组。
> `assume_unique`:【bool】如果为真，则输入数组都假设为唯一，这样可以加快计算速度。默认值为假。
>
> **返回:**【ndarray】`arr1` 中不在 `arr2` 中的值的 1D 数组。当 `assume_unique=False` 时，对结果进行排序，否则仅在对输入进行排序时对结果进行排序。

**代码#1 :**

```py
# Python program explaining
# numpy.setdiff1d() function

# importing numpy as geek 
import numpy as geek

arr1 = [5, 6, 2, 3, 4]
arr2 = [1, 2, 3]

gfg = geek.setdiff1d(arr1, arr2)

print (gfg)
```

**输出:**

```py
[4 5 6]
```

**代码#2 :**

```py
# Python program explaining
# numpy.setdiff1d() function

# importing numpy as geek 
import numpy as geek

arr1 = [1, 2, 3, 4, 5, 6, 7, 8, 9]
arr2 = [1, 3, 5, 7, 9, 11, 13, 15]

gfg = geek.setdiff1d(arr1, arr2)

print (gfg)
```

**输出:**

```py
[2 4 6 8]
```