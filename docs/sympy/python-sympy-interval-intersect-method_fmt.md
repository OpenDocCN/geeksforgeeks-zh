# Python | sympy.Interval().intersect()方法

> 原文: [https://www.geeksforgeeks.org/python-sympy-interval-intersect-method/](https://www.geeksforgeeks.org/python-sympy-interval-intersect-method/)

借助`sympy.Interval().intersect()`方法，可以得到两个集合的交集。

> **语法:** `sympy.Interval(x, y).intersect(Interval(x, y))`
> **返回:** 返回两个集合的交集。

## 示例 1

在这个示例中，我们可以看到，通过使用`sympy.Interval().intersect()`方法，我们能够获得两个集合的交集。

```py
# import sympy, Interval
from sympy import Interval

# Using sympy.Interval().intersect() method
gfg = Interval(5, 10).intersect(Interval(7, 15))

print(gfg)
```

**输出:**

> [7, 8, 9, 10]

## 示例 2

```py
# import sympy, Interval
from sympy import Interval

# Using sympy.Interval().intersect() method
gfg = Interval(0.5, 0.9).intersect(Interval(0.7, 1.2))

print(gfg)
```

**输出:**

> [0.7, 0.8, 0.9]