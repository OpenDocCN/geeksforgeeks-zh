# Python–Sympy polygon.encloses_point()方法

> 原文: [https://www.geeksforgeeks.org/python-sympy-polygon-encloses_point-method/](https://www.geeksforgeeks.org/python-sympy-polygon-encloses_point-method/)

在 Sympy 中，函数`polygon.encloses_point()`用于检查给定点是否被多边形包围。如果给定点位于多边形内部，则返回`True`，否则返回`False`。在多边形的边界上也被认为是`False`的。

```
Syntax: Polygon.encloses_point(p)

Parameters:
 p: Point

Returns:
 True: if point lies inside polygon, otherwise False.
```

## 示例#1:

```py
# import sympy import Point, Polygon
from sympy import Point, Polygon

# creating points using Point()
p1, p2, p3 = map(Point, [(0, 0), (5, 0), (5, 5)])

# creating polygon using Polygon()
poly = Polygon(p1, p2, p3)

# using encloses_point()
isEnclosed = poly.encloses_point(Point(2, 1))

print(isEnclosed)
```

**输出:**

```py
True
```

## 例 2:

```py
# import sympy import Point, Polygon
from sympy import Point, Polygon

# creating points using Point()
p1, p2, p3 = map(Point, [(0, 0), (4, 0), (4, 4)])

# creating polygon using Polygon()
poly = Polygon(p1, p2, p3)

# using encloses_point()
isEnclosed = poly.encloses_point(Point(2, 2))

print(isEnclosed)
```

**输出:**

```py
False
```