# `ndarray.__array__()`方法

> 原文链接: [https://www.geeksforgeeks.org/python-numpy-ndarray-__array__/](https://www.geeksforgeeks.org/python-numpy-ndarray-__array__/)

借助`ndarray.__array__()`方法，我们可以通过给定一个参数作为`dtype`来创建一个我们想要的新数组。如果我们改变新数组中的任何元素，我们可以获得一个不改变原始数组数据元素的数组副本。

**语法:**
`ndarray.__array__()`

**返回:**
*   如果未给出数据类型，则返回对自身的新引用。
*   如果数据类型不同于数组的当前数据类型，则为所提供数据类型的新数组。

**示例#1:**

在这个例子中，我们可以看到我们仅仅通过使用`ndarray.__array__()`方法就改变了新数组的**数据类型**。

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.array([1, 2, 3, 4, 5])

# applying ndarray.__array__() method
geeks = gfg.__array__(float)

print(geeks)
```

**输出:**

```py
[ 1.  2.  3.  4.  5.]
```

**示例#2:**

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.array([[1.1, 2, 3.3, 4, 5],
                [6, 5.2, 4, 3, 2.2]])

# applying ndarray.__array__() method
geeks = gfg.__array__(int)

print(geeks)
```

**输出:**

```py
[[1 2 3 4 5]
 [6 5 4 3 2]]
```