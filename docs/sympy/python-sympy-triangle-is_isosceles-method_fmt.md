# Python–Sympy Triangle.is_isosceles() 方法

> 原文: [https://www.geeksforgeeks.org/python-sympy-triangle-is_isosceles-method/](https://www.geeksforgeeks.org/python-sympy-triangle-is_isosceles-method/)

在 Sympy 中，`Triangle.is_isosceles()` 函数用于检查给定的三角形是否为等腰三角形。等腰三角形是指两条或更多条边长度相同的三角形。

**语法:**
```py
Triangle.is_isosceles()
```

**返回值:**
*   `True`: 如果是等腰三角形。
*   `False`: 否则。

**示例 #1:**
```py
# import Triangle, Point
from sympy.geometry import Triangle, Point

# using Triangle()
t1 = Triangle(Point(0, 0), Point(6, 0), Point(3, 4))

# using is_isosceles()
isIsosceles = t1.is_isosceles()
print(isIsosceles)
```
输出:
```py
True
```

**示例 #2:**
```py
# import Triangle, Point
from sympy.geometry import Triangle, Point

# using Triangle()
t2 = Triangle(Point(0, 0), Point(3, 0), Point(3, 4))

# using is_isosceles()
isIsosceles = t2.is_isosceles()
print(isIsosceles)
```
输出:
```py
False
```