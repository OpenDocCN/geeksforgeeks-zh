# Python | sympy Triangle()方法

> 原文: [https://www.geeksforgeeks.org/python-sympy-triangle-method/](https://www.geeksforgeeks.org/python-sympy-triangle-method/)

函数 `Triangle()` 将给定的点作为三角形的顶点，并借助面积公式计算三角形的面积。

## 语法
```py
Triangle(x, y, z).area
```

## 参数
其中 `x`, `y`, `z` 是坐标点。

## 返回值
三角形的面积。

## 示例#1
```py
# import sympy and geometry module
from sympy import * 
from sympy.geometry import *

x = Point(0, 0)
y = Point(1, 1)
z = Point(1, 0)

# Using  Triangle(x, y, z).area
giveArea = Triangle(x, y, z).area

print(giveArea)
```

**输出:**
```py
1/2
```

## 例 2
```py
# import sympy and geometry module
from sympy import * 
from sympy.geometry import *

x = Point(1, 2)
y = Point(2, 0)
z = Point(1, 0)

# Using  Triangle(x, y, z).area
giveArea = Triangle(x, y, z).area

print(giveArea)
```

**输出:**
```py

```