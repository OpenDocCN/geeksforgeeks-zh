# Python NumPy `broadcast_arrays()` 方法

> 原文: `https://www.geeksforgeeks.org/python-numpy-broadcast_arrays-method/`

借助 `Numpy.broadcast_arrays()` 方法，利用两个或两个以上的数组，可以得到一个广播数组。

> **语法:** `Numpy.broadcast_arrays()`
>
> **返回:** 使用 NumPy 返回广播的数组。

## 示例 1

在这个示例中，我们可以看到，通过使用 `Numpy.broadcast_arrays()` 方法，我们能够使用两个或更多 NumPy 数组来获得广播数组。

```py
# import numpy
import numpy as np

# using Numpy.broadcast_arrays() method
gfg1 = np.array([[1, 2]])
gfg2 = np.array([[3], [4]])

print(np.broadcast_arrays(gfg1, gfg2))
```

**输出:**

[array([[1, 2],
       [1, 2]]), array([[3, 3],
       [4, 4]])]

## 示例 2

```py
# import numpy
import numpy as np

# using Numpy.broadcast_arrays() method
gfg1 = np.array([[1, 2], [6, 7]])
gfg2 = np.array([[3, 5], [4, 8]])

print(np.broadcast_arrays(gfg1, gfg2))
```

**输出:**

[array([[1, 2],
       [6, 7]]), array([[3, 5],
       [4, 8]])]