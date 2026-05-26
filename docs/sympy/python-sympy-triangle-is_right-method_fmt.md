# Python–Sympy Triangle.is_right()方法

> 原文: [https://www.geeksforgeeks.org/python-sympy-triangle-is_right-method/](https://www.geeksforgeeks.org/python-sympy-triangle-is_right-method/)

在 Sympy 中，`Triangle.is_right()` 函数用于检查给定的三角形是否为直角三角形。直角三角形是指其中一个角为直角（90度）的三角形。

## 语法

```
Syntax: Triangle.is_right()
```

返回值：
- `True`: 如果是直角三角形。
- `False`: 否则。

## 示例#1

```py
# import Triangle, Point
from sympy.geometry import Triangle, Point

# using Triangle()
t1 = Triangle(Point(0, 0), Point(4, 0), Point(4, 3))

# using is_right()
isRight = t1.is_right()
print(isRight)
```

**输出:**

```py
True
```

## 示例#2

```py
# import Triangle, Point
from sympy.geometry import Triangle, Point

# using Triangle()
t2 = Triangle(Point(0, 0), Point(2, 0), Point(4, 3))

# using is_right()
isRight = t2.is_right()
print(isRight)
```

**输出:**

```py
False
```