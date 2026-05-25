# Python NumPy `ndarray.__ior__()` 方法

> 哎哎哎::1230 [https://www.geeksforgeeks.org/python-numpy-ndarray-ior/](https://www.geeksforgeeks.org/python-numpy-ndarray-ior/)

借助 `ndarray.__ior__()` 方法，我们可以通过作为参数传递的值，对数组中的元素进行按位或赋值运算。

**语法:**
`ndarray.__ior__(self, value, /)`

**返回:**
`self |= value`

**示例 #1:**
在这个示例中，我们可以看到每个元素都与作为参数传递的值进行了按位或赋值运算。

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.array([1, 2, 3, 4, 5])

# applying ndarray.__ior__() method
print(gfg.__ior__(2))
```

**输出:**

```py
[3 2 3 6 7]
```

**示例 #2:**

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.array([[1, 2, 3, 4, 5],
                [6, 5, 4, 3, 2]])

# applying ndarray.__ior__() method
print(gfg.__ior__(1))
```

**输出:**

```py
[[1 3 3 5 5]
 [7 5 5 3 3]]
```