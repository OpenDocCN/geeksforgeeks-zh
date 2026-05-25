# Python NumPy `ndarray.__invert__()`

> 原文链接: https://www.geeksforgeeks.org/python-numpy-numpy-ndarray-__invert__/

在`Numpy ndarray.__invert__()`的帮助下，可以**反转**一个数组的元素。我们不必提供任何类型的参数，但请记住，此方法仅适用于**整数**值。

> **语法:** `ndarray.__invert__($self, /)`
>
> **返回:** `~self`

## 示例 1

在这个示例中，我们可以看到数组中的每个元素都是借助`ndarray.__invert__()`方法对一元运算符`~`进行运算的。

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.array([1, 2, 3, 4, 5])

# applying ndarray.__invert__() method
print(gfg.__invert__())
```

**输出:**

```py
[-2 -3 -4 -5 -6]
```

## 示例 2

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.array([[1, 2, 3, 4, 5],
                [6, 5, 4, 3, 2]])

# applying ndarray.__invert__() method
print(gfg.__invert__())
```

**输出:**

```py
[[-2 -3 -4 -5 -6]
 [-7 -6 -5 -4 -3]]
```