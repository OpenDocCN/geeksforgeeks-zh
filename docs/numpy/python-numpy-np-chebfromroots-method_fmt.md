# Python | NumPy `chebfromroots()` 方法

> 原文: [https://www.geeksforgeeks.org/python-numpy-np-chebfromroots-method/](https://www.geeksforgeeks.org/python-numpy-np-chebfromroots-method/)

借助 `np.chebfromroots()` 方法，我们可以得到以根为参数传递的切比雪夫级数。

> **语法:** `np.chebfromroots(roots)`
> **返回:** 返回切比雪夫系列。

## 示例 #1

在这个示例中，我们可以看到，通过使用 `np.chebfromroots()` 方法，我们能够获得由通过参数传递的根生成的切比雪夫级数。

```py
# import numpy
import numpy as np
import numpy.polynomial.chebyshev as cheb

# using np.chebfromroots() method
gfg = cheb.chebfromroots((2, 4, 8, 1))

print(gfg)
```

**输出:**

> [9.9375e+01 -1.3125e+02 3.5500e+01 -3.7500e+00 1.2500e-01]

## 示例 2

```py
# import numpy
import numpy as np
import numpy.polynomial.chebyshev as cheb

# using np.chebfromroots() method
gfg = cheb.chebfromroots((-3, 4, -5, 1, 10))

print(gfg)
```

**输出:**

> [-5.19125e+02 4.52375e+02 8.00000e+01 -1.24375e+01 -8.75000e-01 6.25000e-02]