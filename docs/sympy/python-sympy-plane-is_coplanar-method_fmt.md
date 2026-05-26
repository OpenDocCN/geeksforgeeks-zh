# Python | sympy Plane.is_coplanar()方法

> 原文: [https://www.geeksforgeeks.org/python-sympy-plane-is_coplanar-method/](https://www.geeksforgeeks.org/python-sympy-plane-is_coplanar-method/)

在 SymPy 中，函数 `Plane.is_coplanar()` 用于检查给定的平面是否共面。

```py
语法: Plane.is_coplanar(p)

参数:
 p: 一个 Plane 对象

返回值:
 True: 如果平面共面，否则返回 False
```

## 示例 1

```py
# 导入 sympy, Point3D 和 Plane
from sympy import Point3D, Plane

o = (0, 0, 0)

# 使用 Plane()
p1 = Plane(o, (1, 1, 1))
p2 = Plane(o, (2, 2, 2))

# 使用 is_coplanar()
isCoplanar = p1.is_coplanar(p2)

print(isCoplanar)
```

**输出:**

```py
True
```

## 示例 2

```py
# 导入 sympy, Point3D 和 Plane
from sympy import Point3D, Plane

o = (0, 0, 0)

# 使用 Plane()
p3 = Plane(o, (1, 1, 1))
p4 = Plane(o, (3, 2, 1))

# 使用 is_coplanar()
isCoplanar = p3.is_coplanar(p4)

print(isCoplanar)
```

**输出:**

```py
False
```