# 如何用 NumPy 获取数组的唯一元素？

> 原文: [https://www.geeksforgeeks.org/how-to-get-the-unique-elements-of-an-array-using-numpy/](https://www.geeksforgeeks.org/how-to-get-the-unique-elements-of-an-array-using-numpy/)

让我们看看如何使用 NumPy 获取数组的唯一元素。所以为了从数组中找到唯一的元素，我们使用了 NumPy 库的 `numpy.unique()` 函数。

> **语法:** `np.unique(arr)`
> **Return:** 返回一个数组的唯一值。

现在，让我们看看例子:

**例 1:**

## Python 3

```py
# import library
import numpy as np

# create 1d-array
arr = np.array([3, 3, 4,
                5, 6, 5,
                6, 4])

# find unique element
# from a array
rslt = np.unique(arr)

print(rslt)
```

**输出:**

```py
[3 4 5 6]
```

**例 2:**

## Python 3

```py
# import library
import numpy as np

# create a numpy 2d-array
arr = np.array([[9, 9, 7, 7],
                [3, 4, 3, 4]])

# find unique element
# from a array
rslt = np.unique(arr)

print(rslt)
```

**输出:**

```py
[3 4 7 9]
```