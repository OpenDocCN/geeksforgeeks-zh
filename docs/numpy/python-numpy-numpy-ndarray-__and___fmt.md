# Python NumPy ndarray.__and__()

> 原文链接: https://www.geeksforgeeks.org/python-numpy-numpy-ndarray-__and__/

借助`numpy.ndarray.__and__()`方法，我们可以通过该方法中作为参数提供的值，得到按位与（AND）运算后的元素。

## 语法
`ndarray.__and__($self, value, /)`

## 返回
`self & value`

## 示例 1
在这个示例中，我们可以看到每个元素都由在`ndarray.__and__()`方法中作为参数传递的值进行按位与运算。

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.array([1, 2, 3, 4, 5])

# applying ndarray.__and__() method
print(gfg.__and__(2))
```

**输出:**

```py
[0 2 2 0 0]
```

## 示例 2

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.array([[1, 2, 3, 4, 5],
                [6, 5, 4, 3, 2]])

# applying ndarray.__and__() method
print(gfg.__and__(1))
```

**输出:**

```py
[[1 0 1 0 1]
 [0 1 0 1 0]]
```