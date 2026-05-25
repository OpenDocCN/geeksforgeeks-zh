# Python | Numpy np.hermezero()方法

> 原文: [https://www.geeksforgeeks.org/python-numpy-np-hermezero-method/](https://www.geeksforgeeks.org/python-numpy-np-hermezero-method/)

借助`np.hermezero()`方法，我们可以用 **hermezero** 代替`np.zeros()`。

## 语法

`np.hermezero`

## 返回

返回零的数组。

## 示例 1

在这个示例中，我们可以看到，通过使用`np.hermezero()`方法，我们能够获得与`np.zeros`方法相同的功能。

```py
# import numpy and hermezero
import numpy as np
from numpy.polynomial.hermite_e import hermezero

# using np.hermezero() method
gfg = hermezero + [1, 2, 3, 4, 5]

print(gfg)
```

**输出:**

> [1 2 3 4 5]

## 示例 2

```py
# import numpy and hermezero
import numpy as np
from numpy.polynomial.hermite_e import hermezero

# using np.hermezero() method
gfg = hermezero + [[2, 4, 6], [3, 6, 9]]

print(gfg)
```

**输出:**

> [[2 4 6]
> [3 6 9]]