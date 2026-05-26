# Python Sympy Line.is_perpendicular 方法

> 原文: [https://www.geeksforgeeks.org/python-sympy-line-is_perpendicular-method/](https://www.geeksforgeeks.org/python-sympy-line-is_perpendicular-method/)

在 Sympy 中，函数 `is_perpendicular()` 用于检查两个线性实体是否垂直。

```py
Syntax: Line.is_perpendicular(l2)

Parameters:
 l1: LinearEntity
 l2: LinearEntity

Returns:
 True: if l1 and l2 are perpendicular,
 False: otherwise.
```

## 示例 #1

```py
# import sympy and Point, Line
from sympy import Point, Line

p1, p2, p3 = Point(0, 0), Point(1, 1), Point(-1, 1)

l1, l2 = Line(p1, p2), Line(p1, p3)

# using is_perpendicular() method
isPerpendicular = l1.is_perpendicular(l2)

print(isPerpendicular)
```

**输出:**

```py
True
```

## 示例 #2

```py
# import sympy and Point, Line
from sympy import Point, Line

p1, p2, p3 = Point(0, 0), Point(1, 1), Point(5, 3)

l1, l2 = Line(p1, p2), Line(p1, p3)

# using is_perpendicular() method
isPerpendicular = l1.is_perpendicular(l2)

print(isPerpendicular)
```

**输出:**

```py
False
```