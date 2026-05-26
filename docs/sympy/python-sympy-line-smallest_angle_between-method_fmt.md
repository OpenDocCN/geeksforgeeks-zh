# Python | Sympy Line.smallest_angle_between() 方法

> 原文: [https://www.geeksforgeeks.org/python-sympy-line-smallest_angle_between-method/](https://www.geeksforgeeks.org/python-sympy-line-smallest_angle_between-method/)

在 Sympy 中，`smallest_angle_between()` 函数用于返回两条直线交点处的非钝角。

## 语法

```py
smallest_angle_between(l2)
```

**参数：**
- `l1`: `LinearEntity`
- `l2`: `LinearEntity`

**返回值：**
- 角度 [弧度制]

## 示例

**示例 #1:**

```py
# import sympy and Point, Line, pi
from sympy import Point, Line, pi

# using Line() method
l1 = Line((0, 0), (1, 0))
l2 = Line((1, 1), (0, 0))

# using smallest_angle_between() method
rad = l2.smallest_angle_between(l1)

print(rad)
```

**输出：**

```py
pi/4
```

**示例 #2:**

```py
# import sympy and Point, Line, pi
from sympy import Point, Line, pi

# using Line() method
l1 = Line((0, 0), (1, 0))
l3 = Line((3, 1), (0, 0))

# using smallest_angle_between() method
rad = l3.smallest_angle_between(l1)

print(rad)
```

**输出：**

```py
acos(3*sqrt(10)/10)
```