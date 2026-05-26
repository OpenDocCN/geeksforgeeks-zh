# Python | sympy.div()方法

> 原文: [https://www.geeksforgeeks.org/python-sympy-div-method/](https://www.geeksforgeeks.org/python-sympy-div-method/)

函数 `div()` 提供带余数的多项式除法。也就是说，对于多项式 `f` 和 `g`，它计算 `q` 和 `r`，使得 `f = g*q + r` 且 `deg(r) < deg(q)`。

```
Syntax: sympy.div(f, g, domain='QQ')
Return: division of polynomials with remainder
```

## 示例#1

```py
# import sympy
from sympy import *

f = 5 * x**2 + 10 * x + 3
g = 2 * x + 2

# Using sympy.div() method
q, r = div(f, g, domain ='QQ')

print(q)
print(r)
```

**输出:**

```py
5*x/2 + 5/2
```

## 示例#2

```py
# import sympy
from sympy import *

f = 5 * x**2 + 10 * x + 3
g = 2 * x**2 + 2

# Using sympy.div() method
q, r = div(f, g, domain ='QQ')

print(q)
print(r)
```

**输出:**

```py
5/2
10*x - 2
```