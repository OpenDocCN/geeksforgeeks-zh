# Python | Sympy line . are _ concurrent 方法

> 原文: [https://www . geesforgeks . org/python-sympy-line-are _ concurrent-method/](https://www.geeksforgeeks.org/python-sympy-line-are_concurrent-method/)

## 方法介绍

在 Sympy 中，`are_concurrent()` 函数用于检查给定的线性实体（直线）是否共点。如果两个或多个线性实体相交于单个点，则它们是共点的。

## 语法和参数

```py
Syntax: Line.are_concurrent(lines)

Parameters:
 lines: a sequence of linear entities.

Returns:
 True:  if the set of linear entities intersect in one point
 False: otherwise.
```

## 示例

### 示例#1:

```py
# import sympy and Point, Line
from sympy import Point, Line

p1, p2 = Point(0, 0), Point(3, 5)
p3, p4 = Point(-2, -2), Point(0, 2)

l1, l2, l3 = Line(p1, p2), Line(p1, p3), Line(p1, p4)

# using are_concurrent() method
areConcurrent = Line.are_concurrent(l1, l2, l3)

print(areConcurrent)
```

**输出:**

```py
True
```

### 示例#2:

```py
# import sympy and Point, Line
from sympy import Point, Line

p1, p2 = Point(0, 0), Point(3, 5)
p3, p4 = Point(-2, -2), Point(0, 2)

l1, l2, l3 = Line(p1, p3), Line(p1, p4), Line(p2, p3)

# using are_concurrent() method
areConcurrent = Line.are_concurrent(l1, l2, l3)

print(areConcurrent)
```

**输出:**

```py
False
```