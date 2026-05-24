# Python 中的数学常数

> 原文: [https://www.geeksforgeeks.org/constants-of-maths-in-python/](https://www.geeksforgeeks.org/constants-of-maths-in-python/)

[`math`](https://www.geeksforgeeks.org/mathematical-functions-python-set-1-numeric-functions/) 模块是 Python 中的标准内置模块，可用于执行数学任务。`math` 模块有一组方法和常数。

**注:** 更多信息请参考 [math-库函数](https://www.geeksforgeeks.org/tag/python-math-library-functions/)

## 1. Python `math.e` 常量

`math.e` 常量返回欧拉数：2.71828182846。

> **语法:** `math.e`
>
> **返回:** 返回一个浮点值，2.71828182846，代表数学常数 `e`

**示例:**

```py
# Import math Library
import math

# Print the value of Euler e
print (math.e)
```

**输出:**

```py
2.718281828459045
```

## 2. Python `math.pi` 常量

`math.pi` 常量返回值 pi: 3.14159265359。它被定义为圆的周长与直径之比。

> **语法:** `math.pi`
>
> **返回:** 一个浮点值，3.14159265359，代表数学常数 `PI`

**示例:**

```py
# Import math Library
import math

# Print the value of pi
print (math.pi)
```

**输出:**

```py
3.141592653589793
```

## 3. Python `math.tau` 常量

`math.tau` 常量返回值 τ: 6.283185307179586。它被定义为圆的周长与半径之比。

> **语法:** `math.tau`
>
> **返回:** 一个浮点值，6.283185307179586，代表数学常数 `τ`

**示例:**

```py
# Import math Library
import math

# Print the value of tau
print (math.tau)
```

**输出:**

```py
6.283185307179586
```

## 4. Python `math.inf` 常量

`math.inf` 常量返回正无穷大。对于负无穷大，使用 `-math.inf`。`inf` 常数相当于 `float("inf")`。

> **语法:** `math.inf`
>
> **返回:** 一个浮点值，返回正无穷大的值。

**示例:**

```py
# Import math Library
import math

# Print the positive infinity
print (math.inf)

# Print the negative infinity
print (-math.inf)
```

**输出:**

```py
inf
-inf
```

## 5. Python `math.nan` 常量

`math.nan` 常量返回一个浮点 `nan`（不是数字）值。该值不是合法数字。`nan` 常数相当于 `float("nan")`。

> **语法:** `math.nan`
>
> **返回:** 一个浮点值 `nan`（不是数字）

**示例:**

```py
# Import math Library
import math

# Print the value of nan
print (math.nan)
```

**输出:**

```py
nan
```