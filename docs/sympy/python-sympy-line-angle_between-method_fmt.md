# Python | Sympy Line.angle_between Method

> 原文: [https://www.geeksforgeeks.org/python-sympy-line-angle_between-method/](https://www.geeksforgeeks.org/python-sympy-line-angle_between-method/)

在 Sympy 中，`angle_between()` 函数用于返回由从原点发出的射线形成的非反射角，这些射线的方向与线性实体的方向向量相同。

## 方法说明

```py
Syntax: Line.angle_between(l2)

Parameters: 
  l1: LinearEntity
  l2: LinearEntity

Returns:
 angle: angle in radians
```

`注释:` 从向量 `v1` 和 `v2` 的点积可知：`dot(v1, v2) = |v1|*|v2|*cos(A)`，其中 `A` 是两个向量之间形成的角度。我们可以得到两条线的方向向量，并使用上述公式很容易地找到两条线之间的角度。

## 示例

`示例#1:`

```py
# import sympy and Point, Line, pi
from sympy import Point, Line, pi

# using Line() method
l1 = Line((0, 0), (1, 0))
l2 = Line((0, 0), (1, 1))

# using angle_between() method
rad = l1.angle_between(l2)

print(rad)
```

`输出:`

```py
pi/4
```

`例 2:`

```py
# import sympy and Point, Line, pi
from sympy import Point, Line, pi

# using Line() method
l1 = Line((0, 0), (1, 0))
l3 = Line((1, 1), (0, 0))

# using angle_between() method
rad = l1.angle_between(l3)

print(rad)
```

`输出:`

```py
3*pi/4
```