# numpy.ndarray.__rshift__()

> 原文链接: https://www.geeksforgeeks.org/python-numpy-numpy-ndarray-__rshift__/

借助`numpy.ndarray.__rshift__()`方法，我们可以通过该方法中作为参数提供的值，得到**右移**的元素。

## 语法
`ndarray.__rshift__($self, value, /)`

## 返回
`self >> value`

## 示例 1
在这个示例中，我们可以看到每个元素都向右移动了在`ndarray.__rshift__()`方法中作为参数传递的值。

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.array([1, 2, 3, 4, 5])

# applying ndarray.__rshift__() method
print(gfg.__rshift__(2))
```

**输出:**

```py
[0 0 0 1 1]
```

## 示例 2

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.array([[1, 2, 3, 4, 5],
                [6, 5, 4, 3, 2]])

# applying ndarray.__rshift__() method
print(gfg.__rshift__(1))
```

**输出:**

```py
[[0 1 1 2 2]
 [3 2 2 1 1]]
```