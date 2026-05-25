# Python Numpy MaskedArray `__add__`

> 原文: [https://www.geeksforgeeks.org/python-numpy-maskedarray-__add__/](https://www.geeksforgeeks.org/python-numpy-maskedarray-__add__/)

`numpy.ma.MaskedArray` 类是 `ndarray` 的一个子类，设计用于处理缺少数据的数值数组。借助 Numpy `MaskedArray.__add__`，我们可以添加一个特定的值，该值作为参数提供给 `MaskedArray.__add__()` 方法。数值将被添加到 numpy 数组中的每个元素。

> **语法:** `numpy.MaskedArray.__add__`
>
> **返回:** 将自己加到其他，返回一个新的屏蔽数组。

## 示例 1

在这个示例中，我们可以看到数组中的每个元素都添加了方法 `MaskedArray.__add__()` 中作为参数给出的值。记住一件事，它对双类型值不起作用。

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.ma.array([1, 2, 3, 4, 5])

# applying MaskedArray.__add__() method
print(gfg.__add__(5))
```

**输出:**

```py
[ 6  7  8  9 10]
```

## 示例 2

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.ma.array([[1, 2, 3, 4, 5],
                [6, 5, 4, 3, 2]])

# applying MaskedArray.__add__() method
print(gfg.__add__(5))
```

**输出:**

```py
[[ 6  7  8  9 10]
 [11 10  9  8  7]]
```