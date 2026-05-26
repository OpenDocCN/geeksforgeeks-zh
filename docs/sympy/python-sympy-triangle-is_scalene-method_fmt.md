# Python–Sympy . triangle . is_scalene()方法

> 原文: [https://www.geeksforgeeks.org/python-sympy-triangle-is_scalene-method/](https://www.geeksforgeeks.org/python-sympy-triangle-is_scalene-method/)

在 Sympy 中，`Triangle.is_scalene()` 函数用于检查给定的三角形是否为不等边三角形。不等边三角形是指所有边长度都不同的三角形。

语法：`Triangle.is_scalene()`

返回值：
- `True`：如果是不等边三角形。
- `False`：否则。

## 示例#1

```py
# import Triangle, Point
from sympy.geometry import Triangle, Point

# using Triangle()
t1 = Triangle(Point(0, 0), Point(3, 0), Point(1, 2))

# using is_scalene()
isScalene = t1.is_scalene()
print(isScalene)
```

输出：

```py
True
```

## 示例#2

```py
# import Triangle, Point
from sympy.geometry import Triangle, Point

# using Triangle()
t2 = Triangle(Point(0, 0), Point(4, 0), Point(2, 4))

# using is_scalene()
isScalene = t2.is_scalene()
print(isScalene)
```

输出：

```py
False
```