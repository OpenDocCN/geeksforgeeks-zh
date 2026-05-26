# Sympy `Line.perpendicular_segment()` 方法

> 原文: [https://www.geeksforgeeks.org/python-sympy-line-perpendicular_segment-method/](https://www.geeksforgeeks.org/python-sympy-line-perpendicular_segment-method/)

在 Sympy 中，`perpendicular_segment()` 函数用于从给定点向指定直线创建一条垂线段。该线段的端点是点 `p` 和包含该直线的直线上距离最近的点。

```
语法: Line.perpendicular_segment(p)

参数:
 p: Point

返回值: 
 segment: Segment
```

**示例#1:**

```py
# import sympy and Point, Line
from sympy import Point, Line

p1, p2, p3 = Point(0, 0), Point(1, 1), Point(0, 2)
l1 = Line(p1, p2)

# using perpendicular_segment() method
perpendicularSegment = l1.perpendicular_segment(p3)

print(perpendicularSegment)
```

**输出:**

```py
Segment2D(Point2D(0, 2), Point2D(1, 1))
```

**示例#2:**

```py
# import sympy and Point3D, Line3D
from sympy import Point3D, Line3D

p1, p2, p3 = Point3D(0, 0, 0), Point3D(1, 1, 1), Point3D(0, 2, 0)
ll1 = Line3D(p1, p2)

# using perpendicular_segment() method
s1 = l1.perpendicular_segment(p3)

perpendicularSegment = l1.perpendicular_segment(p3)

print(perpendicularSegment)
```

**输出:**

```py
Segment3D(Point3D(0, 2, 0), Point3D(2/3, 2/3, 2/3))
```