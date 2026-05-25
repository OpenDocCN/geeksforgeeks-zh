# Python | Numpy np.legdiv()方法

> 原文: [https://www.geeksforgeeks.org/python-numpy-np-legdiv-method/](https://www.geeksforgeeks.org/python-numpy-np-legdiv-method/)

`np.legdiv()`方法是将一个勒让德级数划分为另一个。它返回两个勒让德级数 `c1 / c2` 的余数商。

> **语法:** `np.legdiv(c1, c2)`
> **参数:**
> `c1`, `c2`: 【`array_like`】勒让德级数系数的一维数组，从低到高排序。
>
> **返回:** 【`ndarray`】表示商和余数的勒让德级数系数。

## 代码#1 :

```py
# Python program explaining
# numpy.legdiv() method

# importing numpy as np   
# and numpy.polynomial.legendre module as geek 
import numpy as np 
import numpy.polynomial.legendre as geek

# Legendre series coefficients

s1 = (2, 4, 8) 
s2 = (1, 3, 5)

# using np.legdiv() method 
res = geek.legdiv(s1, s2)

# Resulting legendre series
print (res) 
```

**Output:**

```py
(array([ 1.6]), array([ 0.4, -0.8]))
```

## 代码#2 :

```py
# Python program explaining
# numpy.legdiv() method

# importing numpy as np   
# and numpy.polynomial.legendre module as geek 
import numpy as np 
import numpy.polynomial.legendre as geek

# Legendre series coefficients
s1 = (10, 20, 30, 40, 50) 
s2 = (2, 4, 6, 8, 10)

# using np.legdiv() method 
res = geek.legdiv(s1, s2)

# Resulting Legendre series
print (res) 
```

**Output:**

```py
(array([ 5.]), array([ 0.]))
```