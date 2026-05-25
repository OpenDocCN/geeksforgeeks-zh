# Python | Numpy MaskedArray

## `__ifloordiv__`方法

`numpy.ma.MaskedArray`类是`ndarray`的一个子类，设计用于处理缺少数据的数值数组。借助Numpy的`MaskedArray.__ifloordiv__`方法，我们可以获得特定值的地板除，该值在MaskedArray中作为参数提供给`__ifloordiv__()`方法。

**语法:**
`numpy.ma.MaskedArray.__ifloordiv__(other)`

**返回:**
地板除自己除以`other`，原地操作。

### 示例 1

在这个示例中，我们可以看到数组中的每个元素都用作为参数给出的值进行了地板除。

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.ma.array([10, 20.5, 30, 4.8, 50])

# applying MaskedArray.__ifloordiv__() method
print(gfg.__ifloordiv__(2))
```

**输出:**

```py
[  5.  10.  15.   2.  25.]
```

### 示例 2

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.ma.array([[10, 20, 30, 4.45, 50],
                [6, 5.5, 4, 3, 2.62]])

# applying MaskedArray.__ifloordiv__() method
print(gfg.__ifloordiv__(5))
```

**输出:**

```py
[[  2.   4.   6.   0.  10.]
 [  1.   1.   0.   0.   0.]]
```