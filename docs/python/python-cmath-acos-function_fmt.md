# Python cmath.acos() 函数

> 原文: [https://www.geeksforgeeks.org/python-cmath-acos-function/](https://www.geeksforgeeks.org/python-cmath-acos-function/)

`cmath` 模块包含许多用于复数数学运算的函数。`cmath.acos()` 函数返回一个复数的弧余弦值。该函数传递的值可以是 `int`、`float` 和 `complex` 类型的数字。

> **语法:** `cmath.acos(x)`
>
> **参数:**
> - **x:** 此参数是要传递给 `acos()` 的值。
>
> **返回:** 该函数返回一个复数的弧余弦值。

以下示例说明了上述功能的使用:

**示例 1:** 在这个示例中，我们可以看到，通过使用 `cmath.acos()` 方法，我们能够通过向其传递任意值来获得其值。

## Python 3

```py
# Python code to implement
# the acos()function

# importing "cmath"
# for mathematical operations
import cmath

# using cmath.acos() method
val = cmath.acos(3)

print(val)
```

**输出:**

```py
-1.762747174039086j
```

**示例 2:**

## Python 3

```py
# Python code to implement
# the acos()function

# importing "cmath"
# for mathematical operations
import cmath

# using cmath.acos() method
val = cmath.acos(2 + 5j)

print(val)
```

**输出:**

```py
(1.1961255219693696-2.3830308809003258j)
```