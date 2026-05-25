# NumPy 掩码数组：`__truediv__` 方法

`numpy.ma.MaskedArray` 类是 `ndarray` 的一个子类，设计用于处理缺少数据的数值数组。借助 `MaskedArray.__truediv__()` 方法，我们可以将一个特定的值（作为参数提供）除以 `MaskedArray` 中的每个元素。

## 语法
`numpy.ma.MaskedArray.__truediv__()`

## 返回值
将参数值作为除数，对数组中的每个元素进行除法运算，返回一个新的掩码数组。

## 示例 1
在这个示例中，数组中的每个元素都用 `__truediv__()` 方法中作为参数给出的值进行了除法运算。

```py
# import the important module in python 
import numpy as np

# make an array with numpy 
gfg = np.ma.array([22, 33.7, 44.5, 55, 77])

# applying MaskedArray.__truediv__() method 
print(gfg.__truediv__(11)) 
```

**输出:**

```py
[2.0 3.063636363636364 4.045454545454546 5.0 7.0]
```

## 示例 2

```py
# import the important module in python 
import numpy as np

# make an array with numpy 
gfg = np.ma.array([[10, 20, 30, 40, 50], 
                [11, 22, 33, 44, 55]])

# applying MaskedArray.__truediv__() method 
print(gfg.__truediv__(5)) 
```

**输出:**

```py
[[2.0 4.0 6.0 8.0 10.0]
 [2.2 4.4 6.6 8.8 11.0]]
```