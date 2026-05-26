# Python Sympy Line.is_parallel() 方法

> 原文: [https://www.geeksforgeeks.org/python-sympy-line-is_parallel-method/](https://www.geeksforgeeks.org/python-sympy-line-is_parallel-method/)

在 Sympy 中，`is_parallel()` 函数用于检查两个线性实体是否平行。

```
Syntax: Line.is_parallel(l2)

Parameters:
 l1: LinearEntity
 l2: LinearEntity

Returns:
 True: if l1 and l2 are parallel,
 False: otherwise.
```

## 示例 #1

```py
# import sympy and Point, Line
from sympy import Point, Line

p1, p2 = Point(0, 0), Point(1, 1)
p3, p4 = Point(3, 4), Point(6, 7)

l1, l2 = Line(p1, p2), Line(p3, p4)

# using is_parallel() method
isParallel = Line.is_parallel(l1, l2)

print(isParallel)
```

**输出:**

```py
True
```

## 示例 #2

```py
# import sympy and Point, Line
from sympy import Point, Line

p1, p2 = Point(0, 0), Point(1, 1)
p3, p4 = Point(3, 4), Point(6, 6)

l1, l2 = Line(p1, p2), Line(p3, p4)

# using is_parallel() method
isParallel = Line.is_parallel(l1, l2)

print(isParallel)
```

**输出:**

```py
False
```