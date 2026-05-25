# Python | Numpy MaskedArray.__rand__

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-num py-masked array-_ _ _ rand _/

`numpy.ma.MaskedArray`类是`ndarray`的一个子类，设计用于处理缺少数据的数值数组。借助`Numpy MaskedArray.__rand__`方法我们可以得到元素，这些元素被作为参数提供的值所and。

> **语法:** `numpy.ma.MaskedArray.__rand__`
> **返回:** `return value & self`

## 示例#1
在这个示例中，我们可以看到每个元素都由作为参数传递的值进行and运算。

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.ma.array([1, 2, 3, 4, 5])

# applying MaskedArray.__rand__() method
print(gfg.__rand__(2))
```

**Output:**

```py
[0 2 2 0 0]
```

## 例2

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.ma.array([[1, 2, 3, 4, 5],
                [6, 5, 4, 3, 2]])

# applying MaskedArray.__rand__() method
print(gfg.__rand__(1))
```

**Output:**

```py
[[1 0 1 0 1]
 [0 1 0 1 0]]
```