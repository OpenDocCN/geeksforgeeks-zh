# Numpy count_nonzero方法 | Python

> 原文: [https://www.geeksforgeeks.org/numpy-count_nonzero-method-python/](https://www.geeksforgeeks.org/numpy-count_nonzero-method-python/)

`numpy.count_nonzero()` 函数计算数组 `arr` 中非零值的个数。

> **语法:** `numpy.count_nonzero(arr, axis=None)`
>
> **参数:**
> `arr`: 【array_like】要计算非 0 的数组。
> `axis`: 【int 或 tuple，可选】轴或轴的 tuple，沿其计数非 0。默认值为 `None`，这意味着非 0 将沿着平坦版本的 `arr` 进行计数。
>
> **返回:** 【int 或 int 数组】数组中沿给定轴的非零值的数量。否则，返回数组中非零值的总数。

**代码#1:**

```py
# Python program explaining
# numpy.count_nonzero() function

# importing numpy as geek
import numpy as geek

arr = [[0, 1, 2, 3, 0], [0, 5, 6, 0, 7]]

gfg = geek.count_nonzero(arr)

print (gfg)
```

**输出:**

```py

```

**代码#2:**

```py
# Python program explaining
# numpy.count_nonzero() function

# importing numpy as geek
import numpy as geek

arr = [[0, 1, 2, 3, 4], [5, 0, 6, 0, 7]]

gfg = geek.count_nonzero(arr, axis = 0)

print (gfg)
```

**输出:**

```py

```