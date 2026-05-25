# Python `numpy.ndarray.__le__()`

> 原文链接: [https://www.geeksforgeeks.org/python-numpy-numpy-ndarray-__le__/](https://www.geeksforgeeks.org/python-numpy-numpy-ndarray-__le__/)

借助于 `Numpy` 的 `numpy.ndarray.__le__()` 方法，我们可以发现数组中的哪个元素小于或等于参数中提供的值。它将返回一个布尔类型的 `numpy` 数组，只有值 `True` 和 `False`。

**语法:**
`ndarray.__le__(self, value, /)`

**返回:**
`self <= value`

## 示例 #1

在这个示例中，我们可以看到在应用 `numpy.__le__()` 之后，我们得到了简单的布尔数组，它可以告诉我们数组中的哪个元素小于或等于提供的参数的元素。

```python
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.array([1, 2, 3, 4, 5, 6])

# applying numpy.__le__() method
print(gfg.__le__(4))
```

**输出:**

```python
[ True  True  True  True False False]
```

## 示例 2

```python
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.array([[1, 2, 3, 4, 5, 6],
                [6, 5, 4, 3, 2, 1]])

# applying numpy.__le__() method
print(gfg.__le__(4))
```

**输出:**

```python
[[ True  True  True  True False False]
 [False False  True  True  True  True]]
```