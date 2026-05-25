# numpy.rollaxis()函数

> 原文: [https://www.geeksforgeeks.org/numpy-rollaxis-function-python/](https://www.geeksforgeeks.org/numpy-rollaxis-function-python/)

`numpy.rollaxis()`函数向后滚动指定的轴，直到它位于给定的位置。

## 语法

`numpy.rollaxis(arr, axis, start=0)`

## 参数

- `arr`: 【ndarray】输入数组。
- `axis`: 【int】轴向后滚动。其他轴的位置相对于彼此不变。
- `start`: 【int，可选】轴滚动到位于该位置之前。默认值0导致“完全”滚动。

## 返回值

【ndarray】在早期的NumPy版本中，只有当轴的顺序改变时才返回`arr`，否则返回输入数组。对于NumPy >= 1.10.0，总是返回`arr`的视图。

## 代码示例

### 代码#1

```py
# Python program explaining
# numpy.rollaxis() function

# importing numpy as geek
import numpy as geek

arr = geek.ones((1, 2, 3, 4))

gfg = geek.rollaxis(arr, 3, 1).shape

print (gfg)
```

**输出:**

```py
(1, 4, 2, 3)
```

### 代码#2

```py
# Python program explaining
# numpy.rollaxis() function

# importing numpy as geek
import numpy as geek

arr = geek.ones((1, 2, 3, 4))

gfg = geek.rollaxis(arr, 2).shape

print (gfg)
```

**输出:**

```py
(3, 1, 2, 4)
```