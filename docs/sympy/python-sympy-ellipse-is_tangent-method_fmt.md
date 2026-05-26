# Python | Sympy 椭圆. is_tangent()方法

> 原文: [https://www.geeksforgeeks.org/python-sympy-ellipse-is_tangent-method/](https://www.geeksforgeeks.org/python-sympy-ellipse-is_tangent-method/)

在 Sympy 中，`Ellipse.is_tangent()` 函数用于检查一个 `Ellipse`、`LinearEntity` 或 `Polygon` 是否与给定的 `Ellipse` 相切。

## 语法
```py
is_tangent(o)
```

## 参数
- `o`：一个 `Ellipse`、`LinearEntity` 或 `Polygon` 对象。

## 返回值
- 如果 `o` 与椭圆相切，则返回 `True`，否则返回 `False`。

## 异常
- 当提供了错误类型的参数时，引发 `NotImplementedError`。

## 示例

### 示例#1
```py
# import sympy and Point, Ellipse, Line
from sympy import Point, Ellipse, Line

p0, p1, p2 = Point(0, 0), Point(3, 0), Point(3, 3)

# using Line and Ellipse method
e1 = Ellipse(p0, 3, 2)
l1 = Line(p1, p2)

# using is_tangent method
e1.is_tangent(l1)
```

**输出:**
```py
True
```

### 示例#2
```py
# import sympy and Point, Ellipse, Line
from sympy import Point, Ellipse, Line

p0, p1, p2 = Point(0, 0), Point(4, 0), Point(4, 2)

# using Line and Ellipse method
e1 = Ellipse(p0, 3, 2)
l1 = Line(p1, p2)

# using is_tangent method
e1.is_tangent(l1)
```

**输出:**
```py
False
```