# 如何将 NumPy 数组的元素舍入到最近的整数？

> 原文: [https://www.geeksforgeeks.org/how-to-round-elements-of-the-numpy-array-to-the-nearest-integer/](https://www.geeksforgeeks.org/how-to-round-elements-of-the-numpy-array-to-the-nearest-integer/)

**先决条件:** [NumPy](https://www.geeksforgeeks.org/python-numpy/)

在本文中，让我们讨论如何将 NumPy 数组的元素舍入到最近的整数。Python 的 [`numpy.rint()`](https://www.geeksforgeeks.org/numpy-rint-python/) 函数，可以将数组的元素转换为最近的整数。

> **语法:** `numpy.rint(x, /, out=None, *, where=True, casting='same_kind', order='K', dtype=None, subok=True[, signature, extobj]) = <ufunc 'rint'>`

## 例 1

```python
import numpy as n

# create array
y = n.array([0.2, 0.3, 0.4, 0.5, 0.6, 0.7])
print("Original array:", end=" ")
print(y)

# rount to nearest integer
y = n.rint(y)
print("After rounding off:", end=" ")
print(y)
```

**输出:**

![](img/79babbeb0bb1f9d3bbbec3deedb6d6c8.png)

## 例 2

```python
import numpy as n

# create array
y = n.array([-0.2, 0.7, -1.4, -4.5, -7.6, -19.7])
print("Original array:", end=" ")
print(y)

# rount to nearest integer
y = n.rint(y)
print("After rounding off:", end=" ")
print(y)
```

**输出:**

![](img/36aa6d6876255c6ab8c469c485e968ae.png)