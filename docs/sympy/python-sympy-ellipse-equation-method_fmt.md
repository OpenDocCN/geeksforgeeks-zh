# Python | Sympy 椭圆.方程()方法

> 原文: [https://www.geeksforgeeks.org/python-sympy-ellipse-equation-method/](https://www.geeksforgeeks.org/python-sympy-ellipse-equation-method/)

在 `sympy` 中，函数 `Ellipse.equation()` 用于生成给定椭圆的方程。

## 语法与参数

```
Syntax: Ellipse.equation(x='x', y='y', _slope=None)
```

**参数:**
- `x` : x轴的标签。默认值为 `'x'`。
- `y` : y轴的标签。默认值为 `'y'`。
- `_slope` : 长轴的斜率。当值为 `'None'` 时被忽略。

**返回值:**
- `equation` : 一个 `sympy` 表达式。

## 示例

### 示例#1

```py
# import sympy, Point and Ellipse
from sympy import Point, Ellipse
from sympy.abc import x, y

# using Ellipse() 
e1 = Ellipse(Point(1, 0), 3, 2)

# using equation()
eq1 = e1.equation(x, y);

print(eq1)
```

**输出:**

```py
y**2/4 + (x/3 - 1/3)**2 - 1
```

### 示例#2

```py
# import sympy, Point and Ellipse
from sympy import Point, Ellipse
from sympy.abc import x, y

# using Ellipse() 
e2 = Ellipse(Point(0, 0), 3, 2)

# using equation()
eq2 = e2.equation(x, y);

print(eq2)
```

**输出:**

```py
x**2/9 + y**2/4 - 1
```