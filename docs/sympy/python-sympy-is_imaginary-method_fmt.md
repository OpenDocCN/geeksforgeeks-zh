# Python | sympy.is_imaginary 方法

> 原文: [https://www.geeksforgeeks.org/python-sympy-is_imaginary-method/](https://www.geeksforgeeks.org/python-sympy-is_imaginary-method/)

借助 `sympy.is_imaginary` 方法，我们可以检查一个元素是否是虚数。该方法将返回布尔值，即 `True` 或 `False`。

> **语法:** `sympy.is_imaginary`
> **返回:** 若为虚数则返回 `True`，否则返回 `False`。

## 示例 1

在这个示例中，我们可以看到，通过使用 `sympy.is_imaginary` 方法，我们能够检查虚数，它将返回一个布尔值。

```py
# import sympy
from sympy import *

# Use sympy.is_imaginary method
gfg = simplify(2 * I).is_imaginary

print(gfg)
```

**输出:**

> True

## 示例 2

```py
# import sympy
from sympy import *

# Use sympy.is_imaginary method
gfg = simplify(5).is_imaginary

print(gfg)
```

**输出:**

> False