# Python `numpy.ndarray.__pow__()`

> 原文链接: https://www.geeksforgeeks.org/python-numpy-numpy-ndarray-__pow__/

借助 `numpy.ndarray.__pow__()` 方法，我们将获得所有元素**乘方**后的结果，其幂值在 `numpy.ndarray.__pow__()` 方法中作为参数提供。

## 语法
`ndarray.__pow__($self, value, mod=None, /)`

## 返回值
返回 `(自身, 数值, mod)` 的幂运算结果。

## 示例 1
在此示例中，我们可以看到每个元素都使用 `ndarray.__pow__()` 方法中作为参数提供的值进行乘方运算。

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.array([1, 2, 3, 4, 5])

# applying ndarray.__pow__() method
print(gfg.__pow__(3))
```

**输出:**

```py
[  1   8  27  64  125]
```

## 示例 2

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.array([[1, 2, 3, 4, 5],
                [6, 5, 4, 3, 2]])

# applying ndarray.__pow__() method
print(gfg.__pow__(2))
```

**输出:**

```py
[[ 1  4  9 16 25]
 [36 25 16  9  4]]
```