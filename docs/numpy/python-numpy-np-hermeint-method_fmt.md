# NumPy `hermeint()`方法

> 原文：[https://www.geeksforgeeks.org/python-numpy-np-hermeint-method/](https://www.geeksforgeeks.org/python-numpy-np-hermeint-method/)

借助`np.hermeint()`方法，我们可以对HermiteE级数进行积分。

## 语法
`np.hermeint(series, m)`

## 返回
返回积分后级数的系数。

## 例 1
在这个例子中我们可以看到，通过使用`np.hermeint()`方法，我们能够得到HermiteE级数的积分级数系数。

```python
# import numpy and hermeint
import numpy as np
from numpy.polynomial.hermite_e import hermeint

series = np.array([2, 0.3, 4, 0.5, 6])

# using np.hermeint() method
gfg = hermeint(series, m = 2)

print(gfg)
```

**输出:**
> [3. -0.225 1. 0.05 0.33333333 0.025 0.2]

## 例 2

```python
# import numpy and hermeint
import numpy as np
from numpy.polynomial.hermite_e import hermeint

series = np.array([1, 2, 3, 4, 5])

# using np.hermeint() method
gfg = hermeint(series, m = 3)

print(gfg)
```

**输出:**
> [-0.75 2.25 -1. 0.16666667 0.08333333 0.05 0.03333333 0.02380952]