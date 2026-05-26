# Python | Sympy encloses_point()方法

> 原文: [https://www.geeksforgeeks.org/python-sympy-encloses_point-method/](https://www.geeksforgeeks.org/python-sympy-encloses_point-method/)

在 sympy 中，`encloses_point()` 函数用于检查给定的点是否被给定的椭圆所包围。

## 语法

```
Syntax: Ellipse.encloses_point(point)
```

返回：如果点被椭圆包围则返回 `True`，否则返回 `False`。

## 示例#1:

```py
# import sympy and geometry module 
from sympy import * 
from sympy.geometry import *

x = Point(0, 0)

# making ellipse with given point as center and radii
e1 = Ellipse(x, 3, 2)

# using encloses_point() method
isEnclosed = e1.encloses_point((0, 0))

print(isEnclosed)
```

**输出:**

```py
True
```

## 示例#2:

```py
# import sympy and geometry module 
from sympy import * 
from sympy.geometry import *

x = Point(3, 1)

# making ellipse with given point as center, hradius and eccentricity
e2 = Ellipse(x, hradius = 3, eccentricity = Rational(4, 5))

# using encloses_point() method
isEnclosed = e2.encloses_point((4, 6))

print(isEnclosed)
```

**输出:**

```py
False
```