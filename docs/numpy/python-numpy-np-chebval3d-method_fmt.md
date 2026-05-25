# Python NumPy `np.chebval3d()` 方法

> 原文链接: https://www.geeksforgeeks.org/python-numpy-np-chebval3d-method/

借助 `np.chebval3d()` 方法，可以得到切比雪夫级数在点 (x, y, z) 上求值后的系数数组。

## 语法
`np.chebval3d(x, y, z, c)`

## 返回值
在 (x, y, z) 上求值后返回数组。

## 示例 #1
在这个示例中，我们可以看到，通过使用 `np.chebval3d()` 方法，我们能够通过评估切比雪夫级数在点 (x, y, z) 上的值来获得系数数组。

```python
# import numpy
import numpy as np
import numpy.polynomial.chebyshev as cheb

# using np.chebval3d() method
gfg = cheb.chebval3d((2, 5), (1, 3), (4, 8), (2, -4, 1))

print(gfg)
```

**输出:**
> [408. 784.]

## 示例 2

```python
# import numpy
import numpy as np
import numpy.polynomial.chebyshev as cheb

# using np.chebval3d() method
gfg = cheb.chebval3d((1, 3, 5, 7), (2, 4, 8), (-10, -12), (2, -4, 1, 5, 1))

print(gfg)
```

**输出:**
> [1.04493678e+10]