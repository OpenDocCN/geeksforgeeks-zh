# Python | Numpy `np.hermweight()`方法

> 原文: [https://www.geeksforgeeks.org/python-numpy-np-hermweight-method/](https://www.geeksforgeeks.org/python-numpy-np-hermweight-method/)

借助`np.hermweight()`方法，利用`np.hermweight()`方法在 hermite 级数中应用权函数，可以得到 hermite 多项式。

> **语法:** `np.hermweight(series)`
> **返回:** 返回埃尔米特多项式的系数。

## 示例#1

在这个示例中我们可以看到，通过使用`np.hermweight()`方法，我们能够通过使用该方法在 hermite 级数中应用权函数来获得 hermite 多项式。

```py
# import numpy and hermweight
import numpy as np
from numpy.polynomial.hermite import hermweight

series = np.array([6, 7, 8, 9, 10])
# using np.hermweight() method
gfg = hermweight(series)

print(gfg)
```

**输出:**

> [2.31952283e-16 5.24288566e-22 1.60381089e-28 6.63967720e-36
> 3.72007598e-44]

## 例 2

```py
# import numpy and hermweight
import numpy as np
from numpy.polynomial.hermite import hermweight

series = np.array([0, -7, 8, -9, 1])
# using np.hermweight() method
gfg = hermweight(series)

print(gfg)
```

**输出:**

> [1.00000000e+00 5.24288566e-22 1.60381089e-28 6.63967720e-36
> 3.67879441e-01]