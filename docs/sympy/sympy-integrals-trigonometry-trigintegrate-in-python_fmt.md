# Python 中的 SymPy 积分：trigintegrate()

> 原文: [https://www.geeksforgeeks.org/sympy-integrals-trigonometry-trigintegrate-in-python/](https://www.geeksforgeeks.org/sympy-integrals-trigonometry-trigintegrate-in-python/)

借助 `trigintegrate()` 方法，我们可以使用模式匹配计算三角函数的积分，并使用该方法返回积分函数。

> **语法:** `trigintegrate(f, x, conds='piecewise')`
> **返回:** 返回综合功能

## 示例 1

在这个例子中我们可以看到，通过使用 `trigintegrate()` 方法，我们能够使用模式匹配获得三角函数的积分值。

### Python 3

```python
# import trigintegrate
from sympy import Symbol, sin, cos, tan, sec, csc, cot
from sympy.integrals.trigonometry import trigintegrate
from sympy.abc import x

# Using trigintegrate() method
gfg = trigintegrate(tan(x)/cos(x), x)

print(gfg)
```

**输出:**

> 1/cos(x)

## 示例 2

### Python 3

```python
# import trigintegrate
from sympy import Symbol, sin, cos, tan, sec, csc, cot
from sympy.integrals.trigonometry import trigintegrate
from sympy.abc import x

# Using trigintegrate() method
gfg = trigintegrate(tan(x)*cot(x), x)

print(gfg)
```

**输出:**

> x