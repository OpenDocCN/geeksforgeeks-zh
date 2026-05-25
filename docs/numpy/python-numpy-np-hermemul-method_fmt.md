# NumPy `np.hermemul()` 方法

> 原文链接：[https://www.geeksforgeeks.org/python-numpy-np-hermemul-method/](https://www.geeksforgeeks.org/python-numpy-np-hermemul-method/)

借助 `np.hermemul()` 方法，可以得到两个 HermiteE 级数的乘积。

> **语法：** `np.hermemul(series1, series2)`
> **返回：** 返回两个 HermiteE 级数的乘积。

## 示例 1

在这个例子中，通过使用 `np.hermemul()` 方法，我们可以得到两个 HermiteE 级数的乘法。

```py
# import numpy and hermemul
import numpy as np
from numpy.polynomial.hermite_e import hermemul

series1 = np.array([1, 2, 3, 4])
series2 = np.array([10, 11, 12, 13])

# using np.hermemul() method
gfg = hermemul(series1, series2)

print(gfg)
```

**输出：**

> [416. 667. 1354. 632. 574. 87. 52.]

## 示例 2

```py
# import numpy and hermemul
import numpy as np
from numpy.polynomial.hermite_e import hermemul

series1 = np.array([11, 22, 33, 44])
series2 = np.array([10, 11, 12, 13])

# using np.hermemul() method
gfg = hermemul(series1, series2)

print(gfg)
```

**输出：**

> [4576. 7337. 14894. 6952. 6314. 957. 572.]