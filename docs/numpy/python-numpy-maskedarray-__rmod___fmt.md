# Python Numpy MaskedArray

## `__rmod__` 方法

> 原文链接: https://www.geeksforgeeks.org/python-numpy-maskedarray/

`numpy.ma.MaskedArray class` 是 `ndarray` 的一个子类，设计用于处理缺少数据的数值数组。借助 Numpy `MaskedArray.__rmod__`，掩码数组中的每个元素都使用二进制运算符 `mod (%)` 进行操作。请记住，我们可以在数组中使用任何类型的值，`mod` 的值将作为 `MaskedArray` 中的参数应用 `__rmod__()`。

> **语法:** `numpy.ma.MaskedArray.__rmod__(other)`
>
> **返回:** 返回 `value % self`。

**示例 1:**
我们可以看到通过 `MaskedArray` 传递的值。`__rmod__()` 方法用于对数组的每个元素执行 `mod` 操作。

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.ma.array([1, 2.5, 3, 4.8, 5])

# applying MaskedArray.__rmod__() method
print(gfg.__rmod__(2))
```

**输出:**

```py
[0.0 2.0 2.0 2.0 2.0]
```

**示例 2:**

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.ma.array([[1, 2, 3, 4.45, 5],
                [6, 5.5, 4, 3, 2.62]])

# applying MaskedArray.__rmod__() method
print(gfg.__rmod__(3))
```

**输出:**

```py
[[0.0 1.0 0.0 3.0 3.0]
 [3.0 3.0 3.0 0.0 0.3799999999999999]]
```