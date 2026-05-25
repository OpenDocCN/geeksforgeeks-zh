# Python | numpy.ndarray.__or__() 方法

> 哎哎哎: [https://www.geeksforgeeks.org/python-numpy-numpy-ndarray-__or__-or-__/](https://www.geeksforgeeks.org/python-numpy-numpy-ndarray-__or__-or-__/)

借助 `numpy.ndarray.__or__()` 方法，我们可以通过在该方法中作为参数提供的值，得到元素进行**或**运算的结果。

> **语法:** `ndarray.__or__($self, value, /)`
>
> **返回:** `自身 | 值`

## 示例 #1

在此示例中，我们可以通过在 `ndarray.__or__()` 方法中作为参数传递的值，看到每个元素都是**或**运算的结果。

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.array([1, 2, 3, 4, 5])

# applying ndarray.__or__() method
print(gfg.__or__(2))
```

**Output:**

```py
[3 2 3 6 7]
```

## 例 2

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.array([[1, 2, 3, 4, 5],
                [6, 5, 4, 3, 2]])

# applying ndarray.__or__() method
print(gfg.__or__(1))
```

**Output:**

```py
[[1 3 3 5 5]
 [7 5 5 3 3]]
```