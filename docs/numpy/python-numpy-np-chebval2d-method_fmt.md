# NumPy `chebval2d()` 方法

> 原文链接：https://www.geeksforgeeks.org/python-numpy-np-chebval2d-method/

借助 `np.chebval2d()` 方法，可以计算切比雪夫级数在点 `(x, y)` 处的值，其中系数数组由 `c` 给出。

## 语法
`np.chebval2d(x, y, c)`

## 返回值
返回在点 `(x, y)` 上求值后的数组。

## 示例 #1
在这个示中，我们可以看到，通过使用 `np.chebval2d()` 方法，我们能够通过评估切比雪夫级数在点 `(x, y)` 处的值来获得结果数组。

```py
# import numpy
import numpy as np
import numpy.polynomial.chebyshev as cheb

# using np.chebval2d() method
gfg = cheb.chebval2d((2, 5), (1, 3), (2, -4, 1))

print(gfg)
```

**输出:**
> [32. 94.]

## 示例 #2

```py
# import numpy
import numpy as np
import numpy.polynomial.chebyshev as cheb

# using np.chebval2d() method
gfg = cheb.chebval2d((1, 3, 5, 7), (2, 4, 8), (2, -4, 1, 5, 1))

print(gfg)
```

**输出:**
> [719680. 6486180. 52831708.]