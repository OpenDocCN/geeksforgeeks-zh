# Python `numpy.ndarray.__ge__()`

> 原文链接: [https://www.geeksforgeeks.org/python-numpy-numpy-ndarray-__ge__/](https://www.geeksforgeeks.org/python-numpy-numpy-ndarray-__ge__/)

借助 **Numpy** 的 `numpy.ndarray.__ge__()` 方法，我们可以判断数组中的哪些元素大于或等于提供的参数值。它将返回一个布尔类型的 NumPy 数组，其中只包含 `True` 和 `False` 值。

> **语法:** `ndarray.__ge__(self, value, /)`
>
> **返回:** `self >= value`

## 示例 1

在这个示例中，我们可以看到在应用 `numpy.__ge__()` 之后，我们得到了一个简单的布尔数组，它可以告诉我们数组中的哪个元素大于或等于提供的参数元素。

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.array([1, 2, 3, 4, 5, 6])

# applying numpy.__ge__() method
print(gfg.__ge__(4))
```

**输出:**

```py
[False False False  True  True  True]
```

## 示例 2

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.array([[1, 2, 3, 4, 5, 6],
                [6, 5, 4, 3, 2, 1]])

# applying numpy.__ge__() method
print(gfg.__ge__(4))
```

**输出:**

```py
[[False False False  True  True  True]
 [ True  True  True False False False]]
```