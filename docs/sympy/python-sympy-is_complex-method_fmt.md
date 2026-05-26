# sympy.is_complex 方法

> 原文: [https://www.geeksforgeeks.org/python-sympy-is_complex-method/](https://www.geeksforgeeks.org/python-sympy-is_complex-method/)

借助 `sympy.is_complex` 方法，我们可以检查元素是否为复数，该方法将返回布尔值，即真或假。

> **语法:** `sympy.is_complex`
> **返回:** 复数则返回真，否则返回假。

## 示例 #1

在这个示例中，我们可以看到，通过使用 `sympy.is_complex` 方法，我们能够检查复数值，它将返回一个布尔值。

```py
# import sympy
from sympy import *

# Use sympy.is_complex method
gfg = simplify(2 * I).is_complex

print(gfg)
```

**输出:**

> True

## 示例 #2

```py
# import sympy
from sympy import *

# Use sympy.is_complex method
gfg = simplify(5).is_complex

print(gfg)
```

**输出:**

> False