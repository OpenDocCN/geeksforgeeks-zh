# Python | `Plane.projection_line()` 方法

> 原文：[https://www.geeksforgeeks.org/python-sympy-plane-projection_line-method/](https://www.geeksforgeeks.org/python-sympy-plane-projection_line-method/)

在 Sympy 中，`Plane.projection_line()` 函数用于通过包含该直线的法平面，将给定的直线投影到给定的平面上。

```py
语法: Plane.projection_line(line)

参数:
 line: LinearEntity 或 LinearEntity3D

返回: Point3D, Line3D, Ray3D 或 Segment3D
```

## 示例 1

```py
# 导入 sympy 及 Plane, Line, Line3D, Point, Point3D
from sympy import Plane, Line, Line3D, Point, Point3D

p = Line(Point(1, 2), Point(2, 3))

# 使用 Plane()
p1 = Plane(Point3D(1, 2, 3), normal_vector=(1, 0, 1))

# 使用 projection_line()
projectionLine = p1.projection_line(p)

print(projectionLine)
```

**输出:**

```py
Line3D(Point3D(5/2, 2, 3/2), Point3D(3, 3, 1))
```

## 示例 2

```py
# 导入 sympy 及 Plane, Line, Line3D, Point, Point3D
from sympy import Plane, Line, Line3D, Point, Point3D

p = Line3D(Point3D(1, 2, 3), Point(0, 0, 0))

# 使用 Plane()
p2 = Plane(Point3D(1, 1, 1), normal_vector=(0, 0, 0))

# 使用 projection_line()
projectionLine = p2.projection_line(p)

print(projectionLine)
```

**输出:**

```py
Line3D(Point3D(1, 2, 3), Point3D(2, 0, 2))
```