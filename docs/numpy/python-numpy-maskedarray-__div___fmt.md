# Python | Numpy MaskedArray.__div__

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-num py-masked array-_ _ _ _ _ _ _ div _/

`numpy.ma.MaskedArray class`是`ndarray`的一个子类，设计用于处理缺少数据的数值数组。在Numpy MaskedArray的帮助下，通过`__div__()`方法，我们可以对MaskedArray中作为参数提供的特定值进行划分。

> **语法:** `numpy.ma.MaskedArray.__div__()`
>
> **返回:** 将他人分割成自己，返回一个新的屏蔽数组。

## 示例#1

在这个示例中，我们可以看到数组中的每个元素都用`MaskedArray.__div__()`方法中作为参数给出的值进行了划分。

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.ma.array([22, 33, 44, 55, 77])

# applying MaskedArray.__div__() method
print(gfg.__div__(11))
```

**Output:**

```py
[2.0 3.0 4.0 5.0 7.0]
```

## 示例2

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.ma.array([[10, 20, 30, 40, 50],
                [11, 22, 33, 44, 55]])

# applying MaskedArray.__div__() method
print(gfg.__div__(5))
```

**Output:**

```py
[[2.0 4.0 6.0 8.0 10.0]
 [2.2 4.4 6.6 8.8 11.0]]
```