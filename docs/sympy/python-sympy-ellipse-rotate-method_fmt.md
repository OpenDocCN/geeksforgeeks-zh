# Python | Sympy 椭圆.rotate()方法

> 原文: [https://www.geeksforgeeks.org/python-sympy-ellipse-rotate-method/](https://www.geeksforgeeks.org/python-sympy-ellipse-rotate-method/)

在 Sympy 中，`rotate()` 函数用于将椭圆围绕给定点逆时针旋转指定的角度。

## 语法
```py
Ellipse.rotate(angle=0, pt=None)
```

## 参数
- `angle`: 旋转角度，单位为弧度。
- `pt`: 旋转中心点，椭圆将围绕此点逆时针旋转。

## 返回值
返回旋转后的椭圆。

## 示例#1
```py
# import sympy and pi, Ellipse
from sympy import Ellipse, pi

# using Ellipse() method
e1 = Ellipse((1, 0), 2, 1)

# using rotate() method
e1.rotate(pi / 2)

print(e1)
```

**输出:**
```py
Ellipse(Point2D(0, 1), 1, 2)
```

## 示例#2
```py
# import sympy and pi, Ellipse
from sympy import Ellipse, pi

# using Ellipse() method
e2 = Ellipse((1, 0), 2, 1)

# using rotate() with given point method
e2.rotate(pi / 2, (1, 2))

print(e2)
```

**输出:**
```py
Ellipse(Point2D(3, 2), 1, 2)
```