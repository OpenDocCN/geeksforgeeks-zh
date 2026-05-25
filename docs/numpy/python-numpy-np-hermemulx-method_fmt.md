# numpy的hermemulx()方法

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-num py-NP-hermmulx 方法/

借助`np.hermemulx()`方法，可以得到hermiteE级数与自变量`x`的乘积。

> **语法:** `np.hermemulx(series)`
> **返回:** 返回hermiteE级数与`x`的乘积。

**例1:**
在这个例子中我们可以看到，通过使用`np.hermemulx()`方法，我们能够利用这个方法得到hermiteE级数与自变量`x`的乘积。

```py
# import numpy and hermemulx
import numpy as np
from numpy.polynomial.hermite_e import hermemulx

series = np.array([1, 2, 3, 4])

# using np.hermemulx() method
gfg = hermemulx(series)

print(gfg)
```

**输出:**

> [2. 7. 14. 3. 4.]

**例2:**

```py
# import numpy and hermemulx
import numpy as np
from numpy.polynomial.hermite_e import hermemulx

series = np.array([11, 22, 33, 44])

# using np.hermemulx() method
gfg = hermemulx(series)

print(gfg)
```

**输出:**

> [22. 77. 154. 33. 44.]