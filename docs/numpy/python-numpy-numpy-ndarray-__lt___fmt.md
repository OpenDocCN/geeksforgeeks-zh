# numpy.ndarray.__lt__()

> 原文链接: https://www.geeksforgeeks.org/python-numpy-numpy-ndaarray-__lt__/

借助 `Numpy` 的 `numpy.ndarray.__lt__()` 方法，我们可以发现数组中的哪个元素比参数中提供的值少。它将返回一个布尔类型的 numpy 数组，只有值 `True` 和 `False`。

> **语法:** `ndarray.__lt__(self, value, /)`
> 
> **返回:** `self < value`

**示例 #1:**
在这个示例中，我们可以看到在应用 `numpy.__lt__()` 之后，我们得到了简单的布尔数组，它可以告诉我们数组中的哪个元素比提供的参数少。

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.array([1, 2, 3, 4, 5, 6])

# applying numpy.__lt__() method
print(gfg.__lt__(4))
```

**Output:**

```
[True True True False False False]
```

**例 2:**

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.array([[1, 2, 3, 4, 5, 6],
                [6, 5, 4, 3, 2, 1]])

# applying numpy.__lt__() method
print(gfg.__lt__(4))
```

**Output:**

```
[[True True True False False False]
 [False False False True True True]]
```