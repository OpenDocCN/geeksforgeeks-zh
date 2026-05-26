# Python 中的奇异积分、奇异函数与 `singularityintegrate()`

> 原文：[https://www.geeksforgeeks.org/sympy-integrals-singularityfunctions-singularityintegrate-in-python/](https://www.geeksforgeeks.org/sympy-integrals-singularityfunctions-singularityintegrate-in-python/)

借助 `singularityintegrate()` 方法，我们可以得到奇异函数的定积分，并利用这种方法返回积分函数。

**语法：**
`singularityintegrate(f, x)`

**返回：**
返回函数的定积分。

## 示例 1

在这个例子中我们可以看到，通过使用 `singularityintegrate()` 方法，我们能够通过使用该方法得到奇异函数的定积分，并返回积分函数。

```py
# import singularityintegrate
from sympy.integrals.singularityfunctions import singularityintegrate
from sympy import SingularityFunction, symbols, Function

x, a, n, y = symbols('x a n y')
f = Function('f')

# Using singularityintegrate() method
gfg = singularityintegrate(SingularityFunction(x**2 + 1, a, 2), x)

print(gfg)
```

**输出：**

> `SingularityFunction(x**2 + 1, a, 3)/3`

## 示例 2

```py
# import singularityintegrate
from sympy.integrals.singularityfunctions import singularityintegrate
from sympy import SingularityFunction, symbols, Function

x, a, n, y = symbols('x a n y')
f = Function('f')

# Using singularityintegrate() method
gfg = singularityintegrate(SingularityFunction(x**3, 4, -2), x)

print(gfg)
```

**输出：**

> `SingularityFunction(x**3, 4, -1)`