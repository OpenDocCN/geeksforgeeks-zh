# Python NumPy `ndarray.__divmod__()`

> 原文链接: https://www.geeksforgeeks.org/python-numpy-numpy-ndarray-__divmod__/

借助`numpy.ndarray.__divmod__()`方法，我们将得到两个数组：一个是元素被`numpy.ndarray.__divmod__()`方法中提供的值除以后的结果，第二个是元素与该值执行`mod`操作后的结果。

**语法:**
`ndarray.__divmod__(self, value, /)`

**返回:**
`divmod(self, value)`

## 示例 1

在这个示例中，我们可以看到，通过使用`ndarray.__divmod__()`方法，我们得到了两个数组。一个是用作为参数传递的值进行整除，另一个是用该值取模。

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.array([1, 2, 3, 4, 5])

# applying ndarray.__divmod__() method
print(gfg.__divmod__(3))
```

**输出:**

```py
(array([0, 0, 1, 1, 1]), array([1, 2, 0, 1, 2]))
```

## 示例 2

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.array([[1, 2, 3, 4, 5],
                [6, 5, 4, 3, 2]])

# applying ndarray.__divmod__() method
print(gfg.__divmod__(3))
```

**输出:**

```py
(array([[0, 0, 1, 1, 1],
       [2, 1, 1, 1, 0]]), 
 array([[1, 2, 0, 1, 2],
       [0, 2, 1, 0, 2]]))
```