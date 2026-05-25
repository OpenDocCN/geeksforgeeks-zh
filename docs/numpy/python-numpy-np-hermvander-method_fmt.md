# Python | Numpy np.hermvander()方法

> 原文: [https://www.geeksforgeeks.org/python-numpy-np-hermvander-method/](https://www.geeksforgeeks.org/python-numpy-np-hermvander-method/)

借助于`np.hermvander()`方法，我们可以从给定度数的埃尔米特级数中得到伪范德蒙矩阵。

### 语法
`np.hermvander(x, deg)`

### 返回
返回给定度数的伪范德蒙矩阵。

**例#1：**
在这个例子中我们可以看到，通过使用`np.hermvander()`方法，我们能够得到hermite级数的伪范德蒙矩阵。

```py
# import numpy and hermvander
import numpy as np
from numpy.polynomial.hermite import hermvander

x = np.array([1, 2, 3, 5, 7, 11])
deg = 2

# using np.hermvander() method
gfg = hermvander(x, deg)

print(gfg)
```

**输出:**

```
[[ 1.  2.  2.]
 [ 1.  4. 14.]
 [ 1.  6. 34.]
 [ 1. 10. 98.]
 [ 1. 14.194.]
 [ 1. 22.482.]]
```

**例 2：**

```py
# import numpy and hermvander
import numpy as np
from numpy.polynomial.hermite import hermvander

x = np.array([5, 10, -10, -5])
deg = 3

# using np.hermvander() method
gfg = hermvander(x, deg)

print(gfg)
```

**输出:**

```
[[ 1.00e+00  1.00e+01  9.80e+01  9.40e+02]
 [ 1.00e+00  2.00e+01  3.98e+02  7.88e+03]
 [ 1.00e+00 -2.00e+01  3.98e+02 -7.88e+03]
 [ 1.00e+00 -1.00e+01  9.80e+01 -9.40e+02]]
```