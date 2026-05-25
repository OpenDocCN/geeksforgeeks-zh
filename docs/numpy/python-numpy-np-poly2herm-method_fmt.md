# Python | Numpy np.poly2herm()方法

> 原文: [https://www.geeksforgeeks.org/python-numpy-np-poly2herm-method/](https://www.geeksforgeeks.org/python-numpy-np-poly2herm-method/)

借助`np.poly2herm()`方法，可以从多项式中得到埃尔米特级数系数。

> **语法:** `np.poly2herm(polynomial)`
> **返回:** 返回埃尔米特级数的系数。

## 示例#1

在这个示例中，我们可以看到，通过使用`np.poly2herm()`方法，我们能够从多项式中获得埃尔米特级数的系数。

```py
# import numpy and poly2herm
import numpy as np
from numpy.polynomial.hermite import poly2herm

x = np.array([0.1, 0.2, 0.3, 0.4, 0.5])
# using np.poly2herm() method
gfg = poly2herm(x)

print(gfg)
```

**输出:**

> [0.625 0.4 0.45 0.05 0.03125]

## 例 2

```py
# import numpy and poly2herm
import numpy as np
from numpy.polynomial.hermite import poly2herm

x = np.array([-0.5, -0.4, -0.3, -0.2, -0.1, 0, 0.1, 0.2, 0.3, 0.4, 0.5])
# using np.poly2herm() method
gfg = poly2herm(x)

print(gfg)
```

**输出:**

> [1.61968750e+01 1.27750000e+01 4.09828125e+01 8.50625000e+00
> 1.33296875e+01 1.24687500e+00 1.29765625e+00 5.78125000e-02
> 4.5171875e-02 7]