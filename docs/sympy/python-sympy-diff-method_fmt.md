# sympy.diff() 方法

> 原文: [https://www.geeksforgeeks.org/python-sympy-diff-method/](https://www.geeksforgeeks.org/python-sympy-diff-method/)

借助 `sympy.diff()` 方法，我们可以找到数学表达式关于变量的微分。

## 语法

`sympy.diff(expression, reference variable)`

## 返回

返回微分后的数学表达式。

## 示例 #1

在这个示例中，我们可以看到通过使用 `sympy.diff()` 方法，可以找到数学表达式关于变量的微分。这里我们也使用 `symbols()` 方法将变量声明为符号。

```py
# import sympy
from sympy import *
x, y = symbols('x y')
gfg_exp = x + y
exp = sympy.expand(gfg_exp**2)
print("Before Differentiation : {}".format(exp))

# Use sympy.diff() method
dif = diff(exp, x)

print("After Differentiation : {}".format(dif))
```

**输出:**

> 差异化前: x**2 + 2*x*y + y**2
>
> 分化后: 2*x + 2*y

## 示例 #2

```py
# import sympy
from sympy import *
x, y = symbols('x y')
gfg_exp = sin(x)*cos(x)

print("Before Differentiation : {}".format(gfg_exp))

# Use sympy.diff() method
dif = diff(gfg_exp, x)

print("After Differentiation : {}".format(dif))
```

**输出:**

> 微分前: sin(x)*cos(x)
>
> 微分后: -sin(x)**2 + cos(x)**2