# numpy.ma.allclose() 函数 – Python

> 原文: [https://www.geeksforgeeks.org/numpy-ma-allclose-function-python/](https://www.geeksforgeeks.org/numpy-ma-allclose-function-python/)

`numpy.ma.allclose()` 函数用于判断两个数组在公差范围内元素是否相等。除了根据 `masked_equal` 参数将掩码值视为相等（默认）或不相等之外，此函数等效于 `allclose`。

## 语法

`numpy.ma.allclose(a, b, masked_equal=True, rtol=1e-05, atol=1e-08)`

## 参数

- `a`, `b`: 输入数组进行比较。
- `masked_equal`: 布尔值，可选。`a` 和 `b` 中的被屏蔽值是否被认为相等（`True`）或不相等（`False`）。默认情况下，它们被认为是相等的。
- `rtol`: 浮点数，可选。相对公差。相对差值等于 `rtol * b`，默认值为 `1e-5`。
- `atol`: 浮点数，可选。绝对公差。绝对差等于 `atol`。默认值为 `1e-8`。

## 返回

布尔值。如果两个数组在给定容差内相等，则返回 `True`，否则返回 `False`。如果任一数组包含 `NaN`，则返回 `False`。

## 代码示例 1

```py
# Python program explaining
# numpy.ma.allclose() function

# importing numpy as geek 
# and numpy.ma module as ma 
import numpy as geek 
import numpy.ma as ma

a = geek.ma.array([1e10, 1e-8, 42.0], mask = [0, 0, 1])

b = geek.ma.array([1.00001e10, 1e-9, -42.0], mask = [0, 0, 1])

gfg = geek.ma.allclose(a, b)

print (gfg)
```

输出：

```py
True
```

## 代码示例 2

```py
# Python program explaining
# numpy.ma.allclose() function

# importing numpy as geek 
# and numpy.ma module as ma 
import numpy as geek 
import numpy.ma as ma

a = geek.ma.array([1e10, 1e-8, 42.0], mask = [0, 0, 1])

b = geek.ma.array([1.00001e10, 1e-9, -42.0], mask = [0, 0, 1])

gfg = geek.ma.allclose(a, b, masked_equal = False)

print (gfg)
```

输出：

```py
False
```