# Python | Numpy MaskedArray.__ge__

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-num py-masked array-_ _ _ ge _/

`numpy.ma.MaskedArray class`是`ndarray`的一个子类，设计用于处理缺少数据的数值数组。借助 Numpy `MaskedArray.__ge__`运算符我们可以找到数组中的哪个元素大于或等于参数中提供的值。

## 语法
`numpy.ma.MaskedArray.__ge__`

**返回:**`self >= value`

## 示例

### 示例 1
在这个示例中，我们可以看到在应用`MaskedArray.__ge__()`之后，我们得到了简单的布尔数组，它可以告诉我们数组中的哪个元素大于或等于提供的参数。

```py
# import the important module in python 
import numpy as np

# make an array with numpy 
gfg = np.ma.array([1, 2, 3, 4, 5, 6])

# applying MaskedArray.__ge__() method 
print(gfg.__ge__(4)) 
```

**Output:**

```py
[False False False  True  True  True]
```

### 示例 2

```py
# import the important module in python 
import numpy as np

# make an array with numpy 
gfg = np.ma.array([[1, 2, 3, 4, 5, 6], 
                [6, 5, 4, 3, 2, 1]])

# applying MaskedArray.__ge__() method 
print(gfg.__ge__(4)) 
```

**Output:**

```py
[[False False False  True  True  True]
 [ True  True  True False False False]]
```