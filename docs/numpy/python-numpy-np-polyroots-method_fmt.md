# Python NumPy `np.polyroots()` 方法

> 原文：[https://www.geeksforgeeks.org/python-numpy-np-polyroots-method/](https://www.geeksforgeeks.org/python-numpy-np-polyroots-method/)

`np.polyroots()` 方法用于计算一个**多项式序列**的根。返回多项式的根。

## 语法
`np.polyroots(c)`

## 参数
- `c`：【array_like】多项式级数系数的一维数组。

## 返回值
- 【ndarray】根的数组。如果所有的根都是真实的，那么结果也是实数，否则就是复数。

## 代码示例 1

```py
# Python program explaining
# numpy.polyroots() method

# importing numpy as np   
# and numpy.polynomial.polynomial module as geek 
import numpy as np 
import numpy.polynomial.polynomial as geek

# Input polynomial series coefficients
s = (2, 4, 8)

# using np.polyroots() method 
res = geek.polyroots(s)

# Resulting polynomial series coefficient
print(res)
```

**输出：**

```py
[-0.25-0.4330127j -0.25+0.4330127j]
```

## 代码示例 2

```py
# Python program explaining
# numpy.polyroot() method

# importing numpy as np   
# and numpy.polynomial.polynomial module as geek 
import numpy as np 
import numpy.polynomial.polynomial as geek

# polynomial series coefficients
s = (1, 2, 3, 4, 5)

# using np.polyroots() method 
res = geek.polyroots(s)

# Resulting polynomial series
print(res)
```

**输出：**

```py
[-0.53783227-0.35828469j -0.53783227+0.35828469j  0.13783227-0.67815439j
  0.13783227+0.67815439j]
```