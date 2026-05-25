# numpy.moveaxis() 函数 | Python

> 原文: [https://www.geeksforgeeks.org/numpy-moveaxis-function-python/](https://www.geeksforgeeks.org/numpy-moveaxis-function-python/)

`numpy.moveaxis()` 函数将数组的轴移动到新的位置。其他轴保持原来的顺序。

## 语法

`numpy.moveaxis(arr, source, destination)`

## 参数

- `arr`: 【ndarray】 输入数组。
- `source`: 【int 或 int 序列】 要移动的轴的原始位置。这些必须是独特的。
- `destination`: 【int 或 int 序列】 每个原始轴的目标位置。这些也必须是独一无二的。

## 返回

【ndarray】 带移动轴的数组。这个数组是输入数组的视图。

## 代码示例

**代码#1:**

```py
# Python program explaining
# numpy.moveaxis() function

# importing numpy as geek
import numpy as geek

arr = geek.zeros((1, 2, 3, 4))

gfg = geek.moveaxis(arr, 0, -1).shape

print(gfg)
```

**输出:**

```py
(2, 3, 4, 1)
```

**代码#2:**

```py
# Python program explaining
# numpy.moveaxis() function

# importing numpy as geek
import numpy as geek

arr = geek.zeros((1, 2, 3, 4))

gfg = geek.moveaxis(arr, -1, 0).shape

print(gfg)
```

**输出:**

```py
(4, 1, 2, 3)
```