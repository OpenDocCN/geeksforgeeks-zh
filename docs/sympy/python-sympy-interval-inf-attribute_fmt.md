# Python | sympy.Interval().inf 属性

> 原文: [https://www.geeksforgeeks.org/python-sympy-interval-inf-attribute/](https://www.geeksforgeeks.org/python-sympy-interval-inf-attribute/)

借助 `sympy.Interval().inf` 属性，可以得到区间的下确界值。

> **语法:** `sympy.Interval().inf`
> 
> **返回:** 返回区间的中值。

## 示例 1

在这个示例中，我们可以看到，通过使用 `sympy.Interval().inf` 属性，我们能够获得区间的下确界值。

```py
# import sympy, Interval
from sympy import Interval

# Using sympy.Interval().inf attribute
gfg = Interval(5, 10).inf

print(gfg)
```

**输出:**

> 5

## 示例 2

```py
# import sympy, Interval
from sympy import Interval

# Using sympy.Interval().inf method
gfg = Interval(-3, 1).inf

print(gfg)
```

**输出:**

> -3