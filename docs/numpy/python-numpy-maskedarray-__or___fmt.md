# Python | NumPy MaskedArray.__or__

> 原文：[https://www.geeksforgeeks.org/python-numpy-maskedarray-__or__/](https://www.geeksforgeeks.org/python-numpy-maskedarray-__or__/)

`numpy.ma.MaskedArray class`是`ndarray`的一个子类，设计用于处理缺少数据的数值数组。借助 NumPy `MaskedArray.__or__`方法，我们可以通过作为参数提供的值来获得元素，即**或**运算。

> **语法：** `numpy.ma.MaskedArray.__or__`
>
> **返回：** 返回自身 | 值。

## 示例 #1

在这个示例中，我们可以看到每个元素都是或运算作为参数传递的值。

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.ma.array([1, 2, 3, 4, 5])

# applying MaskedArray.__or__() method
print(gfg.__or__(2))
```

**输出：**

```py
[3 2 3 6 7]
```

## 示例 2

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.ma.array([[1, 2, 3, 4, 5],
                    [6, 5, 4, 3, 2]])

# applying MaskedArray.__or__() method
print(gfg.__or__(1))
```

**输出：**

```py
[[1 3 3 5 5]
 [7 5 5 3 3]]
```