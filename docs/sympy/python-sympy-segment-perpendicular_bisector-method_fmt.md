# Python | Sympy Segment.perpendicular_bisector()方法

> 原文：`https://www.geeksforgeeks.org/python-sympy-segment-perpendicular_bisector-method/`

在 Sympy 中，函数 `perpendicular_bisector()` 用于查找给定线段的垂直平分线。如果没有指定点，或者指定的点不在平分线上，则平分线作为 `Line` 返回。否则，返回一个连接指定点与平分线和线段交点的 `Segment`。

```py
Syntax: Segment.perpendicular_bisector(p=None)

Parameters:
 p: Point

Returns:
 bisector: Line or Segment

```

## 示例#1

```py
# import sympy and Point, Segment
from sympy import Point, Segment

p1, p2, p3 = Point(0, 0), Point(6, 6), Point(5, 1)
s1 = Segment(p1, p2)

# using perpendicular_bisector() method
perpendicularBisector = s1.perpendicular_bisector()

print(perpendicularBisector)
```

**输出:**

```py
Line2D(Point2D(3, 3), Point2D(-3, 9))
```

## 示例#2

```py
# import sympy and Point, Segment
from sympy import Point, Segment

p1, p2, p3 = Point(0, 0), Point(6, 6), Point(5, 1)
s1 = Segment(p1, p2)

# using perpendicular_bisector() method
perpendicularBisector = s1.perpendicular_bisector(p3)

print(perpendicularBisector)
```

**输出:**

```py
Segment2D(Point2D(5, 1), Point2D(3, 3))
```