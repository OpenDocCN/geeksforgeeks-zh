# Python | Sympy 平面 . projection() 方法

> 原文: [https://www.geeksforgeeks.org/python-sympy-plane-projection-method/](https://www.geeksforgeeks.org/python-sympy-plane-projection-method/)

在 Sympy 中，`Plane.projection()` 函数用于将给定点沿着平面法线方向投影到给定平面上，这意味着投影是沿着平面的法向量方向进行的。

```
Syntax:  Plane.projection(pt)

Parameters:
 pt: Point 或 Point3D

Returns: Point3D
```

`示例 1`:

```py
# import sympy and Plane, Point, Point3D
from sympy import Plane, Point, Point3D

p = Point(2, 2)

# using Plane()
p1 = Plane(Point3D(1, 2, 3), normal_vector =(0, 1, 1))

# using projection()
projectionPoint = p1.projection(p)

print(projectionPoint)
```

`输出`:

```py
Point3D(2, 7/2, 3/2)
```

`示例 2`:

```py
# import sympy and Plane, Point, Point3D
from sympy import Plane, Point, Point3D

p = Point3D(2, 2, 2)

# using Plane()
p1 = Plane(Point3D(1, 2, 3), normal_vector =(0, 1, 1))

# using projection()
projectionPoint = p1.projection(p)

print(projectionPoint)
```

`输出`:

```py
Point3D(2, 5/2, 5/2)
```