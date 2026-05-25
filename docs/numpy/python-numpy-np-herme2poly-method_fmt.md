# Python | Numpy np.herme2poly()方法

> 原文: [https://www.geeksforgeeks.org/python-numpy-np-herme2poly-method/](https://www.geeksforgeeks.org/python-numpy-np-herme2poly-method/)

借助`np.herme2poly()`方法，我们可以从hermiteE级数中得到多项式。

## 语法
`np.herme2poly(series)`

## 返回
返回多项式的系数。

## 示例#1
在这个示例中，我们可以看到，通过使用`np.herme2poly()`方法，我们能够从hermiteE级数中获得多项式的系数。

```py
# import numpy and herme2poly
import numpy as np
from numpy.polynomial.hermite_e import herme2poly

x = np.array([0.1, 0.2, 0.3, 0.4, 0.5])
# using np.herme2poly() method
gfg = herme2poly(x)

print(gfg)
```

**输出:**
> [1.3 -1. -2.7 0.4 0.5]

## 示例#2

```py
# import numpy and herme2poly
import numpy as np
from numpy.polynomial.hermite_e import herme2poly

x = np.array([-0.5, -0.4, -0.3, -0.2, -0.1, 0, 0.1, 0.2, 0.3, 0.4, 0.5])
# using np.herme2poly() method
gfg = herme2poly(x)

print(gfg)
```

**输出:**
> [-4.4300e+02 3.5720e+02 2.2413e+03 -4.8320e+02 -1.5136e+03 1.4700e+02
> 3.0670e+02 -1.4200e+01 -2.2200e+01 4.0000e-01 5.0000e-01]