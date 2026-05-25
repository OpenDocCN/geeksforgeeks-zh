# Python | Numpy np.hermpow()方法

> 原文: [https://www.geeksforgeeks.org/python-numpy-np-hermpow-method/](https://www.geeksforgeeks.org/python-numpy-np-hermpow-method/)

借助`np.hermpow()`方法，可以得到埃尔米特级数的幂。

## 语法与返回值

语法: `np.hermpow(series, pow)`
返回: 加幂后返回级数的系数。

## 示例

### 例 1

在这个例子中，通过使用`np.hermpow()`方法，我们能够得到埃尔米特级数幂次后的级数系数。

```py
# import numpy and hermpow
import numpy as np
from numpy.polynomial.hermite import hermpow

series = np.array([1, 2, 3, 4, 5])

# using np.hermpow() method
gfg = hermpow(series, 2)

print(gfg)
```

输出:

> [10449. 8308. 21970. 6228. 8003. 1004. 846. 40. 25.]

### 例 2

```py
# import numpy and hermpow
import numpy as np
from numpy.polynomial.hermite import hermpow

series = np.array([1, 2, 3])

# using np.hermpow() method
gfg = hermpow(series, 3)

print(gfg)
```

输出:

> [2257. 2358. 3837. 908. 711. 54. 27.]