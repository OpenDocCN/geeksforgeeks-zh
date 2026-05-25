# Python | NumPy `np.polyfromroots()` 方法

> 原文：[https://www.geeksforgeeks.org/python-numpy-np-polyfromroots-method/](https://www.geeksforgeeks.org/python-numpy-np-polyfromroots-method/)

`np.polyfromroots()` 方法用于生成给定根的多项式级数。

> **语法：** `np.polyfromroots(roots)`
> **参数：**
> `roots`：【array_like】输入包含根的序列。
>
> **返回：**【ndarray】多项式级数系数的一维数组。

## 代码示例 #1

```py
# Python program explaining
# numpy.polyfromroots() method

# importing numpy as np   
# and numpy.polynomial.polynomial module as geek 
import numpy as np 
import numpy.polynomial.polynomial as geek

# Input roots

roots = (2, 4, 8)

# using np.polyfromroots() method 
res = geek.polyfromroots(roots)

# Resulting polynomial series coefficient
print (res) 
```

**输出：**

```py
[-64.  56. -14.   1.]
```

## 代码示例 #2

```py
# Python program explaining
# numpy.polyfromroots() method

# importing numpy as np   
# and numpy.polynomial.polynomial module as geek 
import numpy as np 
import numpy.polynomial.polynomial as geek

# Input roots
s = (1, 2, 3, 4, 5)

# using np.polyfromroots() method 
res = geek.polyfromroots(s)

# Resulting polynomial series coefficient
print (res) 
```

**输出：**

```py
[-120.  274. -225.   85.  -15.    1.]
```