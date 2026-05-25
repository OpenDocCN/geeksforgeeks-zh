# Python `numpy.ndarray.__add__()`

> 原文链接: [https://www.geeksforgeeks.org/python-numpy-numpy-ndarray-__add__/](https://www.geeksforgeeks.org/python-numpy-numpy-ndarray-__add__/)

借助 `numpy.ndarray.__add__()`，我们可以添加一个特定的值，该值在 `ndarray.__add__()` 方法中作为参数提供。值将被添加到 **numpy 数组**中的每个元素。

**语法:**
`ndarray.__add__($self, value, /)`

**返回:**
自身 + 值

**示例 #1:**
在这个示例中，我们可以看到数组中的每个元素都添加了方法 `ndarray.__add__()` 中作为参数给出的值。记住一件事，它不会为双精度类型值工作。

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.array([1, 2, 3, 4, 5])

# applying ndarray.__add__() method
print(gfg.__add__(5))
```

**Output:**

```py
[ 6  7  8  9  10]
```

**示例 2:**

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.array([[1, 2, 3, 4, 5],
                [6, 5, 4, 3, 2]])

# applying ndarray.__add__() method
print(gfg.__add__(5))
```

**Output:**

```py
[[ 6  7  8  9  10]
 [11  10  9  8  7]]
```