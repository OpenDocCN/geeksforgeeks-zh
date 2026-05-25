# Python | Numpy MaskedArray.__ne__

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-num py-masked array-_ _ ne _/

`numpy.ma.MaskedArray class` 是 `ndarray` 的一个子类，旨在处理缺少数据的数值数组。在 Numpy 的帮助下，使用 `MaskedArray.__ne__` 运算符我们可以发现数组中的哪个元素不等于参数中提供的值。

> **语法:** `numpy.ma.MaskedArray.__ne__`
> 
> **返回:** `self != value`

## 示例 #1

在这个示例中，我们可以看到在应用 `MaskedArray.__ne__()` 之后，我们得到了简单的布尔数组，它可以告诉我们数组中的哪个元素不等于提供的参数。

```py
# import the important module in python 
import numpy as np

# make an array with numpy 
gfg = np.ma.array([1, 2, 3, 4, 5, 6])

# applying MaskedArray.__ne__() method 
print(gfg.__ne__(4)) 
```

**输出:**

```py
[ True  True  True False  True  True]
```

## 示例 2

```py
# import the important module in python 
import numpy as np

# make an array with numpy 
gfg = np.ma.array([[1, 2, 3, 4, 5, 6], 
                [6, 5, 4, 3, 2, 1]])

# applying MaskedArray.__ne__() method 
print(gfg.__ne__(4)) 
```

**输出:**

```py
[[ True  True  True False  True  True]
 [ True  True False  True  True  True]]
```