# Python | Sympy Plane.are_concurrent() 方法

> 原文：[https://www.geeksforgeeks.org/python-sympy-plane-are_concurrent-method/](https://www.geeksforgeeks.org/python-sympy-plane-are_concurrent-method/)

## Plane.are_concurrent() 方法

在 SymPy 中，`Plane.are_concurrent()` 函数用于检查给定的平面序列是否共点。如果两个或多个平面的交线是一条公共直线，则它们是共点的。

**语法：** `Plane.are_concurrent()`

**参数：**
- `planes`：平面的序列

**返回值：**
- `True`：如果它们共点，否则返回 `False`

### 示例 1

```py
# import sympy, Point3D and Plane
from sympy import Point3D, Plane

# using Plane() 
p1 = Plane(Point3D(5, 0, 0), normal_vector =(1, -1, 1))
p2 = Plane(Point3D(0, -2, 0), normal_vector =(3, 1, 1))

# using are_concurrent()
areConcurrent = Plane.are_concurrent(p1, p2)

print(areConcurrent)
```

**输出：**

```py
True
```

### 示例 2

```py
# import sympy, Point3D and Plane
from sympy import Point3D, Plane

# using Plane() 
p1 = Plane(Point3D(5, 0, 0), normal_vector =(1, -1, 1))
p2 = Plane(Point3D(0, -2, 0), normal_vector =(3, 1, 1))
p3 = Plane(Point3D(0, -1, 0), normal_vector =(5, -1, 9))

# using are_concurrent()
areConcurrent = Plane.are_concurrent(p1, p2, p3)

print(areConcurrent)
```

**输出：**

```py
False
```