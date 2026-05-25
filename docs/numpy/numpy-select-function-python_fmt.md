# numpy.select() 函数

> 原文: [https://www.geeksforgeeks.org/numpy-select-function-python/](https://www.geeksforgeeks.org/numpy-select-function-python/)

## `numpy.select()`

`numpy.select()` 函数根据条件返回从 `choicelist` 中的元素绘制的数组。

### 语法
`numpy.select(condlist, choicelist, default=0)`

### 参数
- **`condlist`**: 【bool ndarray 列表】它确定从 `choicelist` 中的哪个数组获取输出元素。当满足多个条件时，使用 `condlist` 中遇到的第一个条件。
- **`choicelist`**: 【数组列表】提取输出元素的数组列表。它必须和 `condlist` 一样长。
- **`default`**: 【标量，可选】当所有条件评估为 `False` 时，在输出中插入的元素。

### 返回值
【ndarray】根据条件，从选择列表中的元素中提取的数组。

### 代码示例 1

```py
# Python program explaining
# numpy.select() function

# importing numpy as geek 
import numpy as geek

arr = geek.arange(8)

condlist = [arr<3, arr>4]
choicelist = [arr, arr**3]

gfg = geek.select(condlist, choicelist)

print (gfg)
```

**输出:**

```py
[  0, 1, 2, 0, 0, 125, 216, 343]
```

### 代码示例 2

```py
# Python program explaining
# numpy.select() function

# importing numpy as geek 
import numpy as geek

arr = geek.arange(8)

condlist = [arr<4, arr>6]
choicelist = [arr, arr**2]

gfg = geek.select(condlist, choicelist)

print (gfg)
```

**输出:**

```py
[ 0, 1, 2, 3, 0, 0, 0, 49]
```