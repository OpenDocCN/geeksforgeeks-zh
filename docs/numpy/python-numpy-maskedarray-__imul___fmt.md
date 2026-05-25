# Python Numpy MaskedArray

## MaskedArray.__imul__()方法

`numpy.ma.MaskedArray class`是`ndarray`的一个子类，设计用于处理缺少数据的数值数组。借助Numpy的`MaskedArray.__imul__()`方法，我们可以将MaskedArray中作为参数提供的特定值相乘。数值将乘以numpy数组中的每个元素。

> **语法:** `numpy.MaskedArray.__imul__(other)`
>
> **返回:** 将自身乘以`other`原地。

**示例#1:**
在这个示例中，我们可以看到数组中的每个元素都与方法`MaskedArray.__imul__()`中作为参数给出的值相乘。记住一件事，它对双类型值不起作用。

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.ma.array([1, 2, 3, 4.7, 5.2])

# applying MaskedArray.__imul__() method
print(gfg.__imul__(5))
```

**Output:**

```py
[  5.   10.   15.   23.5  26. ]
```

**例2:**

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.ma.array([[1, 2, 3, 4, 5],
                [6, 5, 4, 3, 2]])

# applying MaskedArray.__imul__() method
print(gfg.__imul__(5))
```

**Output:**

```py
[[ 5 10 15 20 25]
 [30 25 20 15 10]]
```