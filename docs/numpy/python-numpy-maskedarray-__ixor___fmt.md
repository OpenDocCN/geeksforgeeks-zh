# Python Numpy MaskedArray.__ixor__

> 哎哎哎: [https://www.geeksforgeeks.org/python-numpy-maskedarray-__ixor__/](https://www.geeksforgeeks.org/python-numpy-maskedarray-__ixor__/)

`numpy.ma.MaskedArray class`是`ndarray`的一个子类，设计用于处理缺少数据的数值数组。借助`MaskedArray.__ixor__`，我们可以通过掩码数组中作为参数提供的值得到异或运算的元素。

> **语法:** `numpy.ma.MaskedArray.__ixor__(self, value, /)`
>
> **返回:** 返回`self ^= value`。

**示例 #1:**
在这个示例中，我们可以看到每个元素都通过在`MaskedArray`中作为参数传递的值进行异或运算。

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.ma.array([1, 2, 3, 4, 5])

# applying MaskedArray.__ixor__() method
print(gfg.__ixor__(2))
```

**输出:**

```py
[3 0 1 6 7]
```

**示例 2:**

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.ma.array([[1, 2, 3, 4, 5],
                [6, 5, 4, 3, 2]])

# applying MaskedArray.__ixor__() method
print(gfg.__ixor__(1))
```

**输出:**

```py
[[0 3 2 5 4]
 [7 4 5 2 3]]
```