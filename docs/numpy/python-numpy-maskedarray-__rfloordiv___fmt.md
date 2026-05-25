# Python | Numpy MaskedArray.__rfloordiv__

> 哎哎哎: [https://www.geeksforgeeks.org/python-numpy-maskedarray-__rfloordiv__/](https://www.geeksforgeeks.org/python-numpy-maskedarray-__rfloordiv__/)

`numpy.ma.MaskedArray class`是`ndarray`的一个子类，设计用于处理缺少数据的数值数组。借助`Numpy MaskedArray.__rfloordiv__`运算符，我们可以用一个特定的值（其他）来划分自我，该值是作为该函数的参数提供的。

> **语法:** `numpy.ma.MaskedArray.__rfloordiv__`
> **返回:** 将自己分割成其他，返回一个新的屏蔽数组。

## 示例 #1
在这个示例中，我们可以看到在应用`MaskedArray.__rfloordiv__()`之后，我们得到了数组中每个元素的底值。此方法对于数组的正、负和浮点值都很有效。

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.ma.array([1, 2.5, 3, 4.8, 5])

# applying MaskedArray.__rfloordiv__() method
print(gfg.__rfloordiv__(2))
```

**Output:**

```py
[2.0 0.0 0.0 0.0 0.0]
```

## 示例 2

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.ma.array([[1, 2, 3, 4.45, 5],
                [6, 5.5, 4, 3, 2.62]])

# applying MaskedArray.__rfloordiv__() method
print(gfg.__rfloordiv__(3))
```

**Output:**

```py
[[3.0 1.0 1.0 0.0 0.0]
 [0.0 0.0 0.0 1.0 1.0]]
```